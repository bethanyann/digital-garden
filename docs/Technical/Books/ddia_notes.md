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

### Preface

We call an application **data-intensive** if data is its primary challenge--the equantity of data, the complexity of data, or the speed at which it is changing--as opposed to __compute-intensive__, where CPU cycles are the bottleneck

New types of database systems ("NoSQL") have been getting lots of attention, but message queues, caches, search indexes, frameworks for batch and stream processing, and related technologies are very important too. Many applications use some combination of these

If any of the following are true for you, you'll find this book valuable:
- You want to learn how to make data systems scalable, for example, to support web or mobile apps with millions of users
- You need to make applications highly available (minimizing downtime) and operationally robust
- You are looking for ways of making systems easier to maintain in the long run, even as they grow and as requirements and technologies change
- You have a natural curiosity for the way things work and want to know what goes on inside major websites and online services. This book breaks down the internals of various databases and data processing systems, and it’s great fun to explore the bright thinking that went into their design.

There is truth in that statement: building for scale that you don’t need is wasted effort and may lock you into an inflexible design. In effect, it is a form of premature optimization. However, it’s also important to choose the right tool for the job, and different technologies each have their own strengths and weaknesses. As we shall see, relational databases are important but not the final word on dealing with data.

> [GitHub repo for all of the references linked in the book)(https://github.com/ept/ddia-references)


### Chapter 1 - Reliable, Scalable & Maintainable Applications

### Chapter 2 - Data Models & Query Languages

### Chapter 3 - Storage & Retrieval

### Chapter 4 - Encoding & Evolution

## Section II: Distributed Data

### Chapter 5 - Replication 

### Chapter 6 - Partitioning

### Chapter 7 - Transactions

### Chapter 8 - The Trouble with Distributed Systems

### Chapter 9 - Consistency & Consensus

## Setion III: Derived Data

### Chapter 10 - Batch Processing

### Chapter 11 - Stream Processing

### Chapter 12 - The Future of Data Systems