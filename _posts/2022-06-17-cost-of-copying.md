---
layout: post
title:  "The Cost of Copying Design"
slug: cost-of-copying
---

They say that you can tell an experienced developer because when you ask them a question about how they would approach or solve a specific problem, their answer will be "it depends." These days, if a designer were to ask me if it would be okay to design a component in a certain way (_"just like Twizonple does it"_), my response is probably going to be "I'll look at it, but it's unlikely since they are well-known for inaccessible design. Out of curiosity, what features do you like best about it?"

<!--more-->

It's likely that Twizonple has implemented something that does not conform to accessibility-related specifications, the whys of which I will probably wax philosophical about at some point, but today is not that day. 

The challenges that come after saying "I'm so sorry, but we can't, it's not accessible", then, are two-fold: 

1. The annoyed colleague. Super-mega-famous tech company does it so it should be okay for us to do it too, and why are you being so stubborn about accessibility, can't you just be more flexible?!
2. Users are "trained" more and more on these Twizonple sites simply through frequent usage. So if you've done something different, you might have to then provide more support so your users know how to work with _your_ site (even if it's correct).

Lately, however, it's been super useful for me to ask "what features do you like best about it," because that gives me something to work with. We can review the component (that already exists) and talk about what accessibility issues it might have. For example, what if they have elements that are made to appear on mouse hover, but not appear if the user is navigating with only a keyboard? Not only is it a failure of the [Keyboard WCAG Success Criteria](https://www.w3.org/WAI/WCAG21/Understanding/keyboard.html), but it will actively train users to expect the poorer user experience and replace their definition of what "default behavior" should be. Spending a little extra time to evaluate the desired pattern and if possible, improve it for accessibility, seems like the right amount of collaboration. A good solution solves for all of the criteria; if your solution doesn't, then you haven't finished designing the right solution yet (and that's okay)! 


## Action Steps to Address the Root Cause

This poor UX design increases the cost of copying patterns from other sites increasingly expensive. For years we've been telling developers and designers to "try to stick to patterns that users already know," because it lowers the user's cognitive burden of learning a new thing or trying to remember how this thing is different from other things. But if there is no way to figure out who is reliable to copy from, who is mostly reliable with some tweaks, and who should be avoided entirely?

For every way a developer wants to implement a component, there will be an example on someone else's website. For every opinion about how design and development (even accessibility) should work, there is a blog post or conference talk that extols the approach and argues that it is "the way." Now, logic dictates that we cannot all have opposing views and also have all of those views be correct, so what should we do here? It seems as though the audit/evaluation phase of design has just ballooned astronomically through virtue of choice. 

As our career advances, our experience becomes intuition, and our lived experience will help cut through the proverbial noise to find the signal, but is there something more we can do?

I think there is. I think we can start by recognizing that whatever it is your team is building, there is nuance there and needs that must be considered. So let's make an evaluation reference guide. 

Here are some action steps for what that kind of guide might look like:

1. start an internal document (or a secret society, but for now let's assume an internal doc is the more acceptable path forward)
2. have a team conversation about what sites, design systems, conference speakers, and bloggers they like and regularly use
3. evaluate the sites and design systems for accessibility and separate them into three buckets: use, use with mitigation, avoid. 
4. evaluate the third-party libraries as use or avoid (note that we're not including "use with mitigation" here-- it's WCAG conformant or it is not), and especially if it is avoid, **include reasons such as what WCAG Success Criteria it fails, and how that failure impacts the user.**
5. for content creators such as speakers and authors: try to stick to technical accuracy and long-term value, and to avoid personal preferences when it comes to delivery. Who has consistently delivered standards-conformant, practical advice? Who accepts feedback and integrates it into their speaking or writing? This is only something time can tell, but as your team grows in experience, this list will grow for you too. 

### Examining Bias

I want to take an extra minute to talk about that last point about evaluating speakers and authors, because it deserves additional clarification. This is **not** about any speaker or author who uses their position to abuse others (in any way). It _is_ about rising above our potential biases (sometimes disguised as personal preferences) to focus on the best outcome for our users. 

**Example:** the very-gruff-but-always-accurate accessibility expert 

* Incorrect: "They need to say this in a nicer way if they want me to listen to them."  
* Correct: "They are a bit gruff, but maybe they've had to be in this industry. From a technical perspective, their advice checks out and is factually accurate.

**Example:** The hyper-religious-yet-technically-detailed design expert

* Incorrect: "They are so religious, I can't take them seriously."
* Correct: "They don't push their beliefs on others or try to control others through their beliefs, so it's none of my concern. From a technical perspective, their advice checks out and is factually accurate."

> It is in our best interest to focus on outcomes for our product and our users, which means we need to be able to hear _what_ they are saying and not tone police who is saying it or _how_ they are saying it. We can succeed when we choose to look past whatever biases we have (we all have some, I'm sorry to tell you that) and pay close attention to the technical message.    

## Conclusion

Ok, back to the list. The list should be relevant to your team and what your team is building. That's why I'm not advocating for this list to be in a book or on a website or anything like that. There is no one-size-fits-all here, nor should there be (also perhaps another article for another day).

I want to specifically note that these lists (design systems, sites, authors, etc) should be kept pretty short; you're not trying to evaluate absolutely everyone for everything. This document becomes the _example_ for how to evaluate a reference or resource for the scope of your product and the needs of your team. It gives examples of things to be on the lookout for. By providing this resource to our teams, we can become a force-multiplier since teams can then learn how to give their own evaluations and provide the same types of examples. We participate in our own success, instead of accepting the defeatist mindset of "everyone else does it" or worse, [not-invented-here (NIH) syndrome](https://en.wikipedia.org/wiki/Not_invented_here).

There will always be some cost associated with copying design, but it does not have to be so catastrophic as to be avoided all together. With some sensible and relevant guidance in place, we can improve both our internal process and our personal craft. Seems like a win-win!
