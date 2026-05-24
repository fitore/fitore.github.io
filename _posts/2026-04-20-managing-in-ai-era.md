---
layout: post
title: "Managing in the AI Era"
date: 2026-05-05
---

The most useful reframe I've found for working with AI agents is also the one that falls apart fastest: treat them like a junior developer.

It works because it sets the right operational stance. You wouldn't give a junior developer a vague ticket and walk away. You wouldn't merge their PR without review. You wouldn't assume silence means progress — in that context, silence usually means they're stuck or have gone somewhere unexpected and haven't told you. The same is true for agents, and for roughly the same reasons.

### Where it breaks: junior developers grow. Agents don't — not the same way.

The investment in onboarding and feedback compounds over time with a human. With agents, the compounding happens at the tooling level — better grounding, better skill definitions, better constraints. You're not developing the agent; you're developing the system around it. That's a different kind of management, and it's worth naming the difference.

### How we structured permission to experiment.

We run a guild model — a small group of senior engineers working in a dedicated R&D space, explicitly sandboxed from production. The brief: prove what's possible, retire findings back to current state, name the gaps. No pressure to ship. Permission to be wrong quickly.

What came back was instructive. The group built an agentic development workflow: a ticket arrives, one agent writes an implementation plan, a second writes the code, a third reviews it, a fourth stages the deploy. Each step has a human at the gate. Not because we don't trust the agents — because in a regulated environment, the human-in-the-loop isn't optional. It's the design.

### The comprehension problem is the one most teams aren't answering yet.

What that workflow surfaces is a harder question: what does "the engineer owns the judgment" actually mean when output arrives faster than it takes to properly review it? I call this comprehension debt — producing work you can't fully reproduce, debug, or defend. It's not a laziness problem. It's an ownership problem, and it shows up at the verification step.

Getting that right is the actual engineering work of the agentic transition. The tooling is the easy part.

### On the management side: AI literacy isn't binary, and the adoption pattern is telling.

I have engineering managers working on their own workflows in parallel — automating repository context, release administration, system health aggregation. Useful things, in use, not experimental.

The pattern I notice across both groups: the people who adopted AI without anxiety mostly started from a question, not a tool. They had something they were already frustrated by. The tool happened to fit. The people who are more cautious were often handed a tool and asked to find a use for it — which is a harder starting position and a slightly unfair one.

Change management in an AI adoption context is mostly about surfacing the right first question. Not "can you use AI more" — but "what do you do every week that's tedious and low-judgment?" That's the surface area. The rest tends to follow.

### The Staff Engineer Angle

The junior developer frame doesn't scale up. Working with a Staff Engineer who is fluent in agents isn't management — it's something closer to architecture by division of labour.

My Staff Engineer is the one who goes deep: building the VS Code agent skills that enforce our domain model at the IDE layer, designing the harness that routes tasks across an orchestrated agent pipeline, proposing which constraints should live in tooling rather than documentation. That work requires being inside the codebase, close to the execution layer. I'm not the right person to do it, and trying to be would slow us both down.

What I own is the surface those tools run against. The architectural constraints they need to enforce. The business rules that have to survive a compliance review. The context that makes the difference between a skill that guides an engineer toward the right pattern and one that confidently produces the wrong thing. When I write a clear problem statement or define the boundary between two bounded contexts, I'm not doing less than my Staff Engineer — I'm doing the upstream work their agent skills depend on.

The productive dynamic isn't "Director manages Staff Engineer who manages agents." It's closer to parallel execution with a shared contract: they build the harness; I define what the harness enforces. The constraint I document today is the linter rule they ship next week. The architectural decision I make clearly enough to write down is the one the IDE agent can surface at the right moment.

What I've learned to watch for is drift between those two layers — cases where I've held a constraint informally (it's obvious, everyone knows it) and it hasn't made it into the tooling. That gap is where the junior developer frame breaks down entirely. No amount of well-managed agent workflow compensates for a constraint that was never made explicit. That part is mine to fix.