# Where We've Been, What We've Learned, and Why I'm More Convinced Than Ever

**To:** All of Eventual
**From:** Sammy
**Date:** February 27, 2026

---

## Let me start with the truth

The last two months have been a lot. We've changed direction multiple times. We've sprinted hard, paused, regrouped, and sprinted again. I know morale has taken a hit, and I'm not going to pretend otherwise. And I know you're watching other AI companies find traction while we've been searching for ours. I see it too.

If you're feeling tired, uncertain, or frustrated, that's not a failure of commitment. It's a reasonable response to moving through genuine ambiguity at speed. I want to acknowledge that directly, because you deserve honesty about where we've been before I ask you to come with me to where we're going.

Last month I shared what we learned from the hackathon. This memo picks up the story from there. Some context will overlap because the arc only makes sense as a whole, but the point isn't to relitigate. It's to show where the journey has taken us since.

---

## Daft Cloud: listening to the market

At the start of the year, our commercial product was Daft Cloud, a managed ingestion tool for AI teams. The thesis was clear: AI teams need to process massive amounts of unstructured data for embeddings, indexing, and extraction. We'd built the best engine for that in Daft, and Daft Cloud was going to be how we commercialized it.

Then the signals started piling up.

I remember sitting at dinner with the engineering team at Harvey, one of the most sophisticated AI companies in the world, and hearing them say that their data ingestion pipeline had been stable for a while. It was a solved problem for them. What kept them up at night was **search reliability and quality**. Not ingestion. Not embeddings. Search.

Meanwhile, our sales pipeline was getting smaller, not bigger. And in conversation after conversation with prospects, we kept hearing the same thing: the cost of embeddings and AI extraction was tiny compared to the token generation path, often by an order of magnitude. We were optimizing something that didn't move the needle for our customers.

We had to make a call. The road we were on was getting narrower while the opportunities around us were growing faster. So we made the hard decision to acknowledge that Daft Cloud in its current commercial form wasn't where the market needed us.

That wasn't failure. That was listening.

---

## The hackathon: exploring without a map

In January, we decided to run a company-wide two-week hack sprint focused on agents. The bet was that our expertise in large-scale data systems could translate into real value for teams building AI agents. We just needed to figure out where.

We went broad deliberately. Teams explored agent observability, knowledge retrieval, agentic search, data connectors, and more. We focused on exporting and working with our existing data, building prototypes like Loup and agentic search that showed we could move fast when pointed at a target.

But here's what I owe you honesty about: **the sprint felt scattered, and the ending was anticlimactic.** There was no crisp "here's what we do next" moment in the final presentations. I know many of you walked out feeling a "now what?" that I should have done more to address.

Jay and I didn't do a good enough job sharing our context and learnings during the hackathon. I own that. We were deep in customer conversations and exploring hypotheses, and we didn't bring the team along with us well enough. That's on me as a leader, and I've learned from it.

What the hackathon did give us, and this is genuinely important, was signal. We learned that agents are **context-starved**. Retrieval is the bottleneck, not generation. Access control across third-party data is unsolved. And "knowledge synthesis" as an abstract concept is too vague to build against, but fast, relevant, specific search is concrete and measurable.

We'd been hearing this from customers before the hackathon, too. Cursor told us that outdated context "decreases capability by confusing the model." Rosebud said their RAG pipeline "did not work at all." Wordware described semantic search as "probabilistic, noisy" and a source of context pollution. The through-line was consistent: models are only as good as the context you feed them, and nobody had a good answer. Those conversations are what pushed us toward knowledge in the first place.

During the hackathon, we saw our agents do better with more context. But our internal knowledge was small enough that we could just give it all to the agent. The context problem only becomes acute at B2B2B or enterprise scale. That realization is what pointed us toward the search sprint.

These weren't obvious truths before the sprint. We earned them.

---

## The search sprint: discipline over comfort

Coming out of the hackathon, we carved out a team and launched a focused search sprint. The hypothesis: build a B2B2B search product that would enable agent builders to connect to their customers' data. A context platform for the agent ecosystem.

We ran two tracks in parallel. On the technical side, we pushed hard to understand where we could genuinely add value to search: latency, quality, authorization, deep search capabilities. We wanted to know what knobs we had at our disposal.

On the market side, Jay and I talked to as many potential customers as we could. We needed to answer one question: **is the pain strong enough?**

Here's what we found.

Technically, we learned a lot. Authorization had no real status quo to beat, and we believed we could build something better. We had conviction we could compete on performance and build the kind of deep, pareto-optimal search that most teams can't build themselves.

But we also hit a wall that taught us something crucial. We were running evals on Wikipedia and, frankly, we'd built a really good trivia bot. Without narrowing in on a specific domain and a specific job function, it was nearly impossible to show real value. Search quality is only meaningful when it's measured against a real person's real workflow. Generic search demos don't move anyone.

And the market reinforced this: there aren't enough customers with strong enough pain in the B2B2B connector space right now. Companies building agents are building their connectors in-house specifically because search quality over those connectors is so crucial to their product. They can't afford to outsource it to a generic platform.

We even had design partners who were willing to pay. We said no. Because we didn't believe the pain was strong enough to sustain a real business. Saying no to interested partners, to potential revenue, because the market signal isn't right is one of the hardest things a startup can do. We did it because we'd rather be honest about what we're seeing than comfortable with what we're hearing.

The biggest takeaway from the search sprint: **you have to pick a specific pain for a specific person.** Not "better search for agents." Better search for *whom*, doing *what*. That realization is what led us to where we are now.

---

## What we learned: the blessings in the bruises

Step back and look at the arc. From Daft Cloud to the hackathon to the search sprint to where we are now, that's four major learning cycles in about eight weeks.

Most startups take 12 to 18 months to learn what we learned in two. That speed of learning is not just something that happened to us. It's a capability. It's one of our genuine competitive advantages, and it came at a cost that you all paid. I want to honor that.

Here's what we now know with conviction:

**We know where value isn't.** "Indexing but easier" is not a wedge. Generic data connectors aren't defensible. RAG-as-a-product has market headwinds. These aren't guesses. They're conclusions we tested against real customers and real market dynamics.

**We know where value IS.** Deep, specific search. Outcomes, not infrastructure. Problems where search quality directly drives revenue. The market is screaming for this. Not in the abstract agent-builder layer, but in concrete workflows where getting the right information to the right person at the right time changes outcomes.

**Our skills compound.** The data infrastructure expertise we built with Daft, the search capabilities we developed during the sprint, the customer intuition we sharpened through dozens of conversations. None of it was wasted. Every piece of it feeds directly into what we're building now.

**We earned clarity the hard way.** We didn't guess our way to this point. We explored, we built, we tested, we talked to customers, and we eliminated. That's more valuable than any amount of whiteboard strategy.

---

## Where we are now: Search for GTM

Here's what GTM looks like today. A sales rep researching a prospect opens ten tabs: LinkedIn, the company blog, Crunchbase, G2, Twitter. They spend 30 to 45 minutes assembling a picture that's outdated by next week. That's just one account.

GTM depends on timing and context. Agentic tools are getting really good at working with internal systems: CRM, email, call recordings. But the bottleneck is increasingly external context: signals from the world that tell you *when* to reach out and *what* to say. We're building a search engine that delivers that external context. Deep people and company intelligence, not generic firmographics from a static database. The kind of signal-rich, context-aware search that the best GTM engineering teams have been building internally.

Jay, Colin, and I have been building for four days. It's early, genuinely early, and I don't want to oversell what we have. But what I can say is that the conversations feel different. Not politely interested. Not "that's cool, keep me posted." Different in a way that we haven't felt before. People feel this pain.

The thesis is straightforward: the best sales teams in the world are already building this capability internally because it's that important. Give someone Claude Code or an AI agent with the right data and the right search, and a single person becomes a one-man army. We're building the product that makes that possible for everyone.

This is where our search expertise, our infrastructure, and our relentless learning over the last two months all converge.

---

## Daft: the foundation

I want to be clear about something: **Daft is not going away. Daft is the foundation.**

Some of you joined this company to build the engine that would replace Spark. That ambition shaped what Daft became, and the technical foundation it gave us is what makes everything we're doing now possible. Where Daft goes from here is a story we'll write together as we learn what this product demands.

Apple and ByteDance depend on Daft. That's not theoretical validation. That's real, important, deployed-in-production work. The team that continues to build and maintain Daft is doing some of the most technically impressive systems work in the industry, and our customers depend on you.

And there's a second truth that matters just as much: **Eventual runs on Daft.** To build a GTM search engine that delivers deep people and company intelligence, we need to process and index massive amounts of unstructured data from across the web. Think LinkedIn profiles, blog posts, conference talks, GitHub activity, press releases, job postings, SEC filings, all at scale. That is a large-scale unstructured data processing problem, and Daft is the engine that makes it possible. The technical challenges here are real: entity resolution across messy web data, deduplication, extraction at scale, and doing all of it fast enough to power a product people depend on daily. These are hard distributed systems problems, and they're ours to solve. Every improvement to Daft's performance, reliability, and scale directly improves the quality and speed of Eventual's search product. The work you do on Daft isn't adjacent to what we're building. It's underneath it.

Both of these things are true, and both of them matter.

---

## What's next

**Immediate structure:** Jay, Colin, and I are building Eventual full-time, targeting a demo next week. The Daft team, under Varun's leadership, continues driving Daft forward with clear priorities: support Eventual, then our key customers (Apple, ByteDance), then the broader community. As Eventual grows and the infrastructure requirements deepen, this structure will evolve. This is a starting point, not a permanent partition.

**How we stay connected:** Every Friday at eng wrap-up, the product team will demo what we built that week and where we're headed next. Infrastructure needs will surface naturally from those demos, and the Daft team picks them up as priority work. You'll see the product take shape in real time, and your work will be directly informed by what we're learning from users. If you're uncertain about how your work connects to where we're headed, ask. The door is open.

**Financial position:** We have 3+ years of runway. In a world changing this fast, the biggest risk we can take is not taking more risks, especially when we have the room to do it.

---

## One last thing

This has been the hardest stretch of my time as a founder. But I'd rather be here, having earned clarity through real work and real honesty, than still guessing. And I'd rather be on this team, with people who can sprint through uncertainty and come out sharper, than anywhere else.

We move fast. We learn honestly. We don't settle. That's who we are. And that's why I believe what's ahead of us is bigger than anything behind us.

— Sammy
