---
id: ddia-notes
title: DDIA
---

# Designing Data Intensive Applications

A short, focused technical note to kick off the documentation.

## Summary
A concise overview of a small utility: reading a file, transforming contents, and writing output.

## Chapters
- Preface
- Section I: Foundations of Data Systems
    - Chapter 1 - Reliable, Scalable & Maintainable Applications
    - Chapter 2 - Data Models & Query Languages
    - Chapter 3 - Storage & Retrieval
    - Chapter 4 - Encoding & Evolution
- Section II: Distributed Data
    - Chapter 5 - Replication 
    - Chapter 6 - Partitioning
    - Chapter 7 - Transactions
    - Chapter 8 - The Trouble with Distributed Systems
    - Chapter 9 - Consistency & Consensus
- Section III: Derived Data
    - Chapter 10 - Batch Processing
    - Chapter 11 - Stream Processing
    - Chapter 12 - The Future of Data Systems

## Section I: Foundations of Data Systems
#### Dicussing the fundamental ideas that underpin the design of data-intensive applications

### Preface

We call an application **data-intensive** if data is its primary challenge--the equantity of data, the complexity of data, or the speed at which it is changing--as opposed to __compute-intensive__, where CPU cycles are the bottleneck

New types of database systems ("NoSQL") have been getting lots of attention, but message queues, caches, search indexes, frameworks for batch and stream processing, and related technologies are very important too. Many applications use some combination of these

If any of the following are true for you, you'll find this book valuable:
- You want to learn how to make data systems scalable, for example, to support web or mobile apps with millions of users
- You need to make applications highly available (minimizing downtime) and operationally robust
- You are looking for ways of making systems easier to maintain in the long run, even as they grow and as requirements and technologies change
- You have a natural curiosity for the way things work and want to know what goes on inside major websites and online services. This book breaks down the internals of various databases and data processing systems, and it’s great fun to explore the bright thinking that went into their design.

There is truth in that statement: building for scale that you don’t need is wasted effort and may lock you into an inflexible design. In effect, it is a form of premature optimization. However, it’s also important to choose the right tool for the job, and different technologies each have their own strengths and weaknesses. As we shall see, relational databases are important but not the final word on dealing with data.

> [GitHub repo for all of the references linked in the book](https://github.com/ept/ddia-references)


### Chapter 1 - Reliable, Scalable & Maintainable Applications
#### Introduces the terminology and approach that we’re going to use throughout this book. It examines what we actually mean by words like reliability, scalability, and maintainability, and how we can try to achieve these goals.

A data-intensive application is typically built from standard building blocks that provide commonly needed functionality. 
For example, many applications need to:

1. Store data so that they, or another application, can find it again later (databases)
2. Remember the result of an expensive operation, to speed up reads (caches)
3. Allow users to search data by keyword or filter it in various ways (search indexes)
4. Send a message to another process, to be handled asynchronously (stream processing)
5. Periodically crunch a large amount of accumulated data (batch processing) 

![Figure 1-1. One possible architecture for a data system that combines several components](image.png)

When you combine several tools in order to provide a service, the service’s interface or application programming interface (API) usually hides those implementation details from clients. Now you have essentially created a new, special-purpose data system from smaller, general-purpose components. 

If you are designing a data system or service, a lot of tricky questions arise. How do you ensure that the data remains correct and complete, even when things go wrong internally? How do you provide consistently good performance to clients, even when parts of your system are degraded?

- Reliability: The system should continue to work correctly (performing the correct function at the desired level of performance) even in the face of adversity (hardware or software faults, and even human error). 
- Scalability: As the system grows (in data volume, traffic volume, or complexity), there should be reasonable ways of dealing with that growth. 
- Maintainability: Over time, many different people will work on the system (engineering and operations, both maintaining current behavior and adapting the system to new use cases), and they should all be able to work on it productively. 

_Reliability_
Typical expecations of a software application include: 
- The application performs the function that the user expected.
- It can tolerate the user making mistakes or using the software in unexpected ways.
- Its performance is good enough for the required use case, under the expected load and data volume. 
- The system prevents any unauthorized access and abuse. 

If all those things together mean “working correctly,” then we can understand reliability as meaning, roughly, “continuing to work correctly, even when things go wrong.” 

The things that can go wrong are called *faults*, and systems that anticipate faults and can cope with them are called *fault-tolerant* or resilient. 
> A fault is usually defined as one component of the system deviating from its spec, whereas a failure is when the system as a whole stops providing the required service to the user. It is impossible to reduce the probability of a fault to zero; therefore it is usually best to design fault-tolerance mechanisms that prevent faults from causing failures. 

*Hardware Faults*
When we think of causes of system failure, hardware faults quickly come to mind

Our first response is usually to add redundancy to the individual hardware components in order to reduce the failure rate of the system.

When one component dies, the redundant component can take its place while the broken component is replaced. This approach cannot completely prevent hardware problems from causing failures, but it is well understood and can often keep a machine running uninterrupted for years. Until recently, redundancy of hardware components was sufficient for most applications, since it makes total failure of a single machine fairly rare. As long as you can restore a backup onto a new machine fairly quickly, the downtime in case of failure is not catastrophic in most applications.

However, as data volumes and applications’ computing demands have increased, more applications have begun using larger numbers of machines, which proportionally increases the rate of hardware faults.

Hence there is a move toward systems that can tolerate the loss of entire machines, by using software fault-tolerance techniques in preference or in addition to hardware redundancy. Such systems also have operational advantages: a single-server system requires planned downtime if you need to reboot the machine (to apply operating system security patches, for example), whereas a system that can tolerate machine failure can be patched one node at a time, without downtime of the entire system.

*Software Errors*

Another class of fault is a systematic error within the system. Such faults are harder to anticipate, and because they are correlated across nodes, they tend to cause many more system failures than uncorrelated hardware faults [5]. Examples include: 
- A software bug that causes every instance of an application server to crash when given a particular bad input.
- A runaway process that uses up some shared resource—CPU time, memory, disk space, or network bandwidth. 
- A service that the system depends on that slows down, becomes unresponsive, or starts returning corrupted responses. 
- Cascading failures, where a small fault in one component triggers a fault in another component, which in turn triggers further faults. 

The bugs that cause these kinds of software faults often lie dormant for a long time until they are triggered by an unusual set of circumstances. In those circumstances, it is revealed that the software is making some kind of assumption about its environment—and while that assumption is usually true, it eventually stops being true for some reason. There is no quick solution to the problem of systematic faults in software. Lots of small things can help: carefully thinking about assumptions and interactions in the system; thorough testing; process isolation; allowing processes to crash and restart; measuring, monitoring and analyzing system behavior in production.

*Human Errors*

How do we make our systems reliable, in spite of unreliable humans? 
- Design systems in a way that minimizes opportunities for error. For example, well-designed abstractions, APIs, and admin interfaces make it easy to do “the right thing” and discourage “the wrong thing.” 
- Decouple the places where people make the most mistakes from the places where they can cause failures. In particular, provide fully featured non-production sandbox environments where people can explore and experiment safely, using real data, without affecting real users.
- Test thoroughly at all levels, from unit tests to whole-system integration tests and manual tests.
- Allow quick and easy recovery from human errors, to minimize the impact in case of failure. For example, make it fast to roll back configuration changes, roll out new code gradually.
- Set up detailed and clear monitoring, such as perfomance metrics and error rates. Monitoring can show us early warning signals and allow us to check whether any assumptions or constraints are being violated. When a problem occurs, metrics can be invaluable in diagnosing the issue. 

_Scalability_

One common reason for degradation is increased load: perhaps the system has grown from 10,000 concurrent users to 100,000 concurrent users, or from 1 million to 10 million.
 Perhaps it is processing much larger volumes of data than it did before. 
 
 *Scalability* is the term we use to describe a system’s ability to cope with increased load. 
 
 Note, however, that it is not a one-dimensional label that we can attach to a system: it is meaningless to say “X is scalable” or “Y doesn’t scale.” Rather, discussing scalability means considering questions like “If the system grows in a particular way, what are our options for coping with the growth?” and “How can we add computing resources to handle the additional load?”

*Describing Load*

Load can be described with a few numbers which we call load parameters. The best choice of parameters depends on the architecture of your system: it may be requests per second to a web server, the ratio of reads to writes in a database, the number of simultaneously active users in a chat room, the hit rate on a cache, or something else.

*Describing Performance*

In a batch processing system such as Hadoop, we usually care about throughput—the number of records we can process per second, or the total time it takes to run a job on a dataset of a certain size.iii In online systems, what’s usually more important is the service’s response time—that is, the time between a client sending a request and receiving a response.

> Latency and response time are often used synonymously, but they are not the same. The response time is what the client sees: besides the actual time to process the request (the service time), it includes network delays and queueing delays. Latency is the duration that a request is waiting to be handled—during which it is latent, awaiting service.

In practice, in a system handling a variety of requests, the response time can vary a lot. We therefore need to think of **response time** not as a single number, but as a _distribution of values that you can measure_.



### Chapter 2 - Data Models & Query Languages
#### Compares several different data models and query languages—the most visible distinguishing factor between databases from a developer’s point of view. We will see how different models are appropriate to different situations.



### Chapter 3 - Storage & Retrieval
#### This chapter turns to the internals of storage engines and looks at how databases lay out data on disk. Different storage engines are optimized for different workloads, and choosing the right one can have a huge effect on performance.

### Chapter 4 - Encoding & Evolution
#### Here we compare various formats for data encoding (serialization) and especially examine how they fare in an environment where application requirements change and schemas need to adapt over time.


### Section II: Distributed Data
#### Data distrubuted across multiple machines and the challenges associated with distributed data

### Chapter 5 - Replication 

### Chapter 6 - Partitioning & Sharding

### Chapter 7 - Transactions

### Chapter 8 - The Trouble with Distributed Systems

### Chapter 9 - Consistency & Consensus

### Setion III: Derived Data
#### When there is no one database that can do everything well, applications need to integrate several different databases, caches, indexes and so on

### Chapter 10 - Batch Processing

### Chapter 11 - Stream Processing

### Chapter 12 - The Future of Data Systems