---
layout: post
title: "Named Blocks and Composition"
tags: components
published: true
---

## The "parent" or "container" component

First, we have a generic "disclosure" component that will yield two named blocks. In the component.js, I'll define the `onClickToggle` action and some other keyboard things that will show/hide the `content` named block, as well as focus-trap things (for accessibility). Here's a truncated version that shows the relevant code:

Template: 

```hbs
<!-- my-disclosure.hbs -->
<div class="my-disclosure" ...attributes>
  {{yield (hash onClickToggle=this.onClickToggle) to="toggle"}}
  
  {{#if this.isActive}}
    {{yield to="content"}}
  {{/if}}
</div>
```

To invoke:

```hbs
<MyDisclosure>
  <:toggle>
    <!-- put toggle here -->
  </:toggle>
  <:content>
    <!-- put content here -->
  </:content>
</MyDisclosure>
```

## For the `<:toggle>` block

Next, I made a template-only component called `MyDropdown::Toggle`:

```hbs
<button type="button" class="my-dropdown-toggle" {{on "click" @onClickToggle}}>
  {{@toggleText}}
  <MyIcon @icon="chevron-down" />
</button>
```

Let's invoke that in the `MyDisclosure` component and attach the action through block params:

```hbs
<MyDisclosure>
  <:toggle as |t|>
    <MyDropdown::Toggle @toggleText="User Menu" @onClickToggle={{t.onClickToggle}} />
  </:toggle>
  <:content>
    <!-- put content here -->
  </:content>
</MyDisclosure>
```

This will toggle the dropdown as desired, but it will also give me a console log error: 

```bash
Uncaught Error: You must pass a function as the second argument to the `on` modifier, you passed undefined.
```

What am I missing/doing incorrectly here? Not sure, because I'm 99% sure that this should work.


## Replacement #1 (works)

If I replace 

```hbs
<MyDropdown::Toggle @toggleText="User Menu" @onClickToggle={{t.onClickToggle}} />
```

with

```hbs
<button type="button" {{on "click" t.onClickToggle}}>User Menu</button>
```

I do not get any errors. Not desired but at least I can see that the idea of it _should_ work and I am probably just missing something.

## Replacement #2 (works)

If I add `...attributes` to the template for `<MyDropdown::Toggle>`:

```hbs
<button type="button" class="my-dropdown-toggle" ...attributes>
  {{@toggleText}}
  <MyIcon @icon="chevron-down" />
</button>
```

And change my invocation a little: 

```hbs
<MyDisclosure>
  <:toggle as |t|>
    <MyDropdown::Toggle @toggleText="User Menu" {{on "click" t.onClickToggle}} />
  </:toggle>
  <:content>
    <!-- put content here -->
  </:content>
</MyDisclosure>
```

This also works, but am I creating a future issue if the parent component and the child component both have `...attributes`? If I wanted to compose what I have here into a single component, where would I need to change things? I have a few more things to think through; I'll post an update once I figure them out.
