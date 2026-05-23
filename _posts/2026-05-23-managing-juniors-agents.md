---
layout: post
title: "One Manager, Two Kinds of Junior: Human and AI"
date: 2026-05-23
---

# One Manager, Two Kinds of Junior

The most useful reframe I've found for working with AI agents is also the one that falls apart fastest: treat them like a junior developer.

It works because it sets the right operational stance. You wouldn't give a junior developer a vague ticket and walk away. You wouldn't merge their PR without review. You wouldn't assume silence means progress — in that context, silence usually means they're stuck or have gone somewhere unexpected and haven't told you. The same is true for agents, and for roughly the same reasons.

**Where it breaks: junior developers grow. Agents don't — not the same way.**

The investment in onboarding and feedback compounds over time with a human. With agents, the compounding happens at the tooling level — better grounding, better skill definitions, better constraints. You're not developing the agent; you're developing the system around it. That's a different kind of management, and it's worth naming the difference.

**How we structured permission to experiment.**

We run a guild model — a small group of senior engineers working in a dedicated R&D space, explicitly sandboxed from production. The brief: prove what's possible, retire findings back to current state, name the gaps. No pressure to ship. Permission to be wrong quickly.

What came back was instructive. The group built an agentic development workflow: a ticket arrives, one agent writes an implementation plan, a second writes the code, a third reviews it, a fourth stages the deploy. Each step has a human at the gate. Not because we don't trust the agents — because in a regulated environment, the human-in-the-loop isn't optional. It's the design.

**The comprehension problem is the one most teams aren't answering yet.**

What that workflow surfaces is a harder question: what does "the engineer owns the judgment" actually mean when output arrives faster than it takes to properly review it? I call this comprehension debt — producing work you can't fully reproduce, debug, or defend. It's not a laziness problem. It's an ownership problem, and it shows up at the verification step.

Getting that right is the actual engineering work of the agentic transition. The tooling is the easy part.

**On the management side: AI literacy isn't binary, and the adoption pattern is telling.**

I have engineering managers working on their own workflows in parallel — automating repository context, release administration, system health aggregation. Useful things, in use, not experimental.

The pattern I notice across both groups: the people who adopted AI without anxiety mostly started from a question, not a tool. They had something they were already frustrated by. The tool happened to fit. The people who are more cautious were often handed a tool and asked to find a use for it — which is a harder starting position and a slightly unfair one.

Change management in an AI adoption context is mostly about surfacing the right first question. Not "can you use AI more" — but "what do you do every week that's tedious and low-judgment?" That's the surface area. The rest tends to follow.

**What I haven't resolved.**

The junior developer frame breaks down at the senior level. A staff engineer working with an agent isn't managing a junior — it's closer to pair programming with a very fast, occasionally confident, sometimes wrong collaborator. That's a different relationship, and it probably needs its own model. We're working on it.

