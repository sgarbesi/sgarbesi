---
categories: coding js
date: 2014-06-12
feature_style: "background-image: url('https://m.media-amazon.com/images/M/MV5BN2JjMTllN2YtODY5Yi00MzdmLTg2YWItMGYwNDYyZDNiNjUyXkEyXkFqcGdeQXVyMjYwNDA2MDE@._V1_.jpg')"
layout: post
subtitle: "Save yourself now from a number of headaches down the line."
title: "Why To Document Your Code"
---

I'll cover my personal experiences coding with other engineers and how not heavily documenting our code grew into a number of 🤕 headaches.

---

## Old Philosophy

![](https://images.chesscomfiles.com/uploads/v1/images_users/tiny_mce/MikeKlein/phpcDFUvu.png)

I use to preach, live and code by the following philosophy:

> Comments should only be written for excessively complex areas and algorithms that live within the code. If you’re looking at a fundamental/basic block of code for a project and don’t understand it, you shouldn’t modify it. Instead, you should ask someone who has worked with the code or do your own research before possibly breaking a number of unknowns because of your ignorance.

As far as the 🤷 ignorance part goes, I still 100% agree.

As far as the comments being reserved for excessively complex areas and algorithms, I have now come to disagree, with what I believe is a good reason.

---

![](https://web.archive.org/web/20150206072948im_/http://salvatore.garbesi.com/content/images/2014/Jun/TiNOd.jpg)

## New Philosophy

I now preach, live and code by the following philosophy:

> Document your code as if it were an open-source project being actively used by thousands of engineers and you were the sole contributor to the project. If you're looking at a fundamental/basic block of code for a project and don't understand it even after reading the documentation, you shouldn't modify it. Instead, you should ask someone who has worked with the code or do your own research before possibly breaking a number of unknowns because of your ignorance.

In the following sections I'll elaborate on my new philosophy and hopefully, save you from making some of the mistakes that I've made in the past which I've since learned from.

---

![](/img/post-assets/2014-06-12-why-to-document-your-code/Bart-Looking_Monster.png)

## The Puppy That Became The Beast

If you've ever worked on a project for an extended period of time, then this will come as no surprise to you. A coding project will eventually do one of two things in its life span. It will either evolve or become deprecated *(there are rare exceptions but for the sake of the majority let's just run with it).*

With evolution comes new additions, compatibilities, patches, and testing just to scratch the surface. This in turn produces a higher level of complexity within the code. What started out as this 🐶 **cute little puppy** *(small project)* that you use to pet (patch) occasionally and that would make you smile with pride *(check this out!)*, has now become this 🐲 **monstrous f#!king beast** that even the Greek Gods wouldn't be capable of slaying if called upon to do so.

**Here's an example to help put things into perspective.**

I'm actively working on a project that started with 2 engineers and birthed 50k lines of code. Fast forward 2 years later, the project now has 9 engineers and contains over 250k lines of code. Do you see what happened here? Since the project wasn't deprecated, it evolved. That cute 50k line 🐶 puppy turned into a 250k line 🐲 beast. Even I, one of the fathers of the project, can't even tame it anymore. It's like a 🏴‍☠️ rebellious teenager, it can only be controlled to a certain extent, and not by a single person.

---

![](https://sites.williams.edu/f18-engl117-01/files/2017/11/maxresdefault.jpg)

## Avoiding Code Replication

In the 📖 Engineers Bible (which if not written, I will write one day) it states:

> Thou shall not rewrite a block of code to perform the same goal twice!

**Code replication is bad.** Okay, that's me being nice; it's horrible! If you're an engineer and you're rewriting the same code over and over again to do the same thing, you're a bad engineer!

> (Put your hand out for a second)
> ✋ ****SLAP****
> That's a bad engineer.
> Don't you do that no more!
> 👌 ***Got it?***
> Good!

**Now that I'm through playing the engineering 👨‍🍼 Dad, let's get back to the point.**

When you start exceeding thousands of lines in code, not only is your code elongating but so is the time that passes in real life as well.

*What do you think you're some magical wizard who just writes thousands of lines of **good code** every day? Okay, 🧚 Peter Pan, you don't exist.*

As time persists, we forget things; we're human, it happens. You're not going to be able to remember every function and line of code you've ever written. Surely there may be instances where you'll have cloudy or even vivid memories of code that you've previously written; but as the code grows larger, becomes more complicated, and is referenced less frequently, those memories will slowly get lost and fade away.

Once those 🧠 memories have faded, what then happens when you need to use that forgotten code again? With or without some trace of it in your memory, you may go looking for it. What if you can't find it? What if you can find it, but there's so much digging involved that you give up the search before you do? *You already know the answer, before I even tell you. You'll have just successfully replicated the same code over again!*

**A real-world example.**

I was working on a project with another programmer about 5 years ago and the documentation was scarce (to put it nicely). By the time we got to the point where we wanted to launch, we pulled a code review on ourselves and the results were surprising.

We had come to find out that we wrote the same functions, with our own unique twist, in a number of different areas throughout the project. We were coding at a fast pace and without any detailed documentation, our only means of finding code was by performing a quick 🕵 search/grep throughout the project. If the search/grep yielded no results, we just went ahead and moved forward by writing the function that was needed from scratch. Had we maintained some sort of code documentation, we not only would've found the functions that we did find a lot quicker but the code replication issues could've been avoided altogether.

**To sum up the point that I'm making. Comment your code with keywords and phrases.** If you perform a search for a chunk of code you're looking for, and you wind up having to dig to find it, when you do find it, add your search phrases and the keywords that would've gotten you there immediately. This is not only for your benefit but for the benefit of anyone else who is working on the project along with you!

---

![](https://tvline.com/wp-content/uploads/2020/10/the-simpsons-video-election-homer-voting.png)

## Fingerprints In Code

You know how when you touch a piece of glass you leave your fingerprints on it? You do the same thing in programming when you write code.

There's a guy I've been working with for about 7 years now, and I'm able to 🔦 spot his code from 100 lines away. Even when following a strictly specified standard, the code is still fingerprinted.

**Here goes an example to better illustrate what I'm talking about when it comes to fingerprints in code:**

*📗 I may write a line of code that looks like this:*

```javascript
var dbConnection = new DB.connect();
```

*📘 ...someone else may write a line of code that looks like this:*

```javascript
var dbConn = new DB.connect();
```

*📙 ...and someone else may write a line of code that looks like this:*

```javascript
var dbConnect = new DB.connect();
```

I could go on a tangent into a whole other debate about naming conventions along with mandating extremely strict coding standards *(which I'm all for)*, but that's just *not reality!* When it comes to the majority of programming jobs in the current marketplace, you'll find this to be true.

**What are the benefits?**

1. ✍️ **You can immediately look at the code and know who wrote it whether it's documented or not.**
Obviously, this has a number of benefits such as knowing who to get in touch with if you're having issues with the code in question.

2. ⏳️ **It's a time saver when it comes to diagnosing problems and patching.**
Sometimes performing a code annotation isn't enough. John Doe may have written Line 10 which is causing a problem, but Jane Doe refactored Lines 1-9 and 11-20 which caused Line 10 to produce a bug.

3. 🎓 **Learning from your peers.**
Say there's a rockstar coder you work with and he codes something in a particular way that is unbeknownst to you. He may be coding that way because it's actually a well-thought-out technique that you're missing out on. Putting your ego aside; how hard is it to say to them: "Hey, why are you coding X like this?" and learn something you may've been missing out on?

4. 👨‍🏫️ **Teaching your peers.**
Let's flip #3 Learning From Your Peers that we just listed above. You're the rockstar coder, and you notice a colleague is coding in such a manner that you deem poorly. Educate them by showing them your techniques.

---

## Hiring New People

![](/img/post-assets/2014-06-12-why-to-document-your-code/Bart_vs._Itchy_and_Scratchy.png)

If you've ever been involved in the hiring process or ever plan to be, this should be a ⛳ **major red flag** for you.

Let's say you hire this new guy, his resume/portfolio is great, you manually test him and he passes with flying colors; maybe even exceeds the desired expectations.

A week later you hire and put him on the project to do what you had originally hired him for. The project in question has barely any documentation. Now, what's going to happen?

**Say hello to your newly hired programmers 🐭 pest!**

This guy will be over your shoulder every chance he gets! He will be sprinting back and forth between his and your desk asking for help like he was the Silicon Valley 🏃 Magic Johnson going for the gold!

**Can you really fault him though? You can't.**

You'd really expect this newcomer to learn your project's code with no documentation, without having to pull out your 🚼 baby stroller? Of course, everyone needs a few weeks or more to ramp up, but by not having any thorough documentation in place, you'll have successfully prolonged the process indefinitely.

**Without documentation:**

You'll double the time it's going to take for the newcomer to become a real native of the project.

You'll have ♿ handicapped your veterans on the project by forcing them to hold this newcomer's hand for an even longer period of time.

---

## Looking Back

I hope this article gave you some incentive to better document your code, in the case that you're not doing so already.

**Key benefits that we covered:**

- Dealing with a growing project for the long haul.
- Using keywords and phrases to easily find snippets of code.
- Avoiding code replication.
- Learning from your peers.
- Saving time and money when hiring new people.
