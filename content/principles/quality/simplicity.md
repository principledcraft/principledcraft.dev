---
title: Simplicity
type: docs
weight: 3
---

[Edsger Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) wrote it in 1975 and it remains true today:

> "Simplicity is prerequisite for reliability."

If you want software that works and that can be changed safely, simplicity is not optional. It is the foundation.

## Every line is a liability

Code is not an asset. It is a liability. Every line you write must be understood by the next person who reads it. It must be tested, reviewed, and maintained. And it might contain a bug.

The less code you have, the fewer places bugs can hide and the easier the system is to understand. The goal is not to write as much code as possible. It is to solve the problem with as little code as is reasonable.

This does not mean writing terse, clever code. Cramming logic into fewer characters is not simplicity; it is obfuscation. Simplicity means fewer concepts and fewer moving parts.

## KISS

"Keep It Stupidly Simple" is one of those principles everyone agrees with and few consistently follow. The straightforward solution feels too easy. Surely the problem needs something more sophisticated?

Usually it does not. Most problems are simpler than they first appear. The sophisticated solution often introduces complexity that creates its own problems, problems you now have to solve on top of the original one.

When two approaches solve the same problem and one is simpler, choose the simpler one. You can always add complexity later if it turns out to be genuinely needed. Removing complexity that was added prematurely is much harder.

## YAGNI

"You Aren't Gonna Need It" is the principle that says: do not build things you do not need yet. Do not add a caching layer because you might need it someday. Do not create an abstraction for a pattern you have seen exactly once.

Predictions about future requirements are usually wrong. When they are right, they are rarely right about the details. I have seen entire squads of development teams being told to start preparign for the next big paradigm shift due to 'Project X', only to see a huge amount of work wasted after 'Project X' is ultimately canceled due to scale up problems. 

Build what is needed now, today, not a few months from now. When new requirements actually arrive, you will know more about what they look like and can build the right thing. Code that does not exist has no bugs and requires no maintenance.

## Complexity compounds

Complexity does not grow linearly. Each new piece interacts with everything already there. A system with ten moving parts does not have ten sources of confusion; it has the interactions between all of them.

This is why "just one more feature" or "just one more abstraction" is dangerous. Each addition seems small on its own, but the accumulated complexity makes every subsequent change harder. Teams rarely notice the moment their codebase crossed from manageable to painful. It happens gradually, one reasonable-seeming decision at a time.

The way to fight this is not heroic cleanup efforts. It is constant vigilance: questioning whether each new addition is worth the complexity it brings, and regularly asking whether existing complexity is still earning its keep.

## Avoid hype, analyse tradeoffs

Simplicity also means resisting the pull of trends. Technologies and patterns come with tradeoffs, and your job as an engineer is to evaluate those tradeoffs for your specific context, not to adopt whatever is popular.

Microservices solve real problems for large organisations with many teams. They also introduce distributed systems complexity that most applications do not need. A message queue is the right tool for some problems and unnecessary overhead for others. The answer is never "always" or "never." It is "what does this cost, and is it worth it here?"

[Dan McKinley](https://mcfunley.com/) calls this [choosing boring technology](https://mcfunley.com/choose-boring-technology). Every team has a limited capacity for adopting new things. Spend that capacity on the problems that are unique to your business, not on replacing proven tools with fashionable ones.

The worst version of this is résumé-driven development: choosing technologies because they look good on a CV rather than because they are right for the project. The users and the team that maintains the code after you leave pay the price for that choice.

## Why simplicity is worth the effort

[CodeMunk](https://www.youtube.com/@codemunk) gives a nice overview of why writing simple code is harder than it looks, and why it pays off.

{{< youtube xnrHnnfcdkA >}}
