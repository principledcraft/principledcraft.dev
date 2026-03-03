---
title: Developer Flow
type: docs
weight: 4
---

Simplicity in the code matters. But so does simplicity in the workflow. A codebase that is well-designed but painful to work with will still slow teams down. Fast feedback loops and low friction are what keep developers productive over time.

## Flow is fragile

Deep, focused work is where most good software gets written. Getting into that state takes time. Getting knocked out of it takes almost nothing: a slow build, a flaky test, a tool that fights you instead of helping you.

Every interruption to flow has a cost beyond the interruption itself. A developer who gets blocked for a few minutes does not just wait. They check email, start thinking about something else. Getting back to where they were takes longer than the interruption itself.

Protecting flow is not a luxury. It directly affects how much useful work a team produces.

## Fast feedback, low friction

The cycle from *I changed something* to *I know whether it works* should be as short as possible. Seconds, not minutes. Minutes, not hours. When feedback is slow, developers batch up changes and test them less often. Bugs get discovered later, when they are harder to trace.

If a task is important enough to run more than once, automate it. Formatting, linting, test suites on every push, deployments. Setting up a development environment should be a single command, not a wiki page with thirty steps that is always slightly out of date. The goal is to spend human attention on things that actually require human thought, like design decisions and understanding what users need.

## Treat flow as real work

A lot of developers see pipeline and tooling work as secondary, something you do when you have spare time between "real" tasks. But this work is an enabler. When build systems, CI pipelines, and deployment processes work well, they make everything else faster. When they do not, they drag the whole team down. Building and maintaining the processes around the code is just as much part of the job as writing the code itself.

## Let developers choose their tools

Teams need to align on the tech stack, testing frameworks, and CI pipeline. Outside those shared decisions, let developers pick their own editor, terminal, OS, and whatever else helps them work. Standardise what affects the whole team, leave the rest to the individual. Allowing people to use familiar tooling is another way to reduce friction.
