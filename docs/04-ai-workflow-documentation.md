# AI Workflow Documentation

## Tools Used

| Tool | Purpose |
|---|---|
| ChatGPT / Codex | Used to structure the assignment deliverables, identify missing planning sections, pressure-test critical path dependencies, and convert draft notes into a GitHub-ready project. |
| Document extraction tooling | Used to read the assignment PDF and existing draft document so the final plan could be aligned with the evaluation rubric. |
| Mermaid | Used to create readable dependency and critical path diagrams in Markdown. |

## Example 1: Delivery Readiness Gap Analysis

### Exact Prompt

```text
Review this TPM assignment and my draft response. Identify which required deliverables are missing or underdeveloped, especially areas that would affect the scoring rubric. Focus on delivery readiness, technical dependencies, resource planning, risks, and AI workflow documentation.
```

### Raw AI Output

```text
Your draft covers purpose, assumptions, dependencies, capacity concerns, sprint timeline, epics, and user stories. It is weaker in the explicit open items list, technical decision log, detailed WBS, critical path consequence, Week 2 stakeholder update, trade-off scenario, risk log with probability/impact/mitigation/contingency, and AI workflow evidence. The response should be reorganized around the assignment's requested sections rather than only around feature planning.
```

### Final Revised Version

I reorganized the project into four rubric-aligned documents:

- Delivery readiness assessment
- Delivery plan
- Risk and issue log
- AI workflow documentation

I also added a WBS CSV because the assignment specifically asks for actionable owner, effort, and prerequisite visibility.

### Judgment Layer

I accepted the AI's gap identification because it matched the assignment rubric. I revised the structure so the final output is easier for evaluators to navigate. I did not include every possible planning artifact because volume would make the submission harder to read; I prioritized artifacts that show TPM judgment.

## Example 2: Critical Path Reasoning

### Exact Prompt

```text
For the Performance Coaching Hub, identify the technical critical path across Product, Data, Backend, Mobile, QA, and Release. Explain which items would cause a release slip if delayed by one week.
```

### Output Summary

The AI suggested that the critical path should begin with metric and scope confirmation, then move through benchmark/privacy decisions, AI architecture, API contract sign-off, backend implementation, mobile integration, QA regression, app store submission, and rollout.

### Final Use

I used that sequence, but revised it to avoid treating "backend work" as a single block. I separated benchmark/privacy and AI architecture as independent upstream decisions because both can block API design and mobile states.

### Judgment Layer

I accepted the dependency order but made it more specific to the Rapsodo context. I chose not to present the critical path as a date-only Gantt chart because the assignment asked for dependency reasoning and impact if something slips.

## Example 3: Scope Trade-Off Scenario

### Exact Prompt

```text
The PM says the Q3 deadline moved three weeks earlier due to a conference. What should the TPM do first, and what scope options should be presented without compromising release quality?
```

### Output Summary

The AI proposed reducing analytics complexity, delaying AI personalization, using feature flags, and protecting the core session summary experience.

### Final Use

I converted the suggestions into four explicit scope options:

- Core hub only
- Premium AI limited beta
- Benchmark-lite
- Full scope with reduced QA window

I also added a recommendation against the full-scope compressed-QA option.

### Judgment Layer

I accepted the feature-flag and scope-reduction framing. I revised the output to make the stakeholder conversation more realistic: the first move is alignment on business value and risk tolerance, not simply asking engineers to compress estimates.

## Reflection

AI accelerated the planning work by quickly surfacing missing sections, alternative risk framings, and dependency chains that are easy to overlook when working from an incomplete brief. It was most useful as a critique and structure partner.

AI fell short when outputs became too generic, especially around "backend work" or "QA testing." A real TPM plan needs to expose the specific handoffs: API contracts, mock responses, benchmark cohort rules, entitlement checks, AI provider behavior, seeded data, and app store timing. I therefore used AI to generate options, then narrowed and revised them based on delivery impact.

On a real project, I would use AI to prepare workshop agendas, draft decision logs, summarize engineering trade-offs, and maintain stakeholder updates. I would not use AI as the source of truth for estimates, technical feasibility, privacy decisions, or release readiness. Those need validation from the actual engineering, product, QA, data, and compliance owners.
