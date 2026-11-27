---
layout: post
title: "What an AI agent needs to know before it can join your company"
date: 2026-11-27
description: "Notes from Databricks in Toronto, read alongside essays from a16z, Neo4j, LangChain and Block on shared knowledge, control and the manager's job"
---

I went to the Databricks event in Toronto on 17 November and came back with a few things I keep thinking about. I'm writing them up in case any of it is useful.

Picture hiring someone sharp who knows a lot about technology but has never worked at your company. They don't know what your metrics mean, which systems to trust, who can approve what, or why you made the calls you made. That's roughly where most AI agents are today. A lot of the day was about how to close that gap.

I don't use Databricks, so this isn't a pitch. Their way of framing the problem was useful, and a few articles I read afterwards filled in the rest. Most of the numbers below come from the vendors themselves, and I've said so where it matters.

## Where agents trip up today

The speakers kept saying the models are smart enough. What's missing is the stuff your best people just know: what a metric means, which source to trust, how you handle the odd case. Ali Ghodsi, Databricks' CEO, put it as AI having a context problem, not an intelligence problem.

The usual fix makes it worse. Each team builds its own agent and teaches it the business through its own prompt, search setup or tool. So one agent thinks "active customer" means one thing and another thinks it means something else. Neo4j, a graph database company, calls this **semantic duplication**, which just means the same definition copied into lots of places. The copies drift apart over time, nobody notices, and two agents give you different answers to the same question.

It's also worth keeping expectations in check. METR, an independent research group, ran a trial in early 2025 where experienced developers took 19% longer with AI tools on their own code, even though they thought they'd been 20% faster. Their February 2026 follow-up suggests newer tools probably do speed people up, but they couldn't say by how much. So people's own sense of time saved isn't a good measure.

## What Databricks showed

Databricks built the day around four words: context, control, cost and choice. An essay from a16z (a venture firm, and an early Databricks investor) puts it more usefully as four questions any setup for agents has to answer. I found these handy for thinking about any vendor, or about your own setup.

| The question | The C (or E) | Databricks' answer | What I'd ask |
| --- | --- | --- | --- |
| What's true? (the actual data) | **Choice**: any cloud, any model, open data formats | Their data platforms, so agents read data where it already lives | Are you copying data around to feed agents, or pointing them at the real source? |
| What does it mean? (definitions) | **Context**: the business meaning behind the data | Genie Ontology: a map of business terms. Some are approved by people; others the system picks up from how data is used. A ranking system called OntoRank decides which to trust | Who approves a definition, and what happens when two sources disagree? |
| What's allowed? (permissions) | **Control**: who and what can do what | Unity Catalog and Unity Gateway: one list of every model, agent and tool, each with its own permissions, budget and limits | Does it actually block an agent from doing something it shouldn't, or just log it afterwards? If it goes down, does everything stop or does everything get through? |
| Did it work? (results) | **Cost**, plus my **E for evaluation**: was the work any good, and what did it cost | Testing tools for agents, plus spend broken down by user, team, agent and model | Are you measuring cost per useful result, or just total spend? |

The E is my addition. Cost tells you what you spent, not whether the work was any good, and I think checking results is the step people are most likely to skip.

A few other things from the day stuck with me:

- Answers depend on who's asking, because the system only uses data you're allowed to see. Two people can ask the same question and get different answers. That makes testing and auditing trickier.
- You can cut costs by sending simpler work to cheaper models, trimming what goes into each request, and giving agents fewer tools. All of that can also lower quality, so it needs checking.
- Their suggested order for adopting all this was: get visibility of cost first, then put the controls in, then build agents for specific areas that pick up the rules already in place.

## Keeping the knowledge up to date

Nobody can write down everything about how a business works before they start, and anything written down goes stale if nobody looks after it. The three sources I read all land on roughly the same answer: let the system suggest things, and have people approve them.

- Databricks has its system pick up definitions from how people use the data, and gives priority to definitions people have approved.
- Neo4j has AI suggest definitions and how they map to real systems, and people sign off.
- Harrison Chase at LangChain (they make tools for building agents) adds the idea I liked most. The agents doing the work only *report* gaps and mistakes. A separate agent, which he calls a curator, makes the fixes on a schedule. If working agents edit the shared knowledge themselves while trying to finish their own tasks, it fills up with contradictions.

Chase also splits the knowledge into three kinds, which is a nice quick checklist for any team:

- **How we do things here** (he calls these skills)
- **What things mean**: definitions, policies, products, customers
- **Where to find current data** and how to get at it, so nobody has to copy it

Two things to watch. If the system gives you one best answer, a wrong answer looks exactly like a right one. And if the system trusts definitions more because they're used more, an early definition can become the default whether it's right or not. The shortcut to avoid is letting how often something is used stand in for someone actually approving it. Someone has to own the approved definitions. Neo4j's suggestion is that the teams who own an area own its meanings, and a platform team keeps the thing running.

## Who ends up with the advantage

The models themselves are becoming interchangeable. Databricks already switches between them depending on the task and the price. What builds up over time is a company's own record: its definitions, who's allowed to do what, and what happened when decisions were made, including the times a person stepped in and corrected the agent.

The a16z essay calls this the "sovereign firm" and uses an example I liked. Two banks rent the same AI model. One keeps track of what worked and where people overrode the agent. Over time it pulls ahead, and it keeps that lead even when it switches to a newer model.

A few catches:

- Everyone telling this story sells something in it. a16z invested in Databricks, Neo4j sells graph databases, and LangChain sells a place to store this kind of knowledge.
- "Switch provider and keep everything" is a goal, not something you can do today. Chase points out there's no standard format yet for this kind of knowledge, so it's not clear what you'd export it into. Databricks' own slide promised freedom from model vendors, not from Databricks.
- a16z themselves say owning the data isn't the advantage. Making better decisions faster than competitors is.

## What it might mean for managers

The a16z essay leans on an old idea from Herbert Simon, an economist: if a business keeps one shared memory, people can make more decisions locally. Part of what managers do today is pass information up and down. If a shared record holds the context, the people closest to the work need less of that.

Ghodsi added a caveat I think is important. He agrees with the direction, but says managers are still needed to develop people, set priorities and look after the team. You need fewer of them just to relay information. So it changes what managers spend their time on. It doesn't remove the role.

The three roles I'd seen in write-ups, individual contributors, people who own a specific outcome and player-coaches, come from Block. Jack Dorsey and Roelof Botha of Sequoia set them out in March 2026 as the plan for how Block will work. A directly responsible individual, or DRI, might own merchant churn in one segment for 90 days. Block says more than Ghodsi does: it needs no permanent middle layer of managers. It also says it's early, expects parts to break, and publishes no results, so for now this is a plan, not evidence.

Two shifts came up a lot:

- **Everyone ends up delegating.** Engineers already hand work to coding agents, check it and correct it. Each correction is something worth keeping, not just a fix.
- **Screens get cheap, the plumbing doesn't.** Speakers described building throwaway prototypes for lots of different user groups on one backend, trying them with a few people, then handing the one that works to engineering to build properly. The lasting work is in the backend, the data agreements between systems, the controls, and deciding what's worth building for real.

## A few things worth trying

None of these need Databricks.

1. **Find a definition that doesn't match.** Pick a term your team shares with another, like "active customer", and ask both systems the same question. If the answers differ, that's the problem in miniature.
2. **Write down where the knowledge lives for one workflow.** What does it need to know, where does each piece come from, and who owns it? The gaps you find are the ones an agent will hit.
3. **Keep the corrections.** When someone overrides an agent or fixes a report, note what they changed and why. That record is the valuable part.
4. **Measure results, not spend.** Cost per merged change or per resolved ticket tells you more than a monthly bill. If you cut costs, check quality didn't drop with them.
5. **Decide what stays with people.** Some decisions can't be undone. Name them, whatever the tools promise.
6. **Ask vendors the four questions above.** Especially whether you can take your knowledge with you, and whether their controls block things or only log them.

## Sources

Anything about what Databricks' products do comes from their docs and the slides I photographed. The accuracy figures are theirs. The bigger argument about how firms change is a16z's, and the three roles are Block's. The table of questions, the risks and the suggestions are my own take.

| Source | Who wrote it | Worth knowing |
| --- | --- | --- |
| [Databricks & the Future of the Firm](https://www.a16z.news/p/databricks-and-the-future-of-the) | Ben Horowitz and Michael McGuiness, a16z, 27 Oct 2026 | a16z led Databricks' Series A in 2013 |
| [How to build a knowledge factory](https://x.com/hwchase17/status/2124181216719151585) | Harrison Chase, LangChain | LangChain sells a place to store this knowledge |
| [The knowledge layer for enterprise AI](https://neo4j.com/blog/agentic-ai/enterprise-knowledge-layer/) | Jesús Barrasa, Neo4j, 20 Jul 2026 | Neo4j sells graph databases |
| [From Hierarchy to Intelligence](https://block.xyz/inside/from-hierarchy-to-intelligence) | Jack Dorsey (Block) and Roelof Botha (Sequoia), 31 Mar 2026 | Block describing its own plan; no results published |
| [Genie Ontology docs](https://docs.databricks.com/en/genie/genie-ontology) and [launch post](https://databricks.com/blog/announcing-ga-genie-ontology) | Databricks | Vendor material |
| [Genie One](https://www.databricks.com/blog/genie-one-ai-cowork-home-everyone) | Databricks | Vendor material; free-period dates |
| [Early-2025 AI and experienced developers](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) and [2026 update](https://metr.org/blog/2026-02-24-uplift-update/) | METR | Independent research group |
