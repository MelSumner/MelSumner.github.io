---
layout: post
title:  "Understanding AccName: Part One"
slug: understanding-accname-part-one
---

Before we begin, some disclaimers and other things of note: 

1. While I am, at the time of this original post, one of the co-editors for the [Accessible Name and Description Computation](https://w3c.github.io/accname/) specification, this does not mean that I am a comprehensive authority on the topic. I am the co-editor because at the time, another editor was needed and I stepped up. I learn more _all the time_.
2. There will be some swearing in this series, so tune out if you don't have a browser extension that changes "swear" words to something else, or you haven't taught your kids how to properly swear yet and they are sitting beside you.
3. I am working on the accessibility of my blog, the code theme doesn't have enough color contrast in some cases, and on smaller viewports it may be difficult to scroll horizontally. They are known issues and I apologize for the inconvenience.

---

"I just don't understand the AccName spec. It's too confusing."

I felt a little sad when a developer said this to me, but I also empathized. I know what they mean. I meant to write a blog post back then...but you know, life. But _then_ I was watching someone's conference talk video, and they were sharing some information about AccName and I thought, "oh dear, that's not what I want developers to know."

So here I am, and I'm going to try to get down some thoughts and examples, and see if I can make AccName a little more approachable for developers. If I come across new information or someone provides factually accurate correction, I will update the post to reflect that.

## Implementors vs Authors

Now, the first thing to understand about the specification is that it is focused on outlining what implementors (aka browsers) should do. And, as it turns out, that is kind of the _opposite_ of what authors (aka developers) should do when thinking about the accessible name or description of an element.

I know. I know! But if you think about how you'd write an algorithm, it...makes sense.

The other thing to do know about the specification is this: Browsers need funding to be implemented, right? So the person who pays the bill can and sometimes does influence what gets paid for and what doesn't. The same goes for assistive tech like screen readers, too. It's all a matter of priorities, time, and energy. And those do not always align with what the spec outlines as "how things _should_ work". 

In some cases, editors may even update the specification to outline _the way things really are_ instead as the most pragmatic choice. But this can leave authors (developers) really confused about what to actually do!

## Mel's rules for accessible names

Okay so, I'm saying "Mel's rules" because maybe there are people who don't agree with me, or understand the spec differently than me, or I am just trying to guard myself from the kind of pompous criticism that I get online sometimes. I will say that this is how I have mostly been doing things for 27+ years and it's served me pretty well, so take that as you will.

Here's how I was taught:

1. HTML is for semantic/meaningful content
2. CSS is for visual presentation
3. JS is for functionality
4. ARIA is for accessibility in the places where there are gaps that are not otherwise provided for

While these are not _exactly_ the rules today (nuance builds up over time), this approach will still mostly serve you well as a developer. I'll even tell you this for free: the web would be a much better place if we had just stuck with these rules. We would have less complexity to deal with, and less bloated code as a result. There's a saying in the South, "it's like reaching around your neck to scratch your ass" and I think that really sums up some of the mind-baffling complexity that we could all have done without.

Anyway.

For developers, here's the order of operations that I want you to think about when you are writing code:

1. HTML
2. `aria-labelledby`
3. `aria-label`
4. `aria-describedby`

What about `title` or `placeholder`? Nope. No. Don't. Put it down. Don't do it. Even if you know what you're doing, even if the specification _technically_ outlines how it should be used, don't. It wasn't implemented consistently and it's a shit experience so just...don't.

This is my #1 rule of web development: Just because you _can_, doesn't mean you _should_. I don't really understand why developers are always asking me if the weird thing they want to do is prohibited, to be quite honest. It shouldn't have to be illegal. It can just be a REALLY BAD IDEA. In fact, it can just be a sort of bad, not very good idea. If you're making things on the web for PEOPLE TO USE, they should be awesome. They shouldn't be tolerable, or works most of the time, they should be awesome. Delightful. You should be bringing the freakin' delight.

## Examples

Let's look at some examples of how to do different kinds of accessible names. I think this is the part that really is going to be edited the most, because I do want to make a comprehensive set of examples and try to organize them in increasing complexity. If I think about it, this might be a separate repo, but I don't know yet. We're all along for the ride on this one.

I am going to describe this to you in simplest way I can imagine, and while there will be nuance for some increasingly-complex scenarios, this is a solid go-to for your foundation. Learn this first, and then add more complex examples on top of that. In _addition_ to this. But try to reach for these _first_.

### Accessible name is...just the text content

This is what everyone should prefer and be your go-to. There is no nuance here. The content of the thing is the accessible name of the thing, and everyone gets the same freakin' one. 

Let's consider the search input, because that's the first example that comes to mind where the complexity increases, depending on the design.

```html
<label for="search-input">Search this site</label>
<input type="search" id="search input" />
```

Or maybe you have a button that does a thing:

```html
<button type="button>Click Me</button>
```

### Accessible name can come from existing elements

Ok so let's imagine that your designer(s) got a little fancy on you, and they made something like this, and the heading is appropriate because it's in the correct heading order and flow of the document:

```html
<div class="some-nice-search-box-with-rounded-corners-and-a-nice-border">
  <h3 id="search-title">Search Our Site</h3>
  <input type="search" aria-labelledby="search-title" />
</div>
```

Here, we see that we can use the `aria-labelledby` (yes, two l's) attribute to say "the accessible name of this input field is another element that already exists." 

### Accessible name just isn't anywhere else.

But maybe you have an "evil" designer, and they are going to get you fired if you have a visible label on the page! Thankfully, you can still pay your bills and provide for your family.

Or, you just don't care enough to push back on crappy design (yes, I said it).

If you must, you can add an `aria-label` attribute to the `input` element.

```html
<input type="search" aria-label="search our site" />
```

Now, your _sighted_ users will have no idea what's going on here, but at least your users with screen readers will know what's going on!
Just kidding, maybe there's some kind of background image of a magnifying glass that's placed _just right_ and then everyone will know that we mean search. Right...?

Or maybe you have an icon-only button (again, there's research on this and user prefer the words, but if you must...)

```html
<button type="button" aria-label="more info">
 <svg aria-hidden="true">
  <!--all the svg here-->
</svg>
</button>
```

### Accessible description

Maybe in addition to your awesome label (using any of the aforementioned methods), you also want to provide some help text for your users so they better understand what you want them to do. In this case, the help text is considered the accessible description. You can use the `aria-describedby` attribute to provide _additional_ context for your users.

```html
<label for="search-input">Search this site</label>
<div id="help-text">Use quotation marks for an exact term.</div>
<input type="search" id="search-input" aria-describedby="help-text" />
```

The user should then be given the accessible name AND the accessible description.

Same attribute value rules as `aria-labelledby`:

1. takes `id` as the value
2. can have multiple values (space separated)
3. the order of those value matter

When you will especially want to reach for this is when you have an input that has both help text and, gasp, an error message! If you do that, then the user will be informed when there is an error associated with the input field. Let's imagine the user has somehow used the search incorrectly.

```html
<label for="search-input">Search this site</label>
<div id="help-text">Use quotation marks for an exact term.</div>
<input
  type="search"
  id="search-input"
  aria-describedby="help-text error-text-001" />
<div id="error-text-001">Search terms must be at least 3 characters long.</div>
```

## Closing out part one

I've just decided that this will be a multi-part blog post, because that's how I can explain and show incrementally more complex examples. For now, this was the simplest example I could think up, so it's what I went with first. If you were a developer and confused about what you should do in these scenarios, hopefully now you have a perspective to build on!

Until next time. -M
