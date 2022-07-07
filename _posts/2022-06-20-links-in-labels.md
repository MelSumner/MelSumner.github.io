---
layout: post
title:  "Links in Labels"
slug: links-labels
---

It seems to be a relatively common pattern to have links in labels, but is that accessible? In this article, I'll explain what's going on, and explore some options, see how they work with a screen reader, and (hopefully) provide some food for thought. 

<!--more-->

## The Common Pattern

The form code below shows a common pattern for presenting the user with a required action: tick a checkbox to indicate that they have read, and accept, the terms and conditions (noting that the link would contain a real URL if this were live code): 

```html
<form action="" method="" name="form-zero">
  <input type="checkbox" id="terms" name="terms" required />
  <label for="terms">I have read and accept the <a href="#">terms and conditions</a>.</label>
  <button type="submit">Submit</button>
</form>
```

When I review this code rendered to a browser with a screen reader, I find that there are two issues here:

* Double label: the accessible name of the input is "I have read and accept the terms and conditions. I have read and accept the terms and conditions." 
* Missing link identifier: there is no indication that anything is linked. A user can only navigate to the link for the terms and conditions (TOC) _after_ they have had to interact with the **required** checkbox.

It seems bad to ask a user to agree to TOC if they have not been first presented with the link to read them (ok, maybe not that bad because there are like ten people in the world who do actually read the terms and conditions, but imagine that this is something super important).

Let's see if this can be improved.

## Approach: Help Text

If you are a mouse user, clicking on the label for a form element would make the cursor move inside the associated input element, or activate a checkbox or radio. This is nice default browser behavior, and helps some users more easily use form controls. But as we discovered in the first example, adding a link here does not work for all users, so I need to try something else.

Let's try help text. To associate the link as help text for the `input`, use the `aria-describedby` attribute.

```html
<form action="" method="" name="form-one">
  <input type="checkbox" id="terms-form-one" name="terms" aria-describedby="terms-help" required />
  <label for="terms-form-one">I have read and accept the terms and conditions</label>
  <div class="help-text" id="terms-help"><a href="#" target="_blank">(read the terms and conditions)</a></div>

  <button type="submit">Submit</button>
</form>
```

Unfortunately, we see here that this will still only convey the _text_ to screen readers; it will not also inform that it is a link. The link can still be found by navigating (via `TAB`, usually), but a user could be confused if they encountered a required checkbox about terms and conditions before encountering the link to actually read those terms and conditions. So this still seems too similar to the first approach. What else can I try?

## Approach: Fieldset and Legend

Maybe I can use the `fieldset` and `legend` elements to improve this pattern. It should allow me to keep the information and also make the link more easily available to all users. I'd like to make the link to the terms and conditions available **before** the required checkbox to accept the terms and conditions.
  
```html
<form action="" method="" name="form-two">
  <fieldset>
    <legend><a href="#" target="_blank">Terms and Conditions</a></legend>
    <input type="checkbox" id="terms-form-two" name="terms" required />
    <label for="terms-form-two">I have read and accept the terms and conditions</label>
  </fieldset>
  <button type="submit">Submit</button>
</form>
```

This one works out pretty okay! 
  
* the markup is semantically accurate
* the native behavior of clicking on a label and activating the control is preserved
* screen readers will read out the `legend` text as a link
* the link to the terms and conditions are presented **before** the required checkbox interaction
  
Some folks may still be of the mind that they don't like using `fieldset` because of the default browser styling (I personally like it, but to each their own). However, it can be re-styled with a little CSS so really, don't worry about that! 
  
## Closing
  
I hope this has helped you better understand some considerations for links inside of labels, and maybe some additional perspective on how a screen reader works. 
  
Until next time. -M
