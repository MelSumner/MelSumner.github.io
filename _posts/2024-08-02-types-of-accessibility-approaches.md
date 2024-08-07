---
layout: post
posttitle:  Approaches to Accessibility and Other Things
slug: types-of-accessibility-approaches
updated: 2024-08-07
---

_Some context: This blog piece is really me unpacking some emotional stuff. I know! Feelings! In a tech blog? No way! But seriously, maybe it will help you too, though. If not, that's totally fine...YMMV._

Yesterday, I was in a discussion about an accessibility-related technical issue, and a person in the discussion said something along the lines of "I don't understand how you can't empathize with the user here." TBQH, my brain...broke.

I wanted to laugh/scream/cry because isn't that _why_ I do what I do? I choose to continue in a technical niche that also happens to have a great deal of emotional labor attached. Their comment felt like an attempt at emotional manipulation, and I reject that.

Web development is a field where I have had to supress my sense of urgency that we're not doing enough to create an inclusive web. I can't talk about my feelings, or the human rights we're dealing with here, because "we're engineers and we're technical." I cannot speak passionately about the people who rely on us to write better code because our lives are increasingly online, and we're taking away any chance they have at independence (the same independence we insist on!) when we get it wrong. I have spent so much time trying to figure out how to reasonably, and unemotionally, present practical guidance web developers just so they won't feel criticized and reject the guidance I'm trying to give them. Forreal. 

In this particular case, my issue was with  the technical approach used to solve the issue for the end user. I am not okay with solutions that break technical requirements. I think the technical requirements should be changed _first_, because that's where we get to consider the existing requirements while trying to write new ones. It was the technical approach that I had an issue with, not the user feedback.

Now, since it is very clear to me, but sometimes not so clear to others, I'll just say it out loud: I want the outcome of an inclusive user experience. I want an accessible web. I want a consistent, testable, reliable set of Specs for the web. I want genuine equality, not solutions that will fall down when the wind changes. 

Yeah, so, I was a _bit_ miffed. 

In a totally different conversation, it came up that I parent in a specific way because I only have one child, and that if I had more children there are a lot of things I'd do differently, probably. The TL;DR is that I have more of a meta parenting approach (the concept, not the company); I want my son to understand the underlying concept and not just tell him what to do in any given situation. I am his guide and his guardian, not his owner. I save direct instructions for instances where he may be physically harmed. There are _definitely_ tradeoffs to this approach. As a side note, I also acknowledge that it may be entirely possible for _other_ people to have multiple children and also use this approach, but I was not confident that I could be one of those people, and chose accordingly.

Last night, when I was unpacking my day mentally, another parallel came to mind: the decisions we make about web applications. There are differing priorities and approaches for small apps vs. apps that have to think about scale. 

It was really only then that I was fully able to de-personalize the perceived insult. I started thinking through the kinds of accessibility approaches that different types of people I've encountered in this line of work.

## Types of accessibility specialists

Before I get into the types I've thought about, I'm very a woman and very online, so I will preempt any criticism with this disclaimer: this is where I am at right now. and I completely reserve the right to change my mind if I receive additional information that updates my worldview. It is fine if you disagree with me. I do not reflect anyone else's opinion except my own. I think this should cover it.

In no particular order, this is the list I'm thinking about.

* The Everything Specialist. This type genuinely seems to know every bit of Spec that has ever been written. It's really impressive. They are also aware of all the different types assistive technologies that could possibly be used, and are a gold mine for things that developers and designers have done incorrectly since the beginning of time.
  * Some of these types are a dependable source of information and dispense it often, and with kindess. 
  * Some of these types...not so much. They don't really _do_ nuance, or practicality. They will let you know that you're wrong in the "fuck-your-feelings" kind of way. 
* The Compliance Specialist. They will have all of the clever tricks that tell you how to make the thing you are doing pass the Success Criterion.
  * In this category, there is the sub-category where folks can get so focused on what the rules permit or do not permit, and the forest can get lost for the proverbial trees. This is a very frustrating group to work with as the focus is often on "is that disallowed? If not, don't care about it." This might be an emotional protection mechanism in a very "care about the things I can control" kind of way, but I am not sure this has the best outcome in the end.
* The Theorist. This type can theorize until the end of time about how things should be done, but how they can't be done because of these 25 other ways it could be misinterpreted or used incorrectly.
  * Sub-type: Safer to do nothing. They can talk everyone into an idea, and in the same conversation, talk everyone back out of that same idea. Don't move anything. It will break something. In theory.
  * Sub-type: There are some gaps, but they can still act. They can identify gaps in an idea from a theoretical perspective, but still be pragmatic about action steps that can be taken to move an idea forward.
* The Accessibility Anarchist. There are folks that think the users' needs should be put above all else...including Spec. They are totally fine with breaking Spec to implement the solution they think resolves what their users have said they want.
  * Sub-type: would only do this in their own app. 
  * Sub-type: (some) browser vendors. 


**Warning: Strong opinions ahead**

The Accessibility Anarchist, particularly when they bear the responsibility of being a browser vendor, is the most frustrating of all categories for me. They are creating a false justice. It creates a rift between folks who depend on the Spec as a source of truth. It creates a distrust in the Spec. It creates a scenario where, instead of the Spec saying "this is how it should work", the browser vendor is saying "this is how Spec should work." It's no longer a collaborative, consensus-driven decision; it's a decision by a select few, behind closed doors and THIS IS VERY BAD for the web _at large_. 

However, browser venders _in general_ have a history of adding exceptions for their own best interests, usually business resons. And, as it turns out, sometimes the lack of specification clarity allows them to have varying interpretations, and they sometimes refuse to make a change because it would be too costly and ineffecient.

Additionally, it's important to recognize that Specs have a history of moving slowly (too slowly, some may argue). 

WE MUST RECOGNIZE THAT THIS HAS LEGAL IMPLICATIONS. How can a browser just _refuse_ to make a change based on clarification from the Spec authors? I'm more than a little concerned that this giant mess is going to lead to some sticky legal situations, and in the end, we haven't actually provided equality for users.

This is keeping me up at night right now.

Ok, back to our normally scheduled programming. 
There may be other types that exist, these four (and their sub-types) are how I'm sorting things through right now. Well, I know for sure there are other types not included here, because I haven't even figured out which one I am, or how my own guidance fits into all of this. 

We're really fucking up on the bigger picture. Big time. 

## Urgent and Important already exists

There are existing challenges that are urgent and important. 

* The places where the various Specifications conflict with each other...or themselves.
* The lack of clarity _in general_. So many things are too vague. Requests for clarification go nowhere.
* The general air of "well, we can't _say_ that, because there are lots of BigTechCo websites that already _do_ that, and it would really break them." Lord forbid.
* A sense of hopelessness that we can't definitely say "do it this way", not in any official capacity that would matter to the web at large.
* The perception that no two accessibility Spec authors agree on any given topic, so why include any accessibility folks in the creation of other Specs? 

Y'all, the web is in a _not great_ place right now. Some will argue that it really never has been, but this is a precarious time because it feels like we've collectively given up somehow. Tech execs have decided to try to fix this with AI instead of the long-term strategic initiatives that would improve the web for everyone. 

Let's keep pushing ourselves to not give up and figure out solutions that work for everyone. America itself is a rather exemplary example of what happens when a few folks decide to implement solutions _for everyone_, but it really only works _for those few_. We know it's not working. We _could actually_ learn from this. 

I think we have to believe that we both deserve better, and can achieve better.

Until next time. -M
