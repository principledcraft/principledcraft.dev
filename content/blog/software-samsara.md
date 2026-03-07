---
title: Software samsara
date: 2026-03-07
summary: I studied Buddhism for a semester in college, never thought it would end up relevant to software engineering. Samsara is the cycle of death and rebirth, and software has its own version. The Buddha's answer was the Middle Way, and it turns out that applies to code too.
authors:
  - name: PrincipledCraft
draft: false
---

Who would have thought that studying a semester of religious sciences in college would help me better understand software engineering? In Buddhism, samsara is the cycle of death and rebirth, the soul moving from one life to the next, never quite arriving.

Software has its own version of this. A team builds something, people leave, a new team inherits it, struggles to understand it, and eventually convinces the business that the only way forward is to start over or to rewrite a significant part of it. The new system is built with conviction and energy. Give it a few years and another team will be making the same case.

I've seen it happen before and also dealt with it myself. I joined a new codebase and found myself struggling to work with it to implement the simplest behaviours, wondering why it was put together the way it was. Upon asking, I came to understand that the system was re-engineered from scratch because the previous system was impossible to comprehend. So why did history seem to repeat itself so easily, even with the best intentions? It seems to me that the urge to rewrite comes from an inability to form a clear theory on how the system operates.

[Peter Naur](https://en.wikipedia.org/wiki/Peter_Naur) illustrates this in his 1985 paper [Programming as Theory Building](https://gwern.net/doc/cs/algorithm/1985-naur.pdf). He argued that the real product of programming isn't the code itself, but the theory the programmers hold in their heads: how the solution maps to the real world, why each part is the way it is, and how it should respond to change. When those programmers leave, the theory dies with them, even if the code keeps running. He called this the "*death*" of a program.

> A dead program may continue to be used for execution in a computer and to produce useful results. The actual state of death becomes visible when demands for modifications of the program cannot be intelligently answered.<br>
> — <cite>Peter Naur</cite>

The code is right there, it works, but nobody knows *why* it's shaped the way it is, and reading the code alone is not enough to piece everything together. The original programmer's intent is lost and/or unclear. So when someone new needs to change it, they bolt on patches that ignore the original structure, or they give up and push for a rewrite.

[Dan North](https://dannorth.net/) picks up on Naur's ideas in his talk *A Defence of Technical Excellence*, where he identifies confusion as a primary blocker in delivering software effectively and on time. When the theory is gone and the structure of the codebase does not clearly communicate its intent and direction, confusion takes over, and confused teams slow down over time, producing more bugs and delivering less code.

{{< youtube BkxIwxSp7V0 >}}
<br />

I feel like one of the most effective defences against that confusion is [simplicity](/principles/quality/simplicity). Simple code is easier to reason about and easier to form a mental model of. It's no guarantee that someone will understand your system, but it removes a huge number of obstacles. When you keep things as simple as possible, you're doing the next person a favour that compounds over the life of the codebase. 

[Eric Evans](https://www.domainlanguage.com/) tackles this from a different angle with Domain-Driven Design. The core idea is that the structure of your software should mirror the structure of the business problem it solves, and that developers and domain experts should share a common language, what Evans calls a "ubiquitous language". When your classes, methods and modules are named after the things the business actually talks about, the code itself becomes a carrier of the theory. A new developer joins, reads the code, and the domain concepts are right there, not buried in someone's head or a forgotten wiki page. DDD fights confusion by keeping the domain visible, which is exactly the kind of shared understanding that Naur argued was the real product of programming.

I like the word *hospitality* for this. Writing hospitable code means thinking about the experience of the person who comes after you. Clear naming, sensible structure, and just enough documentation and hooks in the code to communicate the *why* behind the decisions. Not a spec that will rot in a wiki somewhere, but enough to help someone build an accurate mental model. 

The business effects of when this goes wrong often go unnoticed. Rewrites are expensive in ways that aren't obvious upfront: maintaining two systems at once, features slowing to a crawl while the new system catches up. And then the new system, if built without the same care, eventually faces the same fate. The business demands a rewrite, gets one, and then doesn't take every step necessary to prevent the next one when the team changes. That's not fair. It's samsara. The cycle repeats in smaller ways too: delivery slows, new teammates struggle to onboard, they have to ask a lot of questions, which costs time, money and motivation. If the application is expected to run and evolve for years, the experience of future developers is part of the product. That's what keeps a codebase alive in Naur's sense: not merely running, but understood.

The Buddha's answer to samsara wasn't to reject the world or to cling to it harder. It was the [Middle Way](https://en.wikipedia.org/wiki/Middle_Way): a path between extremes. The rewrite is one extreme, a dramatic rebirth that feels like progress but often just resets the clock. The other extreme is resignation, letting the codebase rot because "it works" and nobody wants to touch it. The Middle Way applied to software is keeping things as simple as possible, but no simpler. Simple enough that the next person can form a theory of how it works. Rich enough that the domain is honestly represented and the code doesn't collapse under real requirements. No rewrites, no neglect, no over-engineering. Just steady, deliberate care, and a real effort to make the system understandable to whoever comes next. That's how you break the cycle.
