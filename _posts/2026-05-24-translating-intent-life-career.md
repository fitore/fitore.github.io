---
layout: post
title: "Translating intent in real life and tech systems"
date: 2026-05-24
---
# The thing I've been doing my whole life finally has a name

I was building [Radian](https://radian-geometric-art.vercel.app) with Claude Code — a geometric art project — and a UI modal wasn't rendering fully on mobile. I asked Claude Code to debug it. What followed was a CSS debugging loop that nearly burned through my daily token limit: each fix producing a new variant of the same problem, each iteration technically reasonable, none of them working. I interrupted it and asked for a UI refactor instead. The modal rendered. Thirty seconds.

The model understood exactly what I asked. It didn't understand what I meant.

I'd been here before. Not with AI.

---

## Subtlety is relative

When I moved from the Balkans to the Middle East, I thought I knew how to communicate directly. I was wrong — but in a direction I hadn't anticipated.

In a culture where indirection can signal respect and careful phrasing carries relational weight, my communication style read as evasive. Too subtle. I was being precise in a register nobody was reading as precision. I recalibrated: said more explicitly what I meant, reduced the inference burden I'd been placing on the receiver.

Then I moved to Canada.

The same directness that had finally felt calibrated landed hard here. My PR reviews came across as blunt. Feedback that felt honest to me felt harsh to the developer receiving it. I wasn't wrong about the code. I was wrong about the message.

The insight that took me too long to name: *the same signal produces a different reading depending on the decoder.* I hadn't changed. The context had. Being perceived as too subtle in one place and too direct in another, while communicating with the same intent, is not a contradiction. It's just what translation actually is.

Translation isn't about the words. It's about what the receiver's frame will do with them.

---

## Systems speak in dialects

When you integrate two software systems, the semantic work is harder than the technical work. Two systems can share a field name and mean completely different things. One system's `status: closed` means the record is archived. Another's means the transaction failed. The schema maps. The meaning doesn't.

The real integration work is surfacing the implicit assumptions — the things each system never had to explain because everything in its environment already agreed. Nobody wrote them down because they were obvious. They are only obvious to the system that built them.

Translation here is not a linguistic problem. It's an ontological one. You're not converting words. You're finding where the world-models diverge.

---

## Mergers are integration at human scale

An acquisition is the same problem, larger and louder and wearing nicer clothes.

Two engineering organizations merge and discover they've been using the same words for different things for years. "Incident" means different things. "Done" means different things. "Ownership" — especially ownership — means different things. You surface this mid-sprint, usually, when something breaks and everyone is already stressed.

The technical integration is a project plan. The cultural translation is the actual work. You're not mapping fields — you're making explicit the assumptions each side had agreed never to examine, because they'd never had to.

I've been living a version of this right now — not across two companies, but across two disciplines that had been using the same vocabulary to mean different things long enough that nobody had noticed. Working with our Director of Data and a staff engineer, we kept running into the same friction: engineering and data had developed their own internal dialects for the same concepts. Customer. Event. State. The words matched. The models underneath them didn't.

The answer we've been building toward isn't a glossary. It's an ontology SDK: shared vocabulary made programmable, so the translation layer lives in the infrastructure rather than in someone's head or a Confluence page nobody reads after the second week.

The insight that pushed us there: documentation describes the gap. Code enforces the bridge. If translation depends on a human remembering to apply it, it will eventually fail.

*(I'm writing a longer post on the ontology work — the architecture, the tradeoffs, and what it revealed about where engineering and data actually diverge conceptually. [Read it here when it's up.](/blog/2026/04/30/merging-organizations/))*

This is, it turns out, precisely what I had been doing between the Balkans and the Middle East and Canada. The subject matter had scaled. The problem was structurally identical.

---

## The actual skill

The CSS debugging loop wasn't a Claude Code failure. It was a translation failure — mine. I had described the symptom accurately. I hadn't communicated the intent: *make this work on mobile, by whatever means*. The model optimized for the problem I named, not the outcome I needed. The moment I reframed the request — refactor rather than fix — the translation landed and the work resolved.

This is the current frontier of human-AI collaboration: not fluency with the model's capabilities, but knowing what your intent will lose in transit before you send it. Decomposing what you mean from what you said. The gap between the two is an engineering surface, not a nuisance.

It's also the same skill I've been building my whole career, just pointed at a new decoder.

In code review: naming the standard you're applying, not just the gap you're flagging — because the standard is the part the other person doesn't yet share.

In systems integration: surfacing implicit assumptions before you touch the schema — because the assumption is what you're actually mapping.

In a merger: treating cultural vocabulary as a first-class technical artifact — because the words are where the world-model differences hide.

In human-agent interaction: externalizing intent, not just writing prompts — because the model has no access to the six months of context you're holding.

The Balkans taught me directness. The Middle East taught me that directness is a spectrum and I wasn't standing where I thought I was. Canada taught me that my recalibration was still someone else's starting point. Every integration taught me that shared vocabulary doesn't mean shared meaning.

And now, working with AI systems that understand exactly what you say and miss what you mean — I find myself in familiar territory. A new decoder, a new frame, the same translation problem.

I've been training for this for a while. I just didn't know that's what it was called.
