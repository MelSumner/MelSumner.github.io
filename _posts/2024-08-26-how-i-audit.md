---
layout: post
title:  "How I audit"
slug: how-i-audit
---

I really, really, REALLY hate accessibility audits.

Okay, maybe I should clarify. I really really REALLY hate getting generic accessibility audit reports that companies pay a lot of money for but don't produce useful results.

Maybe I should explain.

So when my place of employment (at the time of this writing) was asking, "hey some customer asked for a thing called a VPAT, do you know what that is?" I was really interested at the opportunity to weigh in.

Okay, so I've ended up doing the audits for our public accessibility conformance reports(ACRs); while it's not as satisfying as writing new linting rules, strategizing about [Continuous Accessibility](https://continuousaccessibility.com/), or crafting new design system components that are accessible and have great documentation, it has been satisfying because I've been able to undo some of the irritations I've experienced in the past.

## Why I dislike them

My primary gripes are maybe probably everyone's gripes.

1. Duplicate issues
2. Nonsense reports
3. Inclusion of personal preferences over WCAG Success Criterion
4. Non-reproducible issues
5. Lack of internal access for all employees

### Duplicate issues

When you're building apps that scale, you're probably using some kind of framework with reusable components. I work at places that do this because I enjoy working with Ember, the OG of awesome, reusable components. The testing ground for "here's what web components could look like." Also the reason I haven't learned web components yet, I enjoy Ember components already. But I digress.

It's super frustrating to get duplicate issues when the issue is like, the accessible name of a button, and that damn button is on every.single.page. I think I might have developed RSI over the years just from closing issues as duplicates. UNGH. If you file issues, _try_ not to do this. I know it means a little more work (especially if you don't understand reusable components), and we all mess this up even when we don't mean to. But try.

### Nonsense reports

I got a report recently, and it was definitely not reviewed by a human that needed to implement anything, ever. Include where you found the issue. How to reproduce the issue. How to fix or even just _suggestions_ for how to fix if you're not brave. That's okay too. But for the sake of everything that is good in the world, stop sending reports that are some vague IYKYK reports with some WCAG numbers and issue counts. You're not helping anyone do better, here.

### Inclusion of personal preferences

I know. I KNOW. This one is hard. It's soooo tempting to be like, "I expected THIS and didn't get it," but unless you can tie the issue to a WCAG reference in a believable way, just leave it out.

### Non-reproducible issues

We all have that thing that happened to us that one time, and no matter what it's not reproducible. It was probably a race condition. I'm convinced that most non-reproducible issues are race conditions. But the thing is, you have to include what was happening when the issue occurred. What workflow/page were you testing? What browser and AT were you using? What version of the OS? 

If that information isn't there, then WTAF is someone supposed to do? I tell you what I will do, I will check it with the combination I have up right now and then close it with a "cannot reproduce" if that information isn't there.

### Lack of internal access

Once you get reporting set up, then anyone with a login at your company should be able to access it. It shouldn't just be for a single team or single person to view. Everyone needs to be able to see it. Create a short link to it so it's easy to remember. Regularly mention it in chat. Reference it in emails. Make it the place people go to see the numbers and see the progress.

Then you can all celebrate your wins!

Here's the thing. Auditing isn't easy even if you've been doing it for a long time. There's always nuance. There's always the need to know how the app was designed to be used. This is the reason it's good to have internal accessibility experts do the audits.

The other thing is, though, that the human brain is really, really good at rationalizing things. It's been important for our survival and such. But it also means that you might not always be able to see the faults right under your own nose. This is the reason it's good to have external accessibility experts do your audits.

Tricky.

Now, I don't drink Koolaide. It's too sweet for me. I like getting a paycheck, but I also strongly believe that I need to be the expert I was hired to be. This is why I'm a pretty good person to have on board and have doing some audits. I'm pragmatic but I'll push us to do better, and I understand our applications.

So, there are tradeoffs.

## Writing good issues

The other convenient thing about having an internal auditor? I can file an internal issue when I find a problem. When I do, here are the things I include.

1. Summary. This gives a short description of the issue.
2. Screenshot(s). I use Cleanshot X and annotate screenshots when I can. I'll try to include not only what's rendered to the browser, but also what's in the code.
3. How to fix. I'll provide some suggestions for how to fix the issue, especially if there's a design system component that would resolve the issue. But I also make sure to include that other solutions might be viable, and offer to review it if they want me to. I don't want anyone to feel like I'm hampering their creativity, but rather that I'm supporting their success.
4. Other details: What workflow was I in when I found the issue? What test method was I using (so they can reproduce)? What's the impact to the user? Finally, I provide links to any WCAG references that might be relevant to the issue.

I also update issues if I know that a "new" issue I have found is simply another invocation of a component that already has an issue. I'll indicate in the issue that it was found in multiple places. This is useful for the "fix it once, fix it everywhere" kind of components that tend to be in Ember apps, but also informs the developers that if they have different versions of the component, they need to think about that.

The benefits of having a consistent system? Well, developers and designers get used to them when they are done consistently. It's easier to read something when you're familiar with the way it's laid out. Also, it gives other folks something to copy internally, and gives me the confidence that even on days when I'm not at work (what sometimes I take days off), that others can also file issues.

I've also worked out a consistent labeling system, so we can use the system itself to generate reports...that anyone in the company can access. When we all can see what is going on, we can all plan to do better. 

Until next time. -M
