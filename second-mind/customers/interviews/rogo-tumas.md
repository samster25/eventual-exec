---
title: "Rogo - Tumas Rackaitis Interview"
created: 2026-03-05
updated: 2026-03-05
status: active
related:
  - "[[hypotheses]]"
  - "[[strategy]]"
  - "[[conversation-log]]"
---

# Rogo - Tumas Rackaitis Interview

**Date:** December 16, 2025
**Participants:** Jay Chia, Sammy Sidhu, Tumas Rackaitis (co-founder, Rogo)
**Company:** Rogo -- generative AI platform for financial services
**Context:** This is the pivotal "capture the value" call that planted the seed for Eventual Entity Search. The conversation began as a Daft Cloud infrastructure pitch and turned into a masterclass on value capture and product strategy.

---

## Company Background

Rogo is a generative AI platform for financial services. Key facts from the call:

- Deployed with **JP Morgan, Wells Fargo**, and other major financial institutions
- ~90 people and growing rapidly
- Works with leading hedge funds and private equity firms (including Apollo)
- Tumas is an engineer/architect co-founder; previously worked at a hedge fund
- Hired people from DeepMind who built Google Search infrastructure
- Uses Spanner, pub/sub architecture, event-driven data systems
- Strict security requirements: cloud resource-level isolation between bank clients ("The worst thing would be that we serve Goldman Sachs's internal research to Citibank -- that would mean the death of our company")

---

## The Infrastructure Pitch -- And Why It Didn't Land

Sammy and Jay pitched Daft Cloud's managed ingestion and processing pipeline. Tumas was polite but direct about why it wasn't compelling:

> "I have the parallelism already. I put an engineer on a data source and they'll have it up in a week in my stack."

On vendor onboarding friction in financial services:

> "I have to get every single sub-processor approved. Banks actually care about what's in your SOC 2 report. I'd have to put you guys in, they're going to be like, who the hell are you? It's gonna be a whole nightmare."

He was clear that infrastructure wasn't the pain:

> "We use Google Data Flow, Google Pub/Sub, Kubernetes. They allow us to have great parallelism. Using managed inference providers from Gemini or OpenAI... we typically are okay."

---

## The Pivot Moment: "Capture the Value"

This is where the conversation transformed. Tumas challenged the team to think bigger:

> "Guys like you are sitting atop technology that could just kill any data provider. A company like CAPIQ or FactSet or -- I mean, hell, half of Bloomberg does this, right? What they do is they just pay people in Bangladesh to read financial documents and put them into a structured database. That's it. And that's how they're able to send an API feed to all of the different hedge funds. And you're able to do that faster, programmatically, save them, cut them on margin."

But he went further -- don't just disrupt the data providers, become one:

> "You would sell the infra, but I think the money is actually on the other end of it and just selling the raw data."

---

## The Berkeley Lights Cautionary Tale

Tumas told the story of Berkeley Lights -- a company he had shorted as a short seller -- to illustrate the value capture problem:

> "They built these awesome machines that would help you discover drugs. And they'd sell these machines for a million and a half dollars, $2 million a pop. Pfizer and Moderna bought these machines. So they went public and it's like AI for drug discovery. Super trooper, right? But here's the problem: Pfizer buys that machine for $2 million and then discovers something. Discovers the next Ozempic. And what does Berkeley Lights get? $2 million. They get nothing. They create a ton of value and they capture none of it."

His direct challenge:

> "You guys are going to create a ton of value if you make this work. You're going to be building an encyclopedia, all of these different knowledge bases on top of it. But how are you going to capture that value? I would just say -- capture it yourselves. Why not?"

---

## What He Would Actually Buy

When asked about buying data:

> "I would pay $50K without batting an eye. If it's more than that, I would actually have to think about it. I personally would have unilateral buying authority to buy for $50K without batting an eye. I would just send a Ramp card and it'd be done."

On what kind of data:

> "Exa and Parallels are such good pieces of underlying infrastructure that are not imaginative whatsoever of what power you could do. Give me every single store Sweet Green has opened in the Southwest every single day -- literally Google Maps over time."

He wanted curated, structured intelligence about the world -- not tools to build it himself.

---

## On Internal Data and Recency

Tumas had a sharp take on why internal document search is less valuable than people think:

> "How many times did you look at a Google Doc that was made two years ago? I would wager almost never at all. Glean does this as well -- they almost don't care about vector search at all. We actually don't use vector search at all. We just use keyword search on internal documents because recency and who you share the file with ends up being everything."

> "In financial services, there's like no alpha in a memo I wrote about Enron in 2003 because Enron's out of business. And that also applies to Coca Cola in 2003, because Coca Cola is a different company than it was in 2003. There's this huge decay of information asymmetry and relevance."

---

## On Being Specific

> "Don't leave room for imagination. Come with something specific."

He shared his own experience at Rogo:

> "When we sold text-to-SQL, I'm just like, hey, we have this way you connect your database, you're able to get all these different insights, and they're like, what insights do I want? And I'm like, I don't know. It leads me to this tough part."

---

## On Data Set Resale Risk

Tumas also warned about the flat data set trap:

> "Data sets follow the same problem as infrastructure. You guys sell me a flat data set for $50K and then I sell it to every investment bank. I just -- you just captured none of the value."

---

## Key Takeaways

1. **Infrastructure is not the pain** for sophisticated AI teams. They've solved parallelism and ingestion.
2. **The money is in selling intelligence, not infrastructure.** "Capture the value you create."
3. **Berkeley Lights = cautionary tale.** Build machines that create value but capture none of it.
4. **$50K buying authority** exists at companies like Rogo for curated data. No committee needed.
5. **Be specific.** "Don't leave room for imagination." Come with a concrete product, not a platform.
6. **Internal data search is overrated.** Recency and sharing context dominate. External intelligence is the greenfield.
7. **Financial data providers are vulnerable** -- Bloomberg, CAPIQ, FactSet do manual work that can be automated. But hedge funds are "the worst customers."

---

## Impact on Company Direction

This call crystallized the shift from "sell the infrastructure" to "own the intelligence." It planted the seed that became Eventual: we don't sell the tools to process data -- we build curated, navigable intelligence about real-world entities and sell that directly.

The through-line: Harvey told us indexing is solved. Tumas told us to capture the value. Eventual is us taking that advice.
