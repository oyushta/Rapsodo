# Risk and Issue Log

| # | Risk | Description | Probability | Impact | Mitigation | Contingency |
|---|---|---|---|---|---|---|
| 1 | API contract delay blocks mobile and QA | Backend, mobile, and QA cannot work in parallel if request/response schemas and error states keep changing. | Medium | High | Freeze API contracts by end of Week 2; publish mock responses; hold contract review with backend, mobile, QA, and data. | Move mobile to mock-only implementation, defer non-core endpoints, and escalate contract changes through TPM approval. |
| 2 | Benchmark privacy rules emerge late | Similar-athlete comparison may require data minimization, cohort thresholds, or regional restrictions. | Medium | High | Include privacy/legal in Sprint 0; use aggregated anonymized cohorts; define minimum cohort size. | Launch without benchmarking or restrict to broad percentile ranges until review is complete. |
| 3 | Third-party AI provider latency or failures hurt experience | AI tips may be slow, unavailable, repetitive, or costly if provider constraints are underestimated. | Medium | High | Use async generation, caching, timeout, retry, fallback copy, provider monitoring, and cost guardrails. | Disable AI tip feature flag, show "tip unavailable" fallback, and release core hub without AI. |
| 4 | Data quality is insufficient for trend and fatigue insights | Historical sessions may be incomplete, inconsistent across sports, or not suitable for accurate trend calculations. | Medium | Medium | Run data profiling in Sprint 0-1; agree on V1 metrics with reliable coverage; document confidence thresholds. | Reduce insights to metrics with verified data, hide low-confidence insights, and plan richer analytics post-release. |
| 5 | Backend and Data are overallocated | Backend owns many critical path items while the single data engineer owns benchmark and trend logic. | High | High | Split backend work by domain, reduce V1 benchmark complexity, track critical path daily, and protect data engineer focus time. | Move advanced personalization and filters out of V1; add backend support to data integration; adjust milestone expectations early. |
| 6 | QA window is compressed by late integration | Cross-platform mobile, AI, benchmark, entitlement, and app store validation may arrive too late for full regression. | Medium | High | Start QA planning in Sprint 0, automate core flows early, provide seeded test data, and test against mocks before real endpoints. | Use feature flags to disable unstable modules, extend rollout, or release core flows only. |
| 7 | App store approval timing threatens end-of-Q3 release | Store review can take longer if builds are submitted late or metadata is incomplete. | Low | Medium | Prepare submission checklist during Sprint 5, include release buffer, and avoid last-minute premium entitlement changes. | Use phased rollout, delay public enablement via feature flags, or submit a build with dormant features. |
| 8 | AI output quality is inconsistent or unsafe | Recommendations may be generic, repetitive, or not appropriate for athlete coaching. | Medium | Medium | Define prompt templates, guardrails, content filters, confidence checks, and sample review with Product/Coaching SMEs. | Limit AI to conservative coaching tips, reduce personalization, or require curated templates for V1. |

## Active Issue Escalation Rule

Any risk becomes an active issue when it blocks a committed sprint deliverable, threatens the release milestone by more than three working days, or requires Product/Engineering trade-off approval. Active issues should be reviewed daily until either resolved or converted into a scope decision.

## Go/No-Go Criteria

Release should not proceed unless:

- No critical or high-priority bugs remain open.
- Session summary and goal tracking pass cross-platform regression.
- Premium entitlement behavior is validated.
- AI and benchmark features can be disabled independently by feature flag.
- Monitoring and rollback plans are active.
- App store submission materials are complete.
