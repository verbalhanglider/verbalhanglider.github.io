---
layout: post
title:  "Containers vs Culture"
date:   2018-03-30 10:30:44 -0500
categories: containers organization-culture
---

> I'm willing to bet that all the janky bash ever written was meant to solve a real problem. When we start getting fancier, there are often motivations less pure than "Let's do this well," and even if there are not, intention alone does not create maintainable software.

-- Bridget Krumhout,  _Containers Will Not Fix Your Broken Culture (and Other Hard Truths)_ April 2018.

This month's [CACM](https://www.cacm.acm.org) has devoted the Practice section to discussing DevOps, and in there is a really good article called [_Containers Will Not Fix Your Broken Culture (and Other Hard Truths)_](https://cacm.acm.org/magazines/2018/4/226368-containers-will-not-fix-your-broken-culture-and-other-hard-truths/fulltext) by [Bridget Kromhout](https://twitter.com/bridgetkromhoutref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor).

It's full of lots of great metaphors tips like:

> Creative problem solvers have a way of routing around process that we find inconvenient. If your heavyweight change control process applies except in case of emergencies, then (spoiler alert) you are going to see a surprisingly high rate of sorry-not-sorry "emergencies."

And:

> Empowering developer choice is facilitated by containers; there is always a tension between what someone else dictates and what you are convinced you need. Making thoughtful decisions about tools and architecture can help; well-considered constraints can free us from the decisions that are not bringing us distinguishable benefit. Containers can help define scope and reach of a given tool or project, and deconstructing systems to human scale allows us to comprehend their complexity.

And, finally, she gets to the heart of the matter

> ...it's worth considering the why and how of our behaviors, not just the what. If legacy were not important, you could just turn it off. But this is where your customers and money live. Glorifying exciting greenfield projects is all well and good, but the reality is that bimodal IT is a lie. It's ludicrous to tell people that some of them have to stay in "sad mode" indefinitely, while others catapult ahead in "awesome mode."

It all comes down to the old adage: there is no free lunch. Technical solutions are no good at all without very careful planning and lots and lots and lots of talking back and forth between all the parties involved in an organization (all the different kinds of business people in all the different divisions and departments as well as the IT workers and developers). You have to get people talking and talking honestly otherwise whatever technical solution you come up with is going to fail and fail in the worst way not with a boom but with a fizzle.