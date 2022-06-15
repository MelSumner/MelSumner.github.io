---
layout: post
title:  "Details-as-a-menu"
slug: details-as-a-menu
---

A few months back, I had to work on a situation where the `details` element was being used as a dropdown menu for a site navigation. In this post, I'm going to explain why I think you should **not** use a `details` element as a dropdown menu. TL;DR? Don't use the `<details>` element for a dropdown menu, use a `<button>` element that toggles open a list of links instead.

<!--more-->

I know this will disappoint some of you and I'm sorry in advance for that. But I think it's better to know than to not know.

## The Details Element

Here is the HTML spec for the `<details>` element: https://html.spec.whatwg.org/#the-details-element

> The details element represents a disclosure widget from which the user can obtain additional information or controls.

The _"or controls"_ part bothers me a little bit, but we'll get to the why of that in a minute.

You will usually see this when someone needs to add some extra legal info but doesn't want a giant wall-o-text on their website. You can disclose extra information but hide it behind a convenient little dropdown/drawer kind of interaction.

## Some experiments 

Let's play around and see what the browser _allows_ us to do. I like to think of HTML as the parent that lets you get away with anything, and tries to fix things behind the scenes if it needs to. It has sort of the "life is hard enough, and there's other things I can't fix, but this...THIS is something I can do." It always wears a cape in my mind, even though I'm very Edna Mode when it comes to capes. 

### Just details

This code: 

```html
<details>
  <p>Some text here that you'd want to know more about </p>
</details>
```

Renders to this:

<details>
  <p>Some text here that you'd want to know more about </p>
</details>

Looks like it renders the word "details" and you can still open/close the element. So the `details` element is the interactive part?

My spidey senses are tingling, I bet this won't pass the HTML validator. So let's check: 

<img width="675" alt="Error: Element details is missing a required instance of child element summary. Content model for element details:
One summary element followed by flow content." src="https://user-images.githubusercontent.com/4587451/173826383-ab0d2795-ccb6-4483-82ec-313e90c80728.png">

Sure enough, it's not valid HTML to use the `<details>` element without the `<summary>` element. But look at that last bit- "followed by flow content". 
This gives me room to pause, because I know that flow content includes both lists and links and also other things like forms...so hmm wtf? Let's keep going for now, though.

**Result:** Not valid HTML and therefore not valid WCAG (fails on [4.1.2 Name, Role, Value](https://www.w3.org/WAI/WCAG21/Understanding/name-role-value.html); see [H88 Use HTML according to spec](https://www.w3.org/WAI/WCAG21/Techniques/html/H88.html))

### Details and Summary

This code: 

```html
<details>
  <summary>More Info</summary>
  <p>Some text here that you'd want to know more about.</p>
</details>
```

Renders to this:

<details>
  <summary>More Info</summary>
  <p>Some text here that you'd want to know more about </p>
</details>

So, it seems like the `details` is the interactive part, and the `summary` is just text to be used as the title of the element. Interesting.

The HTML validator is not showing that there's anything technically inaccurate with this markup either: 

<img width="600" alt="Document checking completed. No errors or warnings to show." src="https://user-images.githubusercontent.com/4587451/173834024-472e2208-a5a6-4920-b0a3-39b323c69e53.png">


## Accessibility

So what about the accessibility of this, then? 

The `details` element:

* has the implicit role of group.
* is not eligible to receive any other role
* may receive any aria-* attribute that is in the "global" list (https://www.w3.org/TR/wai-aria-1.1/#global_states)
* may receive any aria-* attributes applicable to the group role

The `summary` element:

* has the implicit role of button
* this means that all child elements should be considered presentational by assistive technology (this is not necessarily true in practice, but may be considered either a bug or coincidental that it works, not purposefully allowed by spec)
* is not eligible to receive any other role
* may receive any global aria attribute (see above)
* may receive any aria-* attributes applicable to the button role
* can only be used as the first child of the `details` element

So this spec makes it really clear but the implementation in the browser- the details element still opened even when no summary element was present.

According to HTML spec and ARIA spec, things should be a-okay, which makes me think that it was the implementation that was not done correctly. 

### What really happens

Consider this code:

```html
<details>
  <summary>User Menu</summary>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="./about">About</a></li>
    <li><a href="./contact">Contact Us</a></li>
  </ul>
</details>
```

I tried this in these combinations:

* VoiceOver and Chrome (MacOS)
* VoiceOver and Safari (MacOS)
* Firefox and NVDA (Windows)

Assistive Tech (AT) will tell the user something like this:

* "User Menu, collapsed, summary button"
* "User menu, collapsed, disclosure triangle"
* "User Menu button collapsed"

Once you press the button (technically here the summary element, although the entire elements stays focused), it will announce something like:

* "User menu, expanded, summary button"
* "User Menu, expanded, disclosure triangle"
* "User Menu button expanded"

You can then press TAB (or VO + TAB in Safari) to navigate to the next interactive element, which in this case would be the "Home" link and would be read (in most cases) like, "list with three items. home, link."

Technically this works, even if it's a bit confusing to use with a screen-reader. I expected a disclosure widget and now I'm in a list with links?

If I use my keyboard shortcuts (VO + U, then left/right arrow key through the rota)

* I will see/hear the links inside of the `details` element in the "links" list
* I will see/hear the summary inside of the form elements list but only if I am in Chrome- Safari does not have this same list.

**Nothing associates the two or combines them.** 

## Conclusion

It's technically permissible but don't do it.

* The interactive flow content is not associated with the disclosure widget
* The `button` with `aria-expanded` and hiding/showing a list of links is already a well-known pattern.
* The `details` element was not implemented according to spec (if it was, it should not be interactive if the `summary` element is missing).

