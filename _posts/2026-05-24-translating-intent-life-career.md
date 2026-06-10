---
layout: post
title: "The Same Translation Problem: Life and Technology"
date: 2026-05-24
---

### The Thing I've Been Doing My Whole Life Finally Has a Name

I was building [Radian](https://radian-geometric-art.vercel.app) with AI, a geometric art project, and a UI modal wasn't rendering properly on mobile. I asked Claude Code to debug it. What followed was a CSS debugging loop that nearly burned through my daily token limit: each fix producing a new variant of the same problem, each iteration technically reasonable, none of them working. Eventually I interrupted it and asked for a UI refactor instead. The modal rendered in ~30 seconds. It understood exactly what I asked for but it didn't understand what I meant.

I'd been here before. Not with AI.

### Translation Isn't About Words

When I moved from the Balkans to the Middle East, I thought I knew how to communicate directly. I was wrong, but in a direction I hadn't anticipated.

In a culture where indirection can signal respect and careful phrasing carries relational weight, my communication style read as evasive. Too subtle. I was being precise in a register nobody was reading as precision. I recalibrated: said more explicitly what I meant and reduced the inference burden I was placing on the receiver.

Then I moved to Canada.

The same directness that had finally felt calibrated landed hard here. My PR reviews came across as blunt. Feedback that felt honest to me felt harsh to the developer receiving it. I wasn't wrong about the code, yet I was wrong about the message delivery.

The insight that took me too long to name is that the same signal produces a different reading depending on the decoder. I hadn't changed. The context had. Being perceived as too subtle in one place and too direct in another, while communicating with the same intent, isn't a contradiction. It's just what translation actually is.

Translation isn't about the words. It's about what the receiver's frame will do with them.

### Systems Speak in Dialects

The same pattern shows up in software systems.

When you integrate two systems, the semantic work is usually harder than the technical work. Two systems can share a field name and mean completely different things. One system's `closed` means the record is archived. Another's means the transaction failed. The schema maps but the meaning doesn't.

The real integration work is surfacing the implicit assumptions — the things each system never had to explain because everything around it already agreed. Nobody wrote them down because they were obvious. They were only obvious to the system that built them.

Translation here isn't a linguistic problem. It's an ontological one. You're not converting words. You're finding where the world models diverge.

### Mergers Are Integration at Human Scale

An acquisition is the same problem, larger and louder and wearing nicer clothes.  ([see ontology in a merger post.](/blog/2026/04/30/merging-organizations/))

Two engineering organizations merge and discover they've been using the same words for different things for years. Incident means different things. Done means different things. Ownership, especially ownership, means different things. You usually discover this in the middle of something important, when a system breaks and everyone is already stressed.

The technical integration is a project plan. The cultural translation is the actual work.

I've been living a version of this recently, not across companies but across disciplines. Working with our Director of Data and a Staff Engineer, we kept running into the same friction: engineering and data had developed their own internal dialects for the same concepts. Customer. Event. State. The words matched. The models underneath them didn't.

The answer we've been building toward isn't a glossary. It's a shared vocabulary made programmable, so the translation layer lives in infrastructure rather than in someone's head or a Confluence page nobody reads after the second week. The insight that pushed us there was simple: documentation describes the gap. Code enforces the bridge.

The more we worked on it, the more familiar the pattern became. This was the same thing I'd been doing between the Balkans, the Middle East, and Canada. The subject matter had changed. The problem hadn't. 

### The Actual Skill

Looking back, the CSS debugging loop wasn't a Claude Code failure. It was a translation failure — mine.

I had described the symptom accurately. I hadn't communicated the intent: make this work on mobile, by whatever means necessary. The model optimized for the problem I named, not the outcome I needed. The moment I reframed the request — refactor rather than fix — the translation landed and the work resolved.

I think this is one of the emerging skills of human-AI collaboration. Not fluency with the model's capabilities, but understanding what your intent will lose in transit before you send it. Separating what you mean from what you said. The gap between those two turns out to be an engineering surface rather than an inconvenience.

The pattern shows up everywhere. In code review, the challenge is naming the standard you're applying rather than only the gap you're flagging. In systems integration, it's surfacing assumptions before touching schemas. In mergers, it's treating vocabulary as a first-class technical artifact. In human-agent interaction, it's externalizing intent rather than simply writing prompts.

The Balkans taught me directness. The Middle East taught me that directness is a spectrum and I wasn't standing where I thought I was. Canada taught me that my recalibration was still someone else's starting point. Every integration taught me that shared vocabulary doesn't imply shared meaning.

And now, working with AI systems that understand exactly what you say and still miss what you mean, I find myself in familiar territory.

A new decoder. A new frame. The same translation problem.


--- 


![Translating Intent](/images/translating-intent.png)
