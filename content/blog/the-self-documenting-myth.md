---
title: The self-documenting myth
date: 2026-03-20
description: "What cognitive science tells us about making codebases accessible beyond just writing working code."
summary: "I keep hearing that code should be self-documenting. But cognitive science tells a different story. Writing code that works is only half the job. The other half is making sure others can actually understand it."
authors:
  - name: PrincipledCraft
draft: false
toc: false
breadcrumbs: false
---

{{< summary >}}

"Just read the code." I hear it a lot. No comments needed, no docstrings, the code speaks for itself. Clean code, well-named functions, small methods. What more could you need?

I've been in codebases that claimed to be self-documenting and still found myself lost. Not because the code was bad, but because understanding code takes more than reading syntax. And every hour I spent trying to piece things together was an hour I wasn't delivering anything.

## Your brain has limits

[Felienne Hermans](https://www.felienne.nl) digs into this in [The Programmer's Brain](/books/the-programmers-brain/). She draws on cognitive science to explain what actually happens when we read code. Your brain deals with three types of cognitive load at any given time. Intrinsic load is the difficulty of the problem itself. Extraneous load is what the environment piles on top: confusing naming, scattered code, unclear structure. Germane load is the effort of actually learning, storing what you've understood into long-term memory and building connections you can use later.

These three compete for the same limited working memory, which holds roughly two to six items. When intrinsic and extraneous load eat up all the capacity, there is nothing left for germane load. You can spend an afternoon reading code and walk away without having understood any of it.

## We read more than we write

Research shows that programmers spend around 60% of their time reading and understanding code, not writing it. If most of the work is comprehension, then making code easier to comprehend is part of the job. When code is hard to follow, we default to reading line by line, which is slow and tiring. No wonder so many developers would rather rewrite something from scratch than try to understand what already exists.

## The curse of expertise

There is a cognitive bias called the curse of expertise. Once you have internalised something, you forget how hard it was to learn. What feels like second nature to you is the product of years of experience, automatised skills, and mental models that took time to build. An expert reads a piece of code and sees patterns and familiar shapes. A newcomer sees individual lines.

This is why "just read the code" is misleading. The person who wrote it reads it effortlessly because they already hold the theory behind it. For everyone else, the code alone may not be enough.

## Syntax versus intent

We can distinguish between two kinds of understanding. Textual knowledge is understanding what the code does syntactically: this variable holds that value, this function calls that one. Plan knowledge is understanding the intent, why the code is structured this way, how the parts relate, and what problem it solves.

You can have solid textual knowledge of a piece of code and completely lack plan knowledge. Self-documenting code gives you the first kind at best. The second kind lives in the programmer's head, and unless they leave clues behind, it leaves with them.

## Leaving breadcrumbs

The goal, then, is to lower the extraneous load. Leave more room for germane load, for building actual understanding.

Good naming is the obvious starting point. Names make up roughly a third of all tokens in a codebase and are beacons, anchor points that help a reader form a mental model. A well-chosen name lets the reader chunk code into meaningful units rather than processing it token by token.

Then there are comments. They have a bad reputation, partly because bad comments are worse than none. But the answer to bad comments is better comments. Code tells you *what* is happening. It cannot tell you *why* this approach was chosen over the alternatives, or what assumptions it relies on. [John Ousterhout](https://web.stanford.edu/~ouster/cgi-bin/home.php) puts it well in [A Philosophy of Software Design](/books/a-philosophy-of-software-design/):

> The overall idea behind comments is to capture information that was in the mind of the designer but couldn't be represented in the code.

Consistent conventions matter too. Hermans describes how experienced programmers read code in chunks rather than line by line. Design patterns, naming conventions, and familiar structures are beacons that let the reader skip past details and grasp the bigger picture. When a codebase is inconsistent, every reader has to slow down and process each section from scratch.

And there is broader structure. Among others, things like role expressiveness (how easy it is to see the purpose of each part), hidden dependencies (how visible the connections between components are), and closeness of mapping (how well the code mirrors the problem it solves). These shape how someone will experience your system, and they are worth thinking about when you design one and where to make deliberate trade-offs in this regard.

## Code smells are cognitive load

This is also why [code quality](/principles/quality/the-cost-of-poor-quality) matters beyond correctness. A long parameter list overloads working memory. A god class prevents chunking, forcing you to read line by line. Duplicate code that looks similar but behaves differently leads to wrong assumptions. Hermans points to research showing that code with smells is more likely to contain bugs and more likely to change. It is harder to work with because it places a heavier cognitive burden on whoever reads it.

## Simplicity and understanding

This connects to [simplicity](/principles/quality/simplicity). Simplicity is about more than writing less code or having fewer moving parts. It is about structuring things so the next person can form an accurate mental model without exhausting their working memory. A codebase with fewer lines but scattered logic and cryptic naming is not simple. A longer one with clear structure and well-placed comments might be.

## More than syntax

"Just read the code" works for the person who wrote it. For everyone else, it means reverse-engineering someone's thought process. Writing code that runs correctly is half the job. The other half is leaving behind enough context that someone else can build understanding too.

Every hour a developer spends deciphering code is an hour not spent improving it. Multiply that across a team, across every new joiner and every handover, and hard-to-read code becomes one of the most expensive things an organisation maintains.

Your code is not self-documenting. But with some care, you can make it much easier to understand.
