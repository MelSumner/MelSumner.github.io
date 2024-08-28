---
layout: post
title: "Reasonable WCAG Additions"
slug: reasonable-wcag-additions
updated: 2024-02-14
---

I've been reading the WCAG Success Criteria on a nearly-daily basis for...well, for a really long time now, and I have come to the opinion that some no-nonsense, reasonable additions would be useful. Note that all of these are based on my own personal experience and don't reflect anyone else's opinions but my own, unless they share this blog post with you and tell you that they explicitly think these things are a good idea. Which they are, of course.

I'm also grateful for WCAG Success Criterion [1.3.1 Information and Relationships](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships) because it covers a multitude of sins, BUT I dream of a little more clarity, a little more guidance, a little more explicit "lolno quit that."

## Heading Level Order

Right now, this is just considered a "best practice" but really, everyone benefits from well-organized content that puts the heading levels in order. This is something we have had to do since we were kids in school, writing book report outlines and such. Surely we can be expected to produce content in a reasonable manner as adults.

Use the same kind of heading order like you would in a document, and use CSS for styling. That's it. No exceptions. Just do it.

## No Tables for Layout

Forget adding `role="presentation"` to your table element that you used for layout. It's 2024 and we have all kinds of ways to easily and evenly lay out content on a page with CSS. Promise. I know we can't break the web by introducing rules that would make existing content non-conformant, but we can add "effective from" dates to these things, really. Imagine never changing laws because "well it used to be legal and people might still be using it." lolno. 

## No Toasts for Errors

Look, toasts are clever or whatever, but those little boxes pop up, say their thing and then disappear. When you put error messages in them, how the heck am I supposed to read the message fast enough, figure out what it means, figure out what field it belongs to, and figure out how to fix it? That's asking way too much. Put the error message by the input field where the error actually happened.

## No Nested Interactive Elements

No nested interactive elements. Ever. Not ever. No exceptions. Stop doing this. I never know if the thing I'm about to click on will do that or do something else entirely. Jira does this and it drives me up the wall, and I even _like_ Jira. But I hate that I can't trust it to do the same thing every time. I never really know what's going to happen. A user should KNOW WHAT WILL HAPPEN AND BE ABLE TO TRUST YOU. I know there are other WCAG SC's that technically provide this coverage, but it's time for us to say this out loud and in unison.

## Links are for URLs, Buttons are for...not that

If it goes to a URL, it should be a `<a href="your-url-here">` kind of situation. If it's a toggle, or action, or...really anything that doesn't go a URL, then it's a `button`. Stop fucking with users. Again, users must be able to trust that the thing that looks like a link is actually a link. I know designers have kind of eroded user trust over the years but I'm fed up with it. It's time we take it back and things need to be what they are, especially because they are asking for the user's trust.


I think I will add more to this list later, but I have an accessibility audit to get back to.

Until next time -M

P.S. I see that my blog is not compiling the title correctly (automatically using title case instead of respecting what I've indicated should be in all caps via content). It's a bug. 
