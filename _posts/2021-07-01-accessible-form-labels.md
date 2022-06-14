---
layout: post
title: "Accessible Name for Form Inputs"
date: 2021-07-01 18:00:00 -0500
tags: accessibility forms accname guide
---

Here are some ways to provide an accessible name for your input elements that conform with WCAG 2.1 AA Success Criteria. For these examples, I've tested with Windows (FF + NVDA, Chrome + NVDA) and macOS (Safari + VoiceOver, Chrome + VoiceOver).

<h2 id="nest"><a href="#nest">&sect;</a> Nest It</h2>

Nest the input element inside of the `label` element:

```html
<label> First Name <input type="text" /> </label>
```

This is the perhaps the easiest way to associate input with label, but some will say this is too difficult to style properly. YMMV.

<h2 id="idfor"><a href="#idfor">&sect;</a>Use Id/For</h2>

Use the `for` attribute on the `label` element to associate it with the `input` element:

```html
<label for="input-age">Your Age</label>
<input id="input-age" type="number" />
```

This is probably the most popular way to associate an input with a label, because it provides flexible styling. Note that the `for` and `id` attributes must have the same value to be associated with one another, and that `id` values on a web page must be unique.

<h2 id="multi"><a href="#multi">&sect;</a>Multi-element Name</h2>

Associate a label with the input and also support help text with the aria-labelledby attribute on the `input` element:

```html
<label id="input-name">Your Name</label>
<span class="help-text" id="input-name-additional">
(Preferred)
</span>
<input type="text" aria-labelledby="input-name input-name-additional" />
```

Here we are using aria-labelledby to get the accessible name from multiple elements. (This is not the best example, sorry)

<h2 id="inputhelp"><a href="#inputhelp">&sect;</a> Input with help text</h2>

Associate a label with the input and also support help text with the aria-labelledby attribute on the `input` element:

```html
<label for="input-last">Your Last Name</label>
<span class="help-text" id="input-last-help">
Multiple or Hyphenated last names are supported
</span>
<input type="text" id="input-last" aria-describedby="input-last-help" />
```

Note: This is the way I usually provide an input with additional help text.
