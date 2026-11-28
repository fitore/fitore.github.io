---
layout: post
title: "What an AI agent needs to know before it can join your company"
date: 2026-11-27
description: "Notes from Databricks in Toronto, read alongside essays from a16z, Neo4j, LangChain and Block on shared knowledge, control and the manager's job"
---

Picture hiring someone sharp who knows a lot about technology but has never worked at your company. They don't know what your metrics mean, which systems to trust, who can approve what, or why you made the calls you made. That's roughly where most AI agents are today.

The argument I take from it runs like this. Models are becoming interchangeable, so what separates one company's agents from another's is what the company has accumulated: its definitions, its permissions, its exceptions, and the corrections people make when an agent gets something wrong. That knowledge stays useful only if it is governed, with owners, permissions and a way to check results. Once it is governed in one place, it also changes how decisions are distributed and what managers spend their time on.

These notes come from the Databricks event in Toronto on 17 November and from what I read afterwards: essays from a16z, Neo4j, LangChain and Block. I don't use Databricks, so this isn't a pitch. The day was aimed at the executives who set budgets rather than the people who do the work, so the inner workings stayed at a high level and vendor lock-in didn't come up. The essays filled in more of the mechanism and raised the lock-in question. Most of the numbers come from the vendors themselves, and I say so where it matters. Product detail is in the appendix.

## Where agents trip up today

The speakers kept saying the models are smart enough. What's missing is what your best people carry in their heads: what a metric means, which source to trust, how you handle the odd case. Ali Ghodsi, Databricks' CEO, put it as AI having a context problem rather than an intelligence problem.

The usual fix makes it worse. Each team builds its own agent and teaches it the business through its own prompt, search setup or tool, so one agent thinks "active customer" means one thing and another thinks it means something else. Neo4j, a graph database company, calls this **semantic duplication**: the same definition copied into many places. The copies drift apart, nothing raises an alarm when they do, and two agents give different answers to the same question.

The remedy that Databricks and Neo4j both point to is to define meaning once, in a shared layer, and to make someone responsible for it. The word they use for that layer is ontology: an agreed set of business terms and how they relate to each other and to the data. Neo4j puts ownership with the domain teams. They own what their terms mean, and a platform team keeps the layer running.

## Why the record becomes the advantage

Models are becoming interchangeable, and Databricks already routes between them by task and price. If the model is a component you swap, what carries over from one version to the next is the company's own record: its definitions, who's allowed to do what, and what happened when decisions were made, including the times a person stepped in and corrected an agent. Those corrections are the raw material of the record.

The a16z essay illustrates this with a hypothetical. Two banks rent the same model for credit decisions. One records only the prompt, the answer and the decision. The other also records the facts behind each answer, the human overrides and which decisions worked, and adjusts its policy as it goes. When a better model arrives, the second bank keeps its lead, because its record carries over to the new model.

The argument has limits. Everyone telling this story sells something in it: a16z led Databricks' Series A, Neo4j sells graph databases, and LangChain sells a place to store this kind of knowledge. "Switch provider and keep everything" describes a goal. Harrison Chase of LangChain points out that there's no standard format yet for this kind of knowledge, so it's not clear what you would export it into. Databricks' own slide promised freedom from model vendors, not from Databricks. And a16z themselves say that owning the data is not a moat on its own. The advantage comes from improving decisions and products faster than competitors can.

## Keeping the knowledge current

Nobody can write down how a business works before they start, and what is written down goes stale if nobody tends it. The three sources I read land on much the same loop, in which the system suggests and people approve, and each fills in a different part of it.

Databricks infers definitions from how people use the data and gives priority to the ones people have certified. Neo4j has language models propose definitions and how they map to real systems, and people ratify them. Chase adds the design rule I'd single out. The agents doing the work only *report* gaps and mistakes, and a separate agent, which he calls a curator, makes the fixes on a schedule. His reason is that agents which edit the shared knowledge while chasing their own tasks fill it with contradictions. It is the separation of duties that permissions give you elsewhere in a system, applied to what the company knows.

Chase also splits the knowledge into three kinds, which makes a quick checklist for any team:

- **How we do things here** (he calls these skills)
- **What things mean**: definitions, policies, products, customers
- **Where to find current data** and how to get at it, so nobody has to copy it

Two things to watch. The first is ranking. Systems like Genie Ontology rank the candidate definitions for a term and return the one they judge best. If the system returns one best answer, ranking is effectively the product, and a wrong ranking looks exactly like a right answer. The second is a reinforcing loop, in Donella Meadows' terms. Databricks' ranking counts popularity among its signals, so a definition used early can gain rank and get used more, whether or not it is right. Both are reasons for every approved definition to have a named owner.

## Four questions to ask of any setup

Databricks built the day around four words: context, control, cost and choice. The a16z essay frames the problem more usefully as four questions any setup for agents has to answer. Matching the questions to Databricks' four words is my own pairing. The questions work on any vendor's pitch, and on your own setup. The product names in the third column are Databricks' own; the appendix describes the ontology in more detail.

| The question | The C (or E) | Databricks' answer | What I'd ask |
| --- | --- | --- | --- |
| What's true? (the actual data) | **Choice**: any cloud, any model, open data formats (Delta, Iceberg) | Lakehouse and Lakebase, so agents query data where it already lives | Are you copying data around to feed agents, or pointing them at the real source? |
| What does it mean? (definitions) | **Context**: the business meaning behind the data | Genie Ontology: certified definitions plus snippets learned from usage, ranked by OntoRank | Who certifies a definition, and what wins when two sources disagree? |
| What's allowed? (permissions) | **Control**: who and what can do what | Unity Catalog and Unity Gateway: one registry for models, agents, tools and skills, with identity, budgets and guardrails | Does it actually block an agent from doing something it shouldn't, or just log it afterwards? If it goes down, does everything stop or does everything get through? |
| Did it work? (results) | **Cost**, plus my **E for evaluation**: was the work any good, and what did it cost | Evaluations in Agent Bricks, plus spend broken down by user, team, agent and model | Are you measuring cost per useful result, or just total spend? |

The E is my addition, because I think checking results is the step people are most likely to skip. A cost figure records what you spent and says nothing about whether the work was any good. Databricks' suggested order for adoption had no separate step for it, which is part of why I added it.

## What it might mean for managers

The a16z essay leans on an old idea from Herbert Simon: if a business keeps one shared record, each decision point can act independently, and the system reconciles those actions against the record. Part of what managers do today is pass information up and down. If the record carries that context, the people closest to the work need less of it relayed, and their decisions can still be checked afterwards.

Block's essay, "From Hierarchy to Intelligence" by Jack Dorsey and Roelof Botha, is the most developed version I read. Block is remote-first, so it records decisions, code, plans and progress as machine-readable artifacts, and a system holds the picture managers used to relay. Block replaces the relay with three roles: individual contributors who build and operate the technology, directly responsible individuals (DRIs) who own a cross-cutting outcome (in its example, merchant churn in one segment for 90 days), and player-coaches who keep building while they develop people. It says there is "no need for a permanent middle management layer."

The a16z essay reports Ghodsi's view of Dorsey's piece. He agrees in principle but questions how far hierarchy will shrink, because developing people, setting priorities and noticing when someone is unhappy still need human attention. Block gives priorities to DRIs and people to player-coaches, while Ghodsi gives both to managers. They name the same remaining work and differ on who does it. Block also says it is early, expects parts to break and publishes no outcome data, so for now this is a plan from a company describing itself.

## A few things worth trying

None of these need Databricks.

1. **Find a definition that doesn't match.** Pick a term your team shares with another, like "active customer", and ask both systems the same question. If the answers differ, you have semantic duplication between two teams.
2. **Write down where the knowledge lives for one workflow.** What does it need to know, where does each piece come from, and who owns it? The gaps you find are the ones an agent will hit.
3. **Keep the corrections.** When someone overrides an agent or fixes a report, note what they changed and why. Engineers already do this with coding agents, handing work over, checking it and correcting it, and that record is what carries over when the model changes.
4. **Measure what the work produced.** Cost per merged change or per resolved ticket tells you more than a monthly bill. If you cut costs, check that quality didn't drop with them.
5. **Decide what stays with people.** Some decisions can't be undone. Name them, whatever the tools promise.
6. **Ask vendors the four questions above.** The lock-in question didn't come up in Toronto, so ask whether you can take your knowledge with you. Ask whether their controls block things or only log them, and how quickly a revoked permission reaches their search indexes.

*Co-written with Claude.*

## Appendix: Databricks in more detail

**How Genie Ontology is built.** It combines a modelled layer, drawn from what already sits in Unity Catalog (metric views, domains and pages), with a learned layer of snippets picked up from dashboards, SQL queries and notebooks. Certified definitions take priority over learned ones. OntoRank orders candidates by source authority, certification, the expertise and relevance of the people behind them, popularity and recency. Permissions are applied separately: results respect what the asker is allowed to see.

**Answers depend on who's asking.** Because the system draws only on data the asker can see, two people can put the same question and get different answers. That makes testing and auditing harder. It also makes the speed of permission changes matter: how quickly a revoked permission reaches a search index is an open question, since a stale index could show someone data they've lost access to.

**Cutting cost.** Speakers described routing simpler work to cheaper models, including open-weight ones, compacting and trimming what goes into each request, pruning the tools an agent can see, and caching. Each of these can also lower quality, which is the case for tying every one to an evaluation.

**The suggested adoption order.** Cost visibility first, then governance, then Agent Bricks, which builds domain agents that inherit the policies and access controls already in place. Agent Bricks includes evaluations, but in the order as I noted it, checking results isn't a step of its own.

**Prototypes get cheap.** Speakers described building throwaway prototypes for different user groups on one backend, trying them with a few people, and handing the one that works to engineering. The lasting work is in the backend, the data agreements between systems, the controls, and deciding what is worth building for real.

**Cautions on the numbers.** Databricks' accuracy claims come from its own benchmarks. The 91% pass rate in the Genie Ontology launch post comes from a benchmark Databricks built with Turing, simulating a workspace for a fictional energy supplier. The 84.5% figure is from the day's slides. Whether either holds outside those benchmarks is open. Genie One is free to users through 31 January 2027, so today's costs flatter the economics, and I haven't seen pricing for the ontology.

## Sources

Anything about what Databricks' products do comes from their docs, my notes and the slides I photographed. The accuracy figures are theirs. The bigger argument about how firms change is a16z's, and the three roles are Block's. The pairing of questions with Databricks' four words, the risks and the suggestions are my own take.

- [Databricks & the Future of the Firm](https://www.a16z.news/p/databricks-and-the-future-of-the), Ben Horowitz and Michael McGuiness, a16z, 27 Oct 2026. a16z led Databricks' Series A in 2013.
- [How to build a knowledge factory](https://x.com/hwchase17/status/2124181216719151585), Harrison Chase, LangChain. LangChain sells a place to store this knowledge.
- [The knowledge layer for enterprise AI](https://neo4j.com/blog/agentic-ai/enterprise-knowledge-layer/), Jesús Barrasa, Neo4j, 20 Jul 2026. Neo4j sells graph databases.
- [From Hierarchy to Intelligence](https://block.xyz/inside/from-hierarchy-to-intelligence), Jack Dorsey (Block) and Roelof Botha (Sequoia), 31 Mar 2026. Block describing its own plan; no results published.
- [Genie Ontology docs](https://docs.databricks.com/en/genie/genie-ontology) and [launch post](https://databricks.com/blog/announcing-ga-genie-ontology), Databricks. Vendor material.
- [Genie One](https://www.databricks.com/blog/genie-one-ai-cowork-home-everyone), Databricks. Vendor material; free-period dates.
