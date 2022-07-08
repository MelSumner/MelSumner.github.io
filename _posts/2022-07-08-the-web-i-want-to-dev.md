---
layout: post
title: "The Web I Want(ed) To Dev"
slug: the-web-i-want
updated: 2022-07-08
---

If you're unfamiliar with me, or my work, there's a good chance you won't automatically grok the context for the work that I do. You might even be tempted to find me [on Twitter](https://twitter.com/a11yMel) and tell me how wrong I am about any number of things that I have written. Or if I was a _real_ developer I wouldn't have been okay with leaving _something_ out. But the truth is, the reality of the work we do as web developers is much different that then work we _wish_ we did as web developers. So for now, let's dream a little.

<!--more-->

I still smile when my code builds properly and is published to the web. It brings me genuine joy to bring something new to life, to create a new place of information or utility that wasn't there before. I love caring for that project so it can live on. I love it when someone asks me if they can contribute to one of my open-source projects. These things are probably what gets me through the really tough parts of working in tech and specializing in accessibility. It brings me a lot of joy to create things for the web; I get to do the thing that I love doing every day and I'm so grateful for that.

But, I have also mostly worked for enterprise companies throughout my career. My focus, especially early in my career, was on dependably providing for myself without help. But when I saw the churning waters of startups I knew that I was not that kind of gambler. Enterprise companies are kind of dull by comparison-- there is no free food, no beer kegs, no pool tables-- but there is more stability. That's what I wanted. Stability. The benefits are usually pretty good, too. There might even be retirement matching. There are rules and I can use those rules to succeed, because the technicalities of the rules matter. 

However, there is also not a whole lot in the way of excitement. There are also no bespoke, well-crafted artisan websites here. No one will win awards for this work. In fact, most will not want to admit that they were even associated with it. The code of the everyday in enterprise environments is, realistically, something more like: 

* cleaning up old code to meet legal requirements
* adding new designs to old code 
* getting the content from the CMS that the admins use and render it to a page and also pls support IE.
* trying to change all the underlying code so the user has no idea that anything has happened. Steve (Steve has forever been the name of the random person at work who makes your work life suck because the first person I encountered who made work suck was named Steve; sorry to all good Steves out there) is now satisfied that he has drastically improved things for the company by insisting we all switch to the hot new thing (Narrator: he didn't. He also left shortly after the project was finished, having convinced his new company that he was an amazing 10x developer at his old company).
* trying to build a new thing that is somehow both seamlessly compatible with the old thing and also solves all the problems of the old thing (the reason the new thing was needed in the first place)
* negotiating for every single drop of accessibility in the design and code, even if it's a legal requirement

Ok, I'll stop now. You get the idea. The thing is, even if the job is harsh or boring, the work is still mostly amazing because it's problem solving for the web. It's just...not the kind of problem solving that we _dream_ about doing as web developers/software engineers. 

So what _do_ we dream of? I once bought the url thewebwewantto.dev because I had a vision of a well-crafted site that laid it all out in an accessible, beautifully designed, easy-to-understand way. Yeah, that didn't happen. Life happened instead. While I can't pretend to know what all web developers dreamed of, I can tell you about the web I wanted to dev. 

I probably should categorize these neatly but I'm trying to overcome the tendencies that keep me from shipping things. So today, I'm just going to make a long list. Perhaps it'll motivate me to update the post and categorize each item and make neater lists. Either way, the perfect will not be the enemy of the good, at least not today.


Without futher ado, here are the characteristics of the web I want(ed) to dev:

* Development is always done in a response and "mobile-first" way
* design tools support relative units
* websites support use on all types of devices because doing it any other way would be bananas
* HTML validation is built in to the right places in our tooling
* All content is contained within landmark elements
* There are not a bajillion wrapper divs
* There are not so many DOM elements on the page that it crashes someone's screen reader
* CSS properties are alphabetized
* CSS is named in the noun-then-adjective way
* Design tokens are used
* JS classes are also named logically; they start with is/has if they're a boolean (or sometimes another verb if appropriate), and they can have long names if that's how you describe what it actually does
* No need to support both required _and_ optional; consistent experience is consistent
* There are tests. Maybe it's even test driven development. Maybe it's just sensible tests. Maybe it even includes some funny tests that make you smile a little bit because they're funny.
* There are definitely accessibility tests so if someone else tries to change the code and removes the important accessibility thing, the test will fail
* There are comments in the code, and some of them are funny. None of them are "if you remove this line of code the whole thing breaks but I don't know why"
* There is documentation that is sensible. It has a TL;DR at the top that tells users how to do the thing that 99% of users will need to do, and tucks the in-depth stuff away in a manner that is easy to get to when they need it, but doesn't overwhelm them if they don't.
* Everyone working on it knows how to use, at the very least, the screen reader native to their OS
* There are no PMs asking for "just give me any estimate, I need it to fill out this sheet, it doesn't matter if it's accurate"
* No one cares if I rebase or merge, they're basically mostly the same thing in these kinds of situations
* No one is trying to teach me VIM or EMACs or even mentioning either of them, because no one cares what IDE you use, only that you're content and productive while using it
* CSS is done consistently. Add all the utility classes to the HTML element. Put all of CSS for the element into a single class in the stylesheet. Pick one.
* There are no mixins in the CSS. Actually mixins are banned from all existence.
* There's a pre-defined project structure and Steve doesn't get to change it per project based on his personal preferences or mood that day.
* There are no "nit" comments in code reviews
* Table elements are used for tabular data and that's it. The rows are not interactive. It is not `canvas` based.
* Infinite scroll is not used. Ever.
* Everyone recognized that the web is global so everything is internationalized.
* It is generally well-accepted that if you want to render 10,000 of ANYTHING to a page, it will be slow.
* It is generally well-accepted that you can optimize the underlying code all you want to, but if the front-end UI developers are writing slow code or uploading large images, you're still going to have a bad time.
* No one tries to "get around" accessibility requirements.
* No one suggests a text-only version of the site for screen-reader users.
* There are no "waivers" for failing WCAG success criteria, the issues are addressed and fixed promptly
* Issues are prioritized by impact to the user
* Some portion of everyone's time is spent working on open source
* None of the CSS ends up in the JS
* All of the designers are on board with accessibility, especially when it comes to color contrast
* Those who write code, also write the tests for that code and the docs for that code
* There are no expectations that it will look or behave exactly the same on every single browser and device combination
* The words "pixel perfect" are never uttered
* There's a sensible device-testing lab
* There is visual regression testing
* There is user research
* Users are paid to participate in research and testing.
* No one can push to the main branch of the repo. No one. Not even Steve.
* Deployment pipelines are configured to do all of the tedious stuff automatically
* Ads cannot be added to the site/app if they do not meet a quality and performance threshold.
* There is a limit to how many ads can be on a page because we all recognize that there is an appropriate content-to-ad ratio (and whatever the fuck is happening right now on the internet is not it)
* Zero design decisions are made for the purpose of tricking the user into performing some action
* There is version control that is realistic and takes the users into consideration, because everyone recognizes that it's not about tricking the semver system but rather about communicating intent to the user
* There are realistic metrics about things that really matter
* When team members come back from a conference and are really excited about something they learned, the team figures out if it's a good fit for the project and puts it on the roadmap if so
* There's a useful roadmap and its regularly viewed to keep everyone aligned on where we already decided to go
* Browser resets are not needed because the browsers aligned and decided to all start from the same point and give developers just a little bit of a break
* It's possible to style all form elements with CSS
* If a browser decides to make a thing that other browsers don't want to make, they also make a polyfill that devs can use because they recognize the importance of accessibility across all browsers
* There are no "this site works best on X browser" because we have all agreed that was mean and shitty thing to do
* Tech and web awards shows exist and are for the people who actually build things for the web
* Typescript is folded into JavaScript and made simpler and just the way it is, there's no "picking" which one you will use.
* The Steves will stop increasing the barrier to entry, stop protecting their own jobs by making web development increasingly complex that only they know how to do a thing. There will be at least two people who can do each thing that is essential to the life of the application.
* All spec groups stopped shipping new features & fixed the not accessible things they shipped. Web 3 is about a fair and equitable web experience instead of parting fools with their money.
* All web developers have to take web history because everyone recognized that no one enjoys having some young dev, who somehow has the job title of "senior software engineer", talk about their hot new idea that is really something that was tried 20 years ago and discarded as a terrible idea for many reasons
* Some sort of sensible approach to dependency management that I can't even fathom because it doesn't exist yet. But like, left-pad-guy should not have been able to take out so many sites.
* If a new feature is not accessible, it does not ship.

Anyway. Enough about me. What web did _you_ want to dev?

Until next time. -M
