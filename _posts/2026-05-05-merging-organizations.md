---
layout: post
title: "What a Merger Actually Tests - Ontology to the Rescue"
date: 2026-04-30
info: (images co-created with AI)
---

We're mid-merger. Two engineering organisations, two toolchains, two different answers to the question: where does customer data live, and who owns it?

The interesting thing isn't the integration work itself. The interesting thing is which decisions made years ago are still holding — and which ones were never really decisions. Just the path of least resistance, repeated until it looked like architecture.

A merger is a stress test. And foundations, in my experience, are the work nobody wants to fund upfront because they look like overhead until the moment they aren't.

### The first thing that gets tested: whether you have a shared definition of the domain.

A canonical domain model, aka Ontology, isn't a documentation exercise. It's a contract: a single governed definition of what "customer" means, what "account" means, what a "transaction" is versus a "movement" versus a "posting." Every team is a consumer of this contract, not an author of it.

The subtlety most teams miss: that contract needs to define *meaning*, not just shape. A schema tells you what fields exist. An ontology tells you what a Party actually is — what states it can be in, who is authorised to move it between them, and what the Party is called at each stage: Lead, Applicant, Tax Subject, Consent Holder, Account Owner. Same human. Five governed states. Every system models the slice it needs; the ontology is what makes those slices coherent.

When you have it, merging two organisations means reconciling two implementations of the same contract. Hard, but tractable. When you don't, you're not reconciling implementations — you're discovering mid-stream that you never agreed on the thing itself. This is a recognisable pattern. I think of it as the Golden Source Myth: the idea that there is one true version of an entity, if only you could find it. There isn't. There are multiple valid representations, each serving a different purpose, and the only thing that holds them together is a shared ontology.

### The second thing: whether audit was designed in or bolted on.

In a regulated environment, every mutation is a regulated action. Current state is a projection of the log — not the source of it. When that's true from the start, the compliance trail is an architectural property: the event log, queryable and durable, is what the system is built on. When it isn't, audit becomes someone's full-time job, usually after an examination.

### The third thing: whether you have seams.

The things that tend to survive reorgs and mergers are bounded contexts with clear ownership, event-driven interfaces between services, and a data layer where the financial ledger is genuinely separate from everything else. Not because these are fashionable choices — because they give you seams. Seams are where you cut when you need to.

The things that don't survive: shared databases with implicit contracts, monolithic authentication bolted onto a single org structure, and "we'll document the domain model later." A classic, and always technically true.

### What I'm watching now: the agentic layer as the newest version of this test.

We've added an agent channel to our architecture — same authorisation model, same audit trail, same idempotency requirements as every other channel. That was only possible because the agent tool surface is generated from the same ontology as every other API surface. Not a separate AI path. Not a shortcut. A consumer of the same governed contract, same as the mobile app.

If the foundations aren't there, agents don't make it better. They make it faster to find out.

The question worth asking before the merger, not after: if you had to split this system in two tomorrow, where are the seams? If you can't answer that quickly, you may not have an architecture. You may have a history.

---
![Unified Platform North Star](/images/unified-platform-north-star.png)
