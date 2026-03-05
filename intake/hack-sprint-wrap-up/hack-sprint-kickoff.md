Daft Hack Sprint: Agents Edition
Kickoff: Jan 20th 2026 | Duration: 2 weeks
Why Now
We've spent 2025 learning that "better infrastructure" isn't enough—customers want outcomes. Our GTM conversations (Cursor, Harvey, Rogo) all point the same direction: teams building AI agents are drowning in data problems we're uniquely positioned to solve.
This hack sprint is how we build conviction. We're not shipping product—we're learning what actually breaks in agentic workflows and leveraging our unfair advantage due to building Daft (large-scale unstructured data) to create real value. However we should take this moment to acknowledge the problem and our expertise in multimodal data but to question the form factor of what we built so far. The goal is learning, not validating what we've already built.
Our hypotheses:
Agents are here to stay, and 2026 will be defined by them
Coding agents are becoming the orchestration layer for all agent work—even when the end task isn't code, a coding agent is increasingly the thing coordinating tools, data, and workflows
The biggest bottlenecks aren't model intelligence—they're context, memory, and coordination
What We've Observed
Context starvation — Agents rely on skilled "drivers" to manually inject organizational context. When context drifts, agents derail.
No shared memory — Multiple agents don't compound on each other's knowledge. Every session starts cold.
Dumb retrieval — Agents default to grep XX | head 50 patterns. They don't know what to search for or how to search effectively across heterogeneous data.
Optimized for code, blind to everything else — Web search and code search are solid. Enterprise data, docs, traces, conversations? Not so much.

Themes
Pick one or propose your own:

Theme
Problem
Our Angle
Librarian (Sammy, Colin, Jay's project)
Agents can't browse organizational knowledge effectively
Automated curation layer that exposes a searchable knowledge library as a skill/plugin
Agent Steering
We can't see where agents go off the rails until it's too late
Collect unstructured traces from tasks, commands, and skills. Learn where agents get stuck—e.g., Rust borrow checking on a specific trait pattern—and feed aggregated learnings back as guardrails or hints
Async Exploration
Synchronous "explore then plan" phases cap out at a few minutes
Introduce a new pattern: batch async exploration over large corpora so agents gather more context and self-correct before deep execution. Still human-in-the-loop, but the agent does more homework upfront
Knowledge Copilot
Humans are the only ones who can catch an agent going off the rails and inject missing context
Run an async "sidecar" agent with access to organizational knowledge that monitors the primary agent's trajectory. When the copilot recognizes the agent needs context, it interrupts and injects it—replacing reactive human intervention with proactive knowledge delivery


Measuring Progress
We want to demonstrate results on public datasets and evals so we can objectively measure improvement. Consider targeting:
SWE-Bench (or a tractable subset)
Other code-focused benchmarks where we can measure before/after with your intervention
This keeps us honest and gives us artifacts we can share externally.
Ground Rules
Teams: 2-3 people
Budget: Up to $3k in tokens per team—be scrappy, learning > burn
Integration requirement: Your solution should plug into Claude Code, Cursor, or Codex via skills/plugins—not be a standalone tool
Document everything: We're learning, not shipping. Write down what works, what doesn't, and why. This compounds.
Daily syncs: EOD sharing session (see rubric below)
Guinea pigs: Sammy and Jay will dogfood your projects throughout (and potentially demo externally)
Green Field: Feel free to use whatever tools make sense and make you move the quickest. You are encouraged to use the tools and platforms that weren’t built here. To be clear: it is not a requirement to use Daft or Daft Cloud.

Daily Sharing Rubric
At each EOD sync, every team shares a brief update (~5 min) covering:

Question
What we're looking for
What did you try today?
Concrete experiments, not just "made progress"
What worked?
Even small wins—what surprised you positively?
What didn't work?
Failures are valuable. Be specific about why.
What did you learn about how agents fail?
Patterns, edge cases, failure modes you observed
What's your plan for tomorrow?
Next experiment or pivot based on today's learnings

Write this up in a shared doc so we compound across teams.

Judging Criteria

Criterion
Weight
What we're asking
Interesting results
25%
Did you ship something that measurably improves a coding agent's capability or the human's workflow using one?
Interesting approach
25%
Did you uncover a novel method that could raise the ceiling for agent performance?
Learning depth
25%
How much did we learn about why coding agents get stuck today with current tools?
"It clicks" factor
25%
How much does this problem resonate with coding agent users? Would someone see this and immediately want it?


Prize
$1,500/person for the winning team ($3k for 2-person, $4.5k for 3-person)


