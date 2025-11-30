---
id: dont-make-me-think
title: Don't Make Me Think, Revisited
subtitle: A Common Sense Approach to Web Usability (Voices That Matter)
---

 A Common Sense Approach to Web Usability (Voices That Matter)
 By Steve Krug

### Summary
In the last few years, making things more usable has become almost everybody’s responsibility. Visual designers and developers now often find themselves doing things like interaction design (deciding what happens next when the user clicks, taps, or swipes) and information architecture (figuring out how everything should be organized).

### Guiding Principles
#### Things that make us think

- Another needless source of question marks over people’s heads is links and buttons that aren’t obviously clickable. As a user, I should never have to devote a millisecond of thought to whether things are clickable—or not.
- The point is that every question mark adds to our cognitive workload, distracting our attention from the task at hand. The distractions may be slight but they add up, especially if it’s something we do all the time like deciding what to click on.
- And as a rule, people don’t like to puzzle over how to do things. They enjoy puzzles in their place—when they want to be entertained or diverted or challenged—but not when they’re trying to find out what time their dry cleaner closes. The fact that the people who built the site didn’t care enough to make things obvious—and easy—can erode our confidence in the site and the organization behind it.
- The most important thing you can do is to understand the basic principle of eliminating question marks. When you do, you’ll begin to notice all the things that make you think in the sites and apps you use. And eventually you’ll learn to recognize and avoid them in the things you’re building.

> So why, then? If Web pages are going to be effective, they have to work most of their magic at a glance. And the best way to do this is to create pages that are self-evident, or at least self-explanatory. 

#### How we really use the Web
The difference between how we think people use Web sites and how they actually use them. When we’re creating sites, we act as though people are going to pore over each page, reading all of our carefully crafted text, figuring out how we’ve organized things, and weighing their options before deciding which link to click. What they actually do most of the time (if we’re lucky) is glance at each new page, scan some of the text, and click on the first link that catches their interest or vaguely resembles the thing they’re looking for. There are almost always large parts of the page that they don’t even look at.

__FACT OF LIFE #1: We don’t read pages. We scan them.__
- Why do we scan? We’re usually on a mission. Most Web use involves trying to get something done, and usually done quickly. As a result, Web users tend to act like sharks: They have to keep moving, or they’ll die. We just don’t have the time to read any more than necessary. We know we don’t need to read everything. On most pages, we’re really only interested in a fraction of what’s on the page. We’re just looking for the bits that match our interests or the task at hand, and the rest of it is irrelevant. Scanning is how we find the relevant bits.  We’re good at it. It’s a basic skill: When you learn to read, you also learn to scan.

__FACT OF LIFE #2: We don’t make optimal choices. We satisfice.__
- When we’re designing pages, we tend to assume that users will scan the page, consider all of the available options, and choose the best one. In reality, though, most of the time we don’t choose the best option—we choose the first reasonable option, a strategy known as satisficing. As soon as we find a link that seems like it might lead to what we’re looking for, there’s a very good chance that we’ll click it.
- So why don’t Web users look for the best choice? ￼ We’re usually in a hurry. And as Klein points out, “Optimizing is hard, and it takes a long time. Satisficing is more efficient.” ￼ There’s not much of a penalty for guessing wrong. Unlike firefighting, the penalty for guessing wrong on a Web site is usually only a click or two of the Back button, making satisficing an effective strategy. (Back is the most-used button in Web browsers.) Weighing options may not improve our chances. On poorly designed sites, putting effort into making the best choice doesn’t really help. You’re usually just as well off going with your first guess and using the Back button if it doesn’t work out. ￼ Guessing is more fun. It’s less work than weighing options, and if you guess right, it’s faster. And it introduces an element of chance—the pleasant possibility of running into something surprising and good. Of course, this is not to say that users never weigh options before they click. It depends on things like their frame of mind, how pressed they are for time, and how much confidence they have in the site.

__FACT OF LIFE #3: We don’t figure out how things work. We muddle through.__
- One of the things that becomes obvious as soon as you do any usability testing—whether you’re testing Web sites, software, or household appliances—is the extent to which people use things all the time without understanding how they work, or with completely wrong-headed ideas about how they work.

#### Conventions are your friends 
- If you’re going to innovate, you have to understand the value of what you’re replacing (or as Dylan put it, “To live outside the law, you must be honest”), and it’s easy to underestimate just how much value conventions provide.
- If you’re not going to use an existing Web convention, you need to be sure that what you’re replacing it with either (a) is so clear and self-explanatory that there’s no learning curve—so it’s as good as the convention, or (b) adds so much value that it’s worth a small learning curve.
- My recommendation: Innovate when you know you have a better idea, but take advantage of conventions when you don’t.
- The rule of thumb is that you can—and should—be as creative and innovative as you want, and add as much aesthetic appeal as you can, as long as you make sure it’s still usable.
- Consistency is always a good thing to strive for within your site or app. If your navigation is always in the same place, for instance, I don’t have to think about it or waste time looking for it. But there will be cases where things will be clearer if you make them slightly inconsistent.
- If you can make something significantly clearer by making it slightly inconsistent, choose in favor of clarity.

#### Create effective visual hierarchies 
- Pages with a clear visual hierarchy have three traits: The more important something is, the more prominent it is.
- Things that are related logically are related visually.
- Things are “nested” visually to show what’s part of what.
- A good visual hierarchy saves us work by preprocessing the page for us, organizing and prioritizing its contents in a way that we can grasp almost instantly.

> But over time I’ve come to think that what really counts is not the number of clicks it takes me to get to what I want (although there are limits), but rather how hard each click is—the amount of thought required and the amount of uncertainty about whether I’m making the right choice.


#### Some assistance may be required
- When you can’t avoid giving me a difficult choice, you need to go out of your way to give me as much guidance as I need—but no more. This guidance works best when it’s ￼ Brief: The smallest amount of information that will help me ￼ Timely: Placed so I encounter it exactly when I need it ￼ Unavoidable: Formatted in a way that ensures that I’ll notice it
- Examples are tips adjacent to form fields, “What’s this?” links, and even tool tips.

- Another major source of needless words is instructions. The main thing you need to know about instructions is that no one is going to read them—at least not until after repeated attempts at “muddling through” have failed. And even then, if the instructions are wordy, the odds of users finding the information they need are pretty low.


### Things You Need to Get Right

__The unbearable lightness of browsing__

- This lack of physicality is both good and bad. On the plus side, the sense of weightlessness can be exhilarating and partly explains why it’s so easy to lose track of time on the Web—the same as when we’re “lost” in a good book.
- I think we talk about Web navigation because “figuring out where you are” is a much more pervasive problem on the Web than in physical spaces. We’re inherently lost when we’re on the Web, and we can’t peek over the aisles to see where we are. Web navigation compensates for this missing sense of place by embodying the site’s hierarchy, creating a sense of “there.” Navigation isn’t just a feature of a Web site; it is the Web site, in the same way that the building, the shelves, and the cash registers are Sears. Without it, there’s no there there. The moral? Web navigation had better be good.

__The overlooked purposes of navigation__

- Two of the purposes of navigation are fairly obvious: to help us find whatever it is we’re looking for and to tell us where we are
- It tells us what’s here.
- It tells us how to use the site.

__Secondary, tertiary, and whatever comes after tertiary__

- The moral? It’s vital to have sample pages that show the navigation for all the potential levels of the site before you start arguing about the color scheme.

__Page names, or why I love to drive in LA__

- There are four things you need to know about page names: 
1. Every page needs a name.
2. The name needs to be in the right place.
3. The name needs to be prominent.
4. The name needs to match what I clicked.

__Try the trunk test__

- If the page is well designed, when your vision clears you should be able to answer these questions without hesitation: ￼ What site is this? (Site ID)  What page am I on? (Page name) What are the major sections of this site? (Sections) What are my options at this level? (Local navigation) Where am I in the scheme of things? (“ You are here” indicators) How can I search?
- When you’re designing pages, it’s tempting to think that people will reach them by starting at the Home page and following the nice, neat paths you’ve laid out. But the reality is that we’re often dropped down in the middle of a site with no idea where we are because we’ve followed a link from a search engine, a social networking site, or email from a friend, and we’ve never seen this site’s navigation scheme before.

### Make Sure You Got Them Right

__Focus groups are not usability tests__

- The main difference is that in usability tests, you watch people actually use things, instead of just listening to them talk about them. Focus groups can be great for determining what your audience wants, needs, and likes—in the abstract. They’re good for testing whether the idea behind your site makes sense and your value proposition is attractive, to learn more about how people currently solve the problems your site will help them with, and to find out how they feel about you and your competitors. But they’re not good for learning about whether your site works and how to improve it. The kinds of things you learn from focus groups—like whether you’re building the right product—are things you should know before you begin designing or building anything, so focus groups are best used in the planning stages of a project. Usability tests, on the other hand, should be used through the entire process.
- Testing reminds you that not everyone thinks the way you do, knows what you know, and uses the Web the way you do.


### Larger Concerns and Outside Influences

__Don't hide your affordances under a bushel__

- Affordances are visual clues in an object’s design that suggest how we can use it.
- Unfortunately, the way they used it wasn’t exactly what he intended. He’s clarified it in the new edition of Everyday Things by proposing to call the clues “signifiers” instead, but it may be too late to put that genie back in the bottle. With apologies to Don, I’m going to keep calling them affordances here because (a) it’s still the prevailing usage, and (b) it makes my head hurt too much otherwise.
- Affordances are the meat and potatoes of a visual user interface. For instance, the three-dimensional style of some buttons makes it clear they’re meant to be clicked. The same as with the scent of information for links, the clearer the visual cues, the more unambiguous the signal.

__No cursor = no hover = no clue__

- Before touch screens arrived, Web design had come to rely heavily on a feature called hover—the ability of screen elements to change in some way when the user points the cursor at them without clicking. But a capacitive touch screen (used on almost all mobile devices) can’t accurately sense that a finger is hovering above the glass, only when the finger has touched it. This is why they don’t have a cursor.
- As a result, many useful interface features that depended on hover are no longer available, like tool tips, buttons that change shape or color to indicate that they’re clickable, and menus that drop down to reveal their contents without forcing you to make a choice. As a designer, you need to be aware that these elements don’t exist for mobile users and try to find ways to replace them.

__Flat design: Friend or foe?__

- The distinctions required to draw attention to an affordance often need to be multi-dimensional: It’s the position of something (e.g., in the navigation bar) and its formatting (e.g., reversed type, all caps) that tell you it’s a menu item. By removing a number of these distinctions from the design palette, Flat design makes it harder to differentiate things.

__Delightful is the new black__

- I don’t spend much time thinking about whether things are useful because it strikes me as more of a marketing question, something that should be established before any project starts, using methods like interviews, focus groups, and surveys. Whether something is desirable seems like a marketing question too, and I’ll have more to say about that in the final chapter. For now let’s talk about delight, learnability, and memorability and how they apply to mobile apps.
- Delight is a bit hard to pin down; it’s more one of those “I’ll know it when I feel it” kind of things. Rather than a definition, it’s probably easier to identify some of the words people use when describing delightful products: fun, surprising, impressive, captivating, clever, and even magical. 
- Delightful apps usually come from marrying an idea about something people would really enjoy being able to do, but don’t imagine is possible, with a bright idea about how to use some new technology to accomplish it.
- Delight is sort of like the extra credit assignment of user experience design. Making your app delightful is a fine objective. Just don’t focus so much attention on it that you forget to make it usable, too.

__Usability as common courtesy__

- Most of this book has been about building clarity into Web sites: making sure that users can understand what it is they’re looking at—and how to use it—without undue effort. Is it clear to people? Do they “get it”? But there’s another important component to usability: doing the right thing—being considerate of the user.


__Things that deminish goodwill__

- Here are a few of the things that tend to make users feel like the people publishing a site don’t have their best interests at heart: ￼ Hiding information that I want. The most common things to hide are customer support phone numbers, shipping rates, and prices.
- Punishing me for not doing things your way. I should never have to think about formatting data: whether or not to put dashes in my Social Security number, spaces in my credit card number, or parentheses in my phone number. Many sites perversely insist on no spaces in credit card numbers, when the spaces actually make it much easier to type the number correctly. Don’t make me jump through hoops just because you don’t want to write a little bit of code.
- Asking me for information you don’t really need. Most users are very skeptical of requests for personal information and find it annoying if a site asks for more than what’s needed for the task at hand.
- Shucking and jiving me. We’re always on the lookout for faux sincerity, and disingenuous attempts to convince me that you care about me can be particularly annoying.
- Your site looks amateurish. You can lose goodwill if your site looks sloppy, disorganized, or unprofessional, like no effort has gone into making it presentable.
- There may be times when you’ll choose to have your site do some of these user-unfriendly things deliberately. Sometimes it makes business sense not to do exactly what the customer wants. For instance, uninvited pop-ups almost always annoy people to some extent. But if your statistics show you can get 10 percent more revenue by using pop-ups and you think it’s worth annoying your users, you can do it. It’s a business decision. Just be sure you do it in an informed way, rather than inadvertently.

- One difference between User Centered Design and User Experience Design is their scope. UCD focused on designing the right product and making sure that it was usable. UX sees its role as taking the users’ needs into account at every stage of the product life cycle, from the time they see an ad on TV, through purchasing it and tracking its delivery online, and even returning it to a local branch store.


### Recommended Reading 

1. A Web for Everyone: Designing Accessible User Experiences by Sarah Horton and Whitney Quesenbery. (Their approach: “Good UX equals good accessibility. Here’s how to do both.”)

2. Web Accessibility: Web Standards and Regulatory Compliance by Jim Thatcher et al. (“ Here are the laws and regulations, and we’ll help you understand how to meet them.”)
  
3. Leah Buley’s The User Experience Team of One: A Research and Design Survival Guide is written specifically for people who are “the only person in your company practicing (or aspiring to practice) user centered design” or who “regularly work on a team where you are the only UX person.” Chapters 3 (Building Support for Your Work) and 4 (Growing Yourself and Your Career) are full of good advice and useful resources.









