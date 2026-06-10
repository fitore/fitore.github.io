---
layout: post
title: "What a Fintech Merger Actually Tests: Foundations, Revealed Under Load"
date: 2026-04-30
info: (images co-created with AI)
---

We’re in the middle of a merger. Two engineering organisations, two toolchains, and more than one answer to questions that used to feel obvious: where does customer data live, who owns it, and which system gets the final say. The interesting thing isn’t the integration work itself. It’s discovering which decisions made years ago are still holding, and which ones were never really decisions at all—just the path of least resistance repeated often enough that it started to look like architecture.

A merger is a stress test. Like most stress tests, it reveals foundations that were largely invisible while everything lived inside a single environment. The things that looked settled suddenly need explaining. Assumptions that were never written down become important. Systems that appeared coherent start exposing the compromises that held them together. The technical integration is usually straightforward compared to the work of making those assumptions explicit.

The two diagrams below are an attempt to make those foundations visible. The first shows the target architecture: two organizations converging on a shared ontology that defines meaning once and generates governed surfaces for applications, analytics, and AI agents alike. The second shows the adoption path. One thing mergers repeatedly teach is that you can't automate what you haven't defined, and you can't govern what you don't own. The order matters more than the tooling.

![Ontology SDK Architecture](/images/ontology-sdk-architecture.png)

## Shared Meaning Before Shared Systems

The first thing that gets tested is whether there is a shared definition of the domain.

Some teams call this a canonical domain model. Others call it an ontology. The label matters less than the outcome: a shared understanding of what the business actually is. A schema can tell you that a Customer has a name, address, and identifier. An ontology tells you what a Customer is, what states it can move through, what relationships it can participate in, and which actions are allowed at each stage. The distinction sounds academic until two organisations try to merge their systems and discover they have been using the same word to describe different things.

When those definitions exist, a merger becomes the work of reconciling two implementations of the same ideas. Difficult, but ultimately tractable. When they don’t, you discover something more fundamental: the disagreement isn’t about implementation. It’s about meaning.

One pattern I keep seeing is what I think of as the Golden Source Myth: the belief that somewhere in the organisation there is a single true representation of a business entity waiting to be discovered. In practice, there usually isn’t. There are multiple valid representations, each optimized for a different purpose. A customer in a CRM, a customer in a lending platform, and a customer in a ledger all serve different needs and carry different constraints. What keeps them coherent is not a database. It’s shared meaning.

## Audit Is Either Structural or It Isn’t

The second thing a merger tests is whether audit was designed in or added later.

In regulated environments, writes are rarely just technical operations. They’re business actions with compliance implications attached to them. When systems are built around durable events and append-only history, audit tends to emerge naturally because the architecture already preserves the story of what happened. When they aren’t, audit often becomes a separate process layered on afterward. It works, but usually at the cost of complexity, manual effort, and institutional memory. The difference becomes obvious the moment someone asks not what the system looks like now, but how it got here.

## Seams Are What Let You Change

The third thing a merger tests is whether you have seams.

The systems that tend to survive mergers well aren’t necessarily the newest or most elegant. They’re the ones with clear boundaries. Bounded contexts. Explicit ownership. Event-driven interfaces. Financial ledgers separated from operational workflows. Not because these are fashionable architecture patterns, but because they provide places to cut. Seams matter when organisations change. They matter when systems split. They matter when ownership moves. A surprising amount of architecture only works as long as nobody touches it.

Architecture is the easy part to draw. Adoption is usually the harder problem. Most organizations don't fail because they couldn't imagine a target state; they fail because they couldn't reach it incrementally while continuing to deliver. That's why the second diagram focuses on sequencing rather than technology.

![Ontology SDK Adoption Path](/images/ontology-sdk-adoption-path.png)

## The Newest Version of the Same Test

The newest version of this test is the agent layer.

One thing I’ve found interesting is that the conversations around agents expose many of the same questions the merger exposes: ownership, authorisation, auditability, and source of truth. The agent itself isn’t really the new thing. It’s another consumer of the same foundations. If the domain model is unclear, the agent inherits that ambiguity. If ownership is fuzzy, the agent inherits that confusion. If audit is missing, the agent simply accelerates the problem. Strong foundations make agents safer. Weak foundations make agents more revealing. Which may be their most useful property.

The lesson I’ve taken from the merger isn’t really about mergers. It’s that foundations remain invisible until something applies pressure. Growth does it. Regulation does it. Reorganisations do it. Mergers do it. Increasingly, agents do it too. The question worth asking before any of those arrive is simple: if you had to split this system in two tomorrow, where are the seams? If you can’t answer that quickly, you may not have an architecture. You may have a history.


---



![Unified Platform North Star](/images/unified-platform-north-star.png)
