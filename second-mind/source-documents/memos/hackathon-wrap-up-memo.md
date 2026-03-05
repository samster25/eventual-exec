# Hack Sprint Wrap-Up: What We Did, What We Learned, and Where We Go From Here

**To:** All of Daft
**From:** Sammy
**Date:** February 2026

---

## Why We Did the Hack Sprint

Two weeks ago, we made the call to pause our regular work and run a company-wide hack sprint focused on agents. The reasoning was straightforward: the market is moving fast toward agentic workflows, and we have a genuine unfair advantage in large-scale unstructured data systems. We wanted to explore whether that advantage could translate into real value for teams building AI agents.

We went broad on purpose. Teams explored agent observability, knowledge retrieval, evals, agentic search, data connectors, and more. Jay and I spent the sprint talking to customers and potential customers to find where we might see genuine pull.

## What Happened (Honestly)

About a week in, it became clear we were exploring without a sharp enough target. We didn't have a single metric we were trying to move, and without that anchor, energy naturally diffused. We tried to course-correct by restructuring the sprint into something more like an engineering sprint, but the core issue remained: we were searching for signal without a clear hypothesis to validate.

The final presentations felt anticlimactic because there wasn't a crisp "here's what we do next" moment. I want to acknowledge that directly. That's on me and the leadership team. We asked you to sprint hard and didn't give you a finish line.

I also want to acknowledge something else I've been hearing: some of you aren't sure what we're doing or where the company is headed. That uncertainty is reasonable given the last few weeks. I want to address it head-on.

## What We Actually Learned

The sprint wasn't a waste. We now have significantly more clarity than we did two weeks ago:

- **We know where we can provide value.** Customer conversations during the sprint consistently pointed to two areas of real pain: upstream data sync from platforms like OneDrive, SharePoint, Slack, and Notion (privacy-preserving and reliable), and downstream outcome delivery, where teams don't just want a pipeline or a vector DB but a better AI system end-to-end.

- **We know where we can't.** "Indexing but easier" is not a wedge. Embedding compute is cheap, teams have good-enough solutions, and the market narrative has moved past "RAG as a product." We confirmed this again during the sprint.

- **"Knowledge synthesis" is vague; fast, relevant search is concrete.** We explored the idea of synthesizing organizational knowledge for agents and found the problem too loosely defined to build against. What *did* work was empowering agents with fast, relevant search so they can navigate third-party data effectively. The value is in the search layer that understands datasources itself, not in some abstract notion of "knowledge."

- **We need our own measurable metrics, not downstream proxies.** Early in the sprint we tried to judge our work using end-customer outcomes like agent task-completion rates and support evals. This made it nearly impossible to isolate our impact or demonstrate value without a deep integration. Going forward, whatever we build needs to be measurable on its own terms: P99 latency, search recall, search quality, time to ingest. Metrics that a customer can see move without wiring us into their entire stack.

- **Agent access control is a real, hard, unsolved problem.** Right now, giving an agent access to data is largely all or nothing. There's no good way to scope what an agent can see or do across third-party data sources. We saw this firsthand in the sprint and it resonated in customer conversations. Guiding and locking down agents is a genuine gap in the ecosystem.

- **We built working prototypes** (Loup, agentic search, real-time sync) that demonstrate we can move fast when we have a target.

## Facts About the State of the Company

I want to be direct about a few things:

- **We are financially strong.** We have 3+ years of runway. This financial position is exactly what gives us the room to explore and take swings. We are not in trouble.

- **We are not killing Daft.** Daft is a core part of our identity. Apple, ByteDance, and EssentialAI rely on it. The open source project continues and remains central to who we are.

- **Daft Cloud in its current form doesn't fit the market commercially.** As we laid out in the GTM memo, the pain points customers have today are different from the world we originally built for. That's not failure; that's learning. The best companies adapt when the market tells them something clearly.

## What Happens Now

Starting next week, we return to Daft work. The open source project, our existing commitments, and ongoing engineering priorities resume.

At the same time, we're spinning up a small tiger team to build and validate a prototype product. The sprint gave us enough signal to take a focused shot. We believe there's something real at the intersection of our data systems expertise and the problems agent-builders are facing today, and we intend to prove it out quickly and concretely.

We will share more details on the tiger team's scope and composition in the coming days.

## A Note to the Team

We are deep systems thinkers. That is our DNA, and it's how we deliver the most value. The hack sprint was messy, and I know that's uncomfortable for a team that prides itself on rigor. But the discomfort of exploring without a map is different from the discomfort of being lost. We went out, we learned, and now we're coming back with sharper conviction about where to aim.

You'll have clarity on what you're working on and why. That's my commitment.

Thank you for going all-in these past two weeks. The work you did matters, even when the path forward wasn't always clear.

---
