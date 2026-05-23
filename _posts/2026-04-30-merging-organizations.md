---
layout: post
title: "What a Merger Actually Tests"
date: 2026-04-30
---

# What a Merger Actually Tests

We're mid-merger. Two engineering organisations, two toolchains, two different answers to the question: where does customer data live, and who owns it?

The interesting thing isn't the integration work itself. The interesting thing is which decisions made years ago are still holding — and which ones were never really decisions. Just the path of least resistance, repeated until it looked like architecture.

A merger is a stress test. And foundations, in my experience, are the work nobody wants to fund upfront because they look like overhead until the moment they aren't.

**The first thing that gets tested: whether you have a shared definition of the domain.**

A canonical domain model isn't a documentation exercise. It's a contract — a single governed definition of what "customer" means, what "account" means, what a "transaction" is versus a "movement" versus a "posting." Every team is a consumer of this contract, not an author of it.

When you have it, merging two organisations means reconciling two implementations of the same contract. Hard, but tractable. When you don't, you're not reconciling implementations — you're discovering mid-stream that you never agreed on the thing itself. That's a different kind of problem.

**The second thing: whether audit was designed in or bolted on.**

In a regulated environment, every mutation is a regulated action. The compliance trail isn't something you layer on after the system works — it's the event log, queryable and durable, that the system is built on. When that's true from the start, audit is an architectural property. When it isn't, it becomes someone's full-time job, usually after an examination.

**The third thing: whether you have seams.**

The things that tend to survive reorgs and mergers are bounded contexts with clear ownership, event-driven interfaces between services, and a data layer where the financial ledger is genuinely separate from everything else. Not because these are fashionable choices — because they give you seams. Seams are where you cut when you need to.

The things that don't survive: shared databases with implicit contracts, monolithic authentication bolted onto a single org structure, and "we'll document the domain model later." A classic, and always technically true.

**What I'm watching now: the agentic layer as the newest version of this test.**

We've added an agent channel to our architecture — same authorisation model, same audit trail, same idempotency requirements as every other channel. It's not a shortcut. It's a consumer of the same governed path, and that was only possible because the governed path existed.

If the foundations aren't there, agents don't make it better. They make it faster to find out.

The question worth asking before the merger, not after: if you had to split this system in two tomorrow, where are the seams? If you can't answer that quickly, you may not have an architecture. You may have a history.

---
*[Architecture diagram — Unified Platform North Star]*
