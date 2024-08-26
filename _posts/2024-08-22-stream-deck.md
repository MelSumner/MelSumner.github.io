---
layout: post
posttitle: "How I use my Stream Deck"
slug: stream-deck
---

I bought an Elgato Stream Deck in the fall of 2020, and it came up recently that I may use it in a non-conventional way. Elgato has my attention as a gamer; I use their key lights, microphone, and even tried their web cam for a while (the web cam didn't keep; I have a Sony ZV-1 and I'm happy with it).

I currently use my Stream Deck attached to my Macbook Pro for work; here are some of the things I have it set up to help with:

* GitHub commands I can never remember (or, just don't want to get wrong)
* CLI commands for MacOS (especially the one I have to run after every update)
* Zoom
* Rectangle, because Mac doesn't have the awesome screen snapping stuff Windows has
* Code snippets I use a lot
* Zakim commands for W3C IRC chat

So let's talk about a couple of these use cases.

## Rectangle App

Right now, I have an ultra-widescreen monitor. This is where Rectangle comes in pretty handy. 

I have commands that give me a variety of configuration options but I've taken the ones I use the most and put them into my Stream Deck.

![Stream Deck setup window with three rows of five buttons each. First row: left half, right half, center, left 2/3, right 2/3. Second row: Top left, bottom left, top right, bottom right, blank button. Third row: previous menu, left 1/3, center 1/3, right 1/3, next menu](https://github.com/user-attachments/assets/856b7172-37b7-429b-8dc6-a0704dafcf04)

I do wish that they would build this into the OS like Windows has, but until then, this works.

## IRC

The W3C uses IRC for meetings, and notes are taken with a bot named Zakim. Since this isn't a tool folks otherwise use, everyone is always trying to remember what the commands are (via various cheat sheets, etc). These meetings are still a bit intimidating for me, so to reduce my anxiety in the times when I do scribe, I set up my Stream Deck to help me with that. 

![Stream Deck setup window with three rows of five buttons each. First row: present, add self to queue, remove self from queue, become scribe, takeover scribe. Second row: display agenda, next item, close item, queue list, blank button. Third row: previous menu, pick scribe, blank button, end meeting, make minutes.](https://github.com/user-attachments/assets/38296ee3-e038-499d-9289-548280a9bf11)

I still can't remember (or find) what the command is to say something in IRC and make sure it's left out of the minutes, but that's probably for the best, anyway.

## Other random useful macros

There are some other things that I find super useful to me to have available at the push of a button.

* Blog Frontmatter (used this one while making this post!)
* After MacOS Update: `xcode-select --install`
* Conventional Comment Request: `Please consider using [conventional comments](https://conventionalcomments.org/) when reviewing this PR.` This comes in really handy when I'm submitting a PR.
* An "approve PR" shortcut: `This seems fine to me right now,  if I think of anything else later I'll open an issue or a PR. 👍 :shipit:`
* Caffeinate to keep my computer awake for 8 hours: `caffeinate -dist 28800`
* Caffeinate to keep my computer awake for 4 hours: `caffeinate -dist 14400`

There are a lot of uses for the Stream Deck, and it's become a convenient tool for me to have this lil gadget on my desk!

Until next time. -M
