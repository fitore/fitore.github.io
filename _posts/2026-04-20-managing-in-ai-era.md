---
layout: post
title: "Managing in the AI Era: Where the Responsibility Moves"
date: 2026-05-05
---

## The Junior Developer Analogy

The most useful reframe I've found for working with AI agents is to treat them like junior developers. Not because they're equivalent. They're not. The analogy works because it encourages the right operational behavior. You don't hand a junior developer a vague ticket and disappear. You don't merge code without review. You don't assume silence means progress. Most of the time, silence means they're stuck, confused, or solving a different problem than the one you thought you gave them. The same pattern shows up with agents. Give them a poorly-defined problem and they'll often produce something technically reasonable that misses the intent entirely. The failure mode isn't incompetence. It's translation.

The analogy starts to break down when you look at where improvement comes from.

A junior developer improves through experience. Agents don't. When performance improves, it's usually because the surrounding system improved: better context, sharper skills, clearer constraints, stronger verification, more explicit definitions of success. You're not developing the agent. You're developing the environment the agent operates within.

We saw this in our own experimentation. We run a small R&D guild, intentionally separated from production concerns. The goal isn't to ship. It's to explore what becomes possible, retire findings back into the current state, and make the gaps visible. One of the workflows that emerged was an agentic software factory. A ticket arrives. One agent develops an implementation plan. Another writes code. Another reviews it. Another prepares deployment. Humans sit at the gates between stages. Not because we don't trust the agents, but because in a regulated environment the human-in-the-loop isn't optional. It's part of the system design.

What became interesting wasn't that the workflow worked. It was that the quality of the outcome depended far less on the individual agents than on the structure surrounding them. The more explicit the constraints became, the more reliable the workflow became. That experience led me to a different concern.


## Comprehension Debt
Most discussions about AI focus on production. How much code can it generate? How much time can it save? The harder question is comprehension. I think of it as comprehension debt: producing work faster than you can understand, reproduce, debug, or defend it. The problem isn't that the code was written by an agent. The problem is that ownership still sits with the engineer reviewing it. If output arrives faster than understanding, the bottleneck hasn't disappeared. It has moved.

## Where the Responsibility Moves

The same shift shows up in engineering leadership.

My Staff+ engineers spend their time building the harness: orchestration layers, governance boundaries, ontology-backed knowledge models, and the tooling that shapes what agents can see and do. My responsibility sits one layer higher: defining constraints, clarifying ownership, and making business rules explicit enough that they can survive contact with tooling. The constraint documented today becomes the policy tomorrow. The architectural decision written clearly enough becomes the IDE guidance surfaced at exactly the right moment. What looks like documentation often turns out to be infrastructure in waiting.

The same translation problem shows up one level higher, in how organizations evaluate the work. Engineering isn't the only function relearning how to reason about AI investments. Finance is too. The easiest metric is hours saved. It's also the one that's steadily losing credibility. Time doesn't appear anywhere on a P&L unless it becomes something concrete: supporting more volume without proportional hiring, shortening delivery cycles, reducing operational cost, or creating new revenue. Until that conversion is made explicit, the savings remain theoretical—and finance is right to discount them.

That shift changes how we think about investment as well. We already distinguish between keeping the lights on, improving quality, building new capabilities, and making the engineering system itself more productive. AI doesn't replace those categories; it cuts across them. Some investments improve the throughput of existing teams. Others make previously impractical work economically viable. Others create strategic options whose value won't become visible for years. Those are different claims requiring different evidence, and treating them as a single line item called "AI" obscures what we're actually learning.

That's why the junior developer analogy eventually stops being useful. The difficult part of the agentic transition isn't managing the agents. It's making the system explicit enough that they can operate safely inside it. Agents don't eliminate ambiguity. They expose it.

The places where they struggle are often the same places where the organization was relying on shared understanding rather than shared definition. No amount of orchestration compensates for a constraint that never made it into the system in the first place.

The agent isn't the system that's learning. We are. The work is no longer just producing software. Increasingly, it's making the organization itself explicit enough that good judgment no longer depends on tribal knowledge. That's the shift I think many of us are actually managing.
