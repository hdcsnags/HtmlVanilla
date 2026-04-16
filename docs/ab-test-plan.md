# A/B Test Plan: Headline Variant Evaluation

**Document version:** 1.0  
**Status:** Draft — awaiting stakeholder sign-off  
**Owner:** Product Marketing  
**Last updated:** 2025-01-01  
**Depends on:**
- `design/copy-variants.md` — variant inventory (headline copy, CTAs, sub-headlines)
- `docs/messaging-brief.md` — positioning constraints and brand guardrails

---

## 1. Purpose and Scope

This document defines the methodology for evaluating the A/B headline variants catalogued in `design/copy-variants.md` across three distinct target personas. The goal is to identify a statistically reliable winning variant for each persona segment — or a single universally performant variant if one emerges — while remaining within the positioning constraints established in `docs/messaging-brief.md`.

This is a **planning document only**. It does not specify implementation details for live test infrastructure, analytics instrumentation, or feature-flag configuration. Those concerns are handled separately by the engineering and data teams.

### 1.1 Out of Scope

- A/B test infrastructure setup or SDK integration
- Analytics event schema or tagging specifications
- Multivariate testing of non-headline elements (layout, imagery, colour)
- Pricing page or conversion funnel tests outside the headline evaluation
- Localisation or internationalisation variants

---

## 2. Persona Definitions

The three personas below represent the primary addressable segments identified in `docs/messaging-brief.md`. Each persona description includes the job-to-be-done (JTBD), key pain points, and the decision lens through which they evaluate messaging.

### 2.1 Persona A — DevOps Lead

| Attribute | Detail |
|---|---|
| **Role title examples** | DevOps Engineer, Platform Engineer, Site Reliability Engineer, Infrastructure Lead |
| **Seniority** | IC Level 4–6 or team lead; typically 5–12 years experience |
| **Organisation size** | Series B+ startup to mid-market (50–2,000 employees) |
| **Primary JTBD** | Ship reliable infrastructure changes faster without manual toil or on-call incidents |
| **Secondary JTBD** | Demonstrate platform value to engineering leadership; reduce cognitive load on the team |
| **Key pain points** | Flaky CI pipelines; configuration drift; incident fatigue; tribal knowledge in runbooks |
| **Evaluation lens** | Technical credibility first — they will dismiss marketing language quickly. Responds to specificity, peer validation, and evidence of production-scale use cases. |
| **Typical entry point** | Organic search, GitHub discovery, word-of-mouth from peers, conference talks |
| **Risk posture** | Moderate. Will trial before committing; values reversibility and good documentation. |

### 2.2 Persona B — CTO

| Attribute | Detail |
|---|---|
| **Role title examples** | CTO, VP Engineering, Head of Engineering, Engineering Director |
| **Seniority** | C-suite or VP-level; typically 10+ years experience |
| **Organisation size** | Seed-to-growth stage startup (10–500 employees) or BU lead at enterprise |
| **Primary JTBD** | Increase engineering velocity and system reliability without proportionally growing headcount |
| **Secondary JTBD** | Reduce bus-factor risk; improve developer experience to aid retention; satisfy board/investor expectations on efficiency |
| **Key pain points** | Engineering bottlenecks blocking product roadmap; unclear ROI on tooling spend; difficulty comparing build-vs-buy; compliance and security posture |
| **Evaluation lens** | Outcome-oriented and ROI-conscious. Scans for business impact, not feature lists. Trusts analyst reports, customer logos, and revenue/cost impact metrics. |
| **Typical entry point** | Analyst recommendations, peer CTO networks, LinkedIn, investor portfolio introductions |
| **Risk posture** | Conservative to moderate. Requires business case and security review before budget approval. |

### 2.3 Persona C — ML Engineer

| Attribute | Detail |
|---|---|
| **Role title examples** | Machine Learning Engineer, MLOps Engineer, AI/ML Platform Engineer, Research Engineer |
| **Seniority** | IC Level 3–6; typically 3–10 years experience |
| **Organisation size** | Any organisation with a dedicated ML/AI practice |
| **Primary JTBD** | Reliably move models from experimentation to production with reproducible, observable pipelines |
| **Secondary JTBD** | Reduce time spent on infrastructure plumbing; collaborate effectively with data scientists who are not infra-focused |
| **Key pain points** | Model reproducibility failures; training/serving skew; lack of versioning for data and models; slow iteration cycles between research and production |
| **Evaluation lens** | Workflow-centric and pragmatic. Wants to see that the tool understands ML-specific concerns (experiment tracking, feature stores, GPU scheduling). Distrusts generic DevOps tools rebranded for ML. |
| **Typical entry point** | ML-focused communities (Hugging Face, MLflow Slack, papers with code), conference talks, internal champions |
| **Risk posture** | Low-to-moderate. Will prototype quickly but needs confidence in production scalability before advocacy. |

---

## 3. Variant Inventory Reference

All headline copy, sub-headline copy, and CTA text tested in this plan is drawn exclusively from `design/copy-variants.md`. The variant identifiers used throughout this document (e.g., `V1`, `V2`, `V3`) map directly to the variant IDs defined in that file.

**Important:** No variant may be added to a live test without first being registered in `design/copy-variants.md` and reviewed against the positioning constraints in `docs/messaging-brief.md`. Any variant found to conflict with the brand guardrails in the messaging brief is ineligible for testing regardless of predicted performance.

### 3.1 Variant Eligibility Checklist

Before a variant enters the test rotation, it must satisfy all of the following:

- [ ] Variant is listed and described in `design/copy-variants.md`
- [ ] Variant does not make claims excluded by `docs/messaging-brief.md` (e.g., unsupported superlatives, competitor comparisons without legal sign-off)
- [ ] Variant has been reviewed by at least one member of Legal/Compliance if it contains performance benchmarks or customer outcome claims
- [ ] Variant has been reviewed by Brand for tone and voice consistency
- [ ] Variant is visually implemented and QA'd in staging before traffic is allocated

---

## 4. Success Metrics

Metrics are tiered into **primary** (decision-driving) and **secondary** (directional and diagnostic). A winning variant must outperform the control on the primary metric at the required confidence level. Secondary metrics are used to rule out false positives and to inform future iteration.

### 4.1 Primary Metrics

| Persona | Primary Metric | Definition | Rationale |
|---|---|---|---|
| DevOps Lead | **Free trial activation rate** | Unique visitors who complete trial signup / unique visitors exposed to variant | DevOps leads evaluate by doing. Trial activation is the highest-signal action they take at the top of the funnel. |
| CTO | **Demo request rate** | Unique visitors who submit a demo request form / unique visitors exposed to variant | CTOs rarely self-serve trial. Demo request indicates intent to bring the tool into a business evaluation process. |
| ML Engineer | **Documentation engagement rate** | Unique visitors who navigate to docs or quickstart guide / unique visitors exposed to variant | ML engineers validate technical credibility through documentation depth before committing to trial. Doc click-through is the leading indicator of qualified interest. |

### 4.2 Secondary Metrics

| Metric | Applicable Personas | Definition | Use |
|---|---|---|---|
| **Bounce rate** | All | Single-page sessions / total sessions exposed to variant | High bounce on a winning primary-metric variant may indicate traffic quality issues or misleading headlines. |
| **Time on page** | All | Average session duration on the landing page | Directional signal for message resonance. Not decision-driving due to high variance. |
| **Scroll depth (50% and 90%)** | All | % of sessions reaching 50% / 90% of page height | Indicates whether the headline creates enough curiosity to pull users into body copy. |
| **CTA click-through rate (secondary CTA)** | DevOps Lead, ML Engineer | Clicks on secondary CTA (e.g., "View docs", "See pricing") / exposures | Captures intent signals that do not convert directly to primary metric. |
| **Return visit rate (7-day)** | CTO | % of exposed unique visitors who return within 7 days | CTOs often return after internal discussions. Leading indicator of deal progression. |
| **Qualified lead rate** | CTO | Demo requests marked as ICP-fit by sales within 5 business days of submission / total demo requests | Guards against a variant that drives high demo volume from non-ICP visitors. |

### 4.3 Guardrail Metrics

The following metrics must not degrade below the defined thresholds in any winning variant, even if the primary metric improves. A variant that violates a guardrail is disqualified.

| Guardrail Metric | Threshold | Rationale |
|---|---|---|
| **Page load time (P75)** | Must not increase by more than 200ms vs. control | Headline variants may include different asset weights. Performance regressions harm all users. |
| **Accessibility score (Lighthouse)** | Must maintain ≥ 90 | Brand and legal requirement. |
| **Spam/abuse form submissions** | Must not increase by more than 20% vs. control | A headline that attracts low-quality submissions degrades sales team efficiency. |

---

## 5. Test Methodology

### 5.1 Test Design

**Test type:** Parallel A/B test (not sequential or bandit)  
**Randomisation unit:** Visitor (cookie/device ID)  
**Allocation:** Equal split across all variants within each persona segment (e.g., if 4 variants: 25% each)  
**Segmentation approach:** Persona segments are identified via traffic source, UTM parameters, and where available, firmographic data from identity resolution. Segment assignment is determined before exposure and is immutable for the duration of the test.

> **Note:** Persona segmentation via UTM parameters requires coordination with demand generation. The mapping of UTM values to persona segments must be documented separately and kept in sync with campaign operations.

### 5.2 Control Variant

The control variant for each persona test is the **currently live production headline** at the time the test is launched. If the product page has not previously been live (e.g., a new page), the control is designated as the first variant listed in `design/copy-variants.md` that has been reviewed and approved.

### 5.3 Test Duration

Minimum test duration is determined by **both** of the following conditions being satisfied — whichever requires more calendar time:

1. **Statistical condition:** Required sample size reached in each variant cell (see Section 5.4)
2. **Calendar condition:** Minimum of **14 full calendar days** of data collected to account for day-of-week effects and weekly traffic cycles

Maximum test duration is **60 calendar days**. If statistical significance has not been reached by day 60, the test is declared inconclusive and escalated to the product marketing lead for a decision (see Section 7.3).

### 5.4 Sample Size and Power

| Parameter | Value | Rationale |
|---|---|---|
| **Minimum detectable effect (MDE)** | 15% relative improvement over control | Below 15% lift, the business impact does not justify variant switching costs and re-implementation risk. |
| **Statistical significance threshold (α)** | 0.05 (two-tailed) | Industry standard for marketing experiments. |
| **Statistical power (1 − β)** | 0.80 | Standard power level; acceptable Type II error rate of 20%. |
| **Baseline conversion rate assumption** | Per-persona baseline derived from 30-day pre-test actuals | Must be recalculated at test kickoff using current data. |

Sample size calculations must be performed at test kickoff using current baseline rates. The calculations must be documented in the test tracking sheet before traffic allocation begins.

### 5.5 Traffic Allocation

- Tests run on **new visitors only** to eliminate returning visitor bias from prior exposure to the control.
- Returning visitors who were previously bucketed into a variant cell **remain in their assigned cell** for the duration of the test.
- Internal company IP ranges are excluded from test traffic.
- Bot and crawler traffic is filtered before analysis using the analytics platform's standard bot exclusion list.

### 5.6 Interaction Effects and Mutual Exclusivity

- No more than one headline A/B test may run concurrently on the same page for the same persona segment.
- If other tests (e.g., layout tests, CTA colour tests) are running concurrently on the same page, the headline test team must coordinate with the owners of those tests to ensure mutual exclusivity or, where that is not feasible, to document the potential interaction effect and its implications for result interpretation.

---

## 6. Test Execution Checklist

The following checklist must be completed before any variant receives live traffic.

### 6.1 Pre-Launch

- [ ] Variants confirmed against `design/copy-variants.md` — all test variant IDs documented
- [ ] Positioning compliance review completed against `docs/messaging-brief.md`
- [ ] Legal/Compliance review completed for any claim-bearing variants
- [ ] Brand review completed for tone and voice
- [ ] Baseline conversion rates pulled from analytics for the 30 days preceding test launch
- [ ] Sample size calculated and documented for each persona segment and each primary metric
- [ ] Minimum test duration calculated and calendar end date set
- [ ] Guardrail metric baselines documented
- [ ] QA sign-off on all variant implementations in staging
- [ ] Analytics instrumentation verified in staging (events firing correctly for primary and secondary metrics)
- [ ] Stakeholder notification sent (Product, Marketing, Sales, Engineering leads)
- [ ] Test tracking sheet created and linked from this document

### 6.2 During Test

- [ ] Weekly health check: sample ratio mismatch (SRM) check performed
- [ ] Weekly health check: guardrail metrics reviewed
- [ ] No changes made to variant copy, layout, or analytics instrumentation after launch
- [ ] No changes made to the pages adjacent to the test (e.g., downstream funnel steps) that could confound results
- [ ] Anomalous traffic events (outages, viral spikes, campaign surges) logged with timestamps

### 6.3 Post-Launch / Analysis

- [ ] Final sample size and test duration confirmed as meeting pre-specified requirements
- [ ] SRM check passed (see Section 6.4)
- [ ] Primary metric results calculated with confidence intervals
- [ ] Secondary metric results reviewed
- [ ] Guardrail metrics confirmed as not violated
- [ ] Segment-level breakdowns reviewed (device type, geography, traffic source) for heterogeneity
- [ ] Results documented in test tracking sheet
- [ ] Decision made per Section 7 criteria
- [ ] Stakeholder results summary distributed

### 6.4 Sample Ratio Mismatch (SRM) Check

A sample ratio mismatch occurs when the observed traffic split between variant cells differs significantly from the intended split. SRM is a signal of instrumentation error or bucketing bias and invalidates test results.

**Method:** Chi-squared goodness-of-fit test comparing observed cell sizes to expected sizes (based on intended allocation percentages).  
**Threshold:** If the p-value of the SRM check is < 0.01, the test is flagged as potentially invalid and must be investigated before results are acted upon.  
**Resolution:** Engineering and analytics must identify and remediate the source of the mismatch. The test may need to be restarted.

---

## 7. Decision Criteria for Selecting a Winning Variant

### 7.1 Standard Win Conditions

A variant is declared the **winner** for a given persona if ALL of the following are true:

1. **Primary metric significance:** The variant's primary metric improvement over the control achieves p < 0.05 (two-tailed) at the required sample size.
2. **Confidence interval excludes zero:** The 95% confidence interval for the relative lift does not include zero.
3. **Practical significance:** The observed lift is ≥ 15% relative improvement over control (the pre-specified MDE).
4. **No guardrail violations:** None of the guardrail metrics defined in Section 4.3 are violated.
5. **SRM check passed:** The sample ratio mismatch check (Section 6.4) does not flag the test as invalid.
6. **Positioning compliance:** The winning variant is confirmed as compliant with `docs/messaging-brief.md`. A variant that conflicts with the positioning brief **cannot be declared a winner** regardless of performance metrics.

### 7.2 Tie-Breaking Procedure

If two or more variants both satisfy the win conditions in Section 7.1 for the same persona segment:

1. **Step 1 — Primary metric magnitude:** The variant with the higher observed lift on the primary metric is preferred.
2. **Step 2 — Secondary metric tiebreak:** If lifts are within 2 percentage points of each other (within margin of error), secondary metrics are used to differentiate. The variant with better secondary metric performance across the majority of secondary metrics wins.
3. **Step 3 — Strategic alignment:** If secondary metrics are also inconclusive, the Product Marketing lead makes the final call based on strategic alignment with the current positioning priorities in `docs/messaging-brief.md`. This decision must be documented with rationale.

### 7.3 Inconclusive Test Handling

A test is declared **inconclusive** if:

- Maximum test duration (60 days) is reached without achieving statistical significance on the primary metric, **OR**
- The SRM check flags the test as invalid and the mismatch cannot be resolved

**Inconclusive escalation process:**

1. Product Marketing lead is notified within 2 business days of the inconclusive determination.
2. A retrospective is held within 5 business days to assess: Was the MDE realistic? Was the baseline rate estimate accurate? Was traffic volume sufficient?
3. Options considered: (a) extend test with revised power calculation, (b) redesign variant set with larger expected effect sizes, (c) accept control as default and archive the test.
4. Decision and rationale are documented in the test tracking sheet.

### 7.4 Negative Result Handling

If a variant performs **significantly worse** than the control (p < 0.05 in the negative direction, with magnitude ≥ 10% relative degradation):

1. The variant is immediately removed from rotation regardless of whether the test has reached its planned end date.
2. The underperformance is documented in `design/copy-variants.md` as a negative signal against that variant.
3. The messaging themes associated with the underperforming variant are flagged for review in the next `docs/messaging-brief.md` revision cycle.

### 7.5 Cross-Persona Winner Analysis

After per-persona winners are determined, a cross-persona analysis is conducted to evaluate:

- **Universal winner possibility:** Does any single variant win or perform neutrally across all three personas? If so, it is a candidate for a single unified headline (simpler to maintain, no segmentation required).
- **Conflict check:** Does the per-persona winner for one persona perform significantly worse for another persona? If so, segmented delivery is required and the trade-offs must be documented.
- **Positioning coherence:** Are the per-persona winners collectively coherent with the brand narrative in `docs/messaging-brief.md`, or do they pull the positioning in contradictory directions?

The cross-persona analysis output is a **recommendation memo** addressed to the Product Marketing lead and CTO, summarising the per-persona winners, the universal winner assessment, and a recommended implementation path.

---

## 8. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| **Product Marketing Lead** | Owns this test plan; final decision authority on inconclusive tests and tie-breaks; ensures positioning compliance |
| **Growth/Experimentation Analyst** | Owns sample size calculation, test monitoring, SRM checks, and statistical analysis |
| **Frontend Engineer** | Implements variant copy in staging and production; maintains analytics instrumentation |
| **Brand Designer** | Reviews all variants for visual and tone consistency before launch |
| **Legal/Compliance** | Reviews claim-bearing variants before launch |
| **Sales Lead** | Provides input on demo request quality (qualified lead rate guardrail); consulted on CTO persona behaviour |
| **Data Engineer** | Ensures analytics event pipeline is reliable and bot filtering is current |

---

## 9. Test Tracking and Documentation

All tests governed by this plan must be logged in the central **Experimentation Tracking Sheet** (link to be added at test kickoff). Each test record must include:

- Test ID and name
- Variant IDs tested (from `design/copy-variants.md`)
- Target persona segment
- Test start date and planned end date
- Baseline metrics at launch
- Sample size targets
- Weekly health check log entries
- Final results (primary and secondary metrics with confidence intervals)
- SRM check result
- Decision outcome and rationale
- Link to results summary distributed to stakeholders

Test records must be retained for a minimum of 24 months after test completion.

---

## 10. Plan Revision History

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2025-01-01 | Product Marketing | Initial draft |

---

## Appendix A: Statistical Terminology Reference

| Term | Definition |
|---|---|
| **MDE (Minimum Detectable Effect)** | The smallest true effect size the test is designed to reliably detect, given the chosen sample size, α, and power. |
| **α (significance level)** | The probability of rejecting the null hypothesis when it is actually true (Type I error rate). Set at 0.05 in this plan. |
| **Power (1 − β)** | The probability of correctly rejecting the null hypothesis when the true effect equals the MDE. Set at 0.80 in this plan. |
| **Two-tailed test** | A significance test that considers the possibility of the effect being in either direction (positive or negative). Used in this plan to guard against declaring a winner that is actually harmful. |
| **SRM (Sample Ratio Mismatch)** | A condition where the observed allocation of visitors to variant cells does not match the intended allocation, indicating a possible instrumentation error. |
| **Confidence interval** | A range of values within which the true effect size is expected to fall with a given probability (95% in this plan). |

## Appendix B: Persona-to-UTM Mapping (Placeholder)

This appendix will be completed in coordination with demand generation before the first test launch. It will document the UTM parameter values (source, medium, campaign, content) that map to each of the three personas defined in Section 2, enabling correct segment assignment at the point of page exposure.

*To be completed: Demand Generation + Product Marketing — target date prior to first test launch.*

## Appendix C: References

- `design/copy-variants.md` — Headline variant inventory and copy
- `docs/messaging-brief.md` — Positioning constraints, brand guardrails, and tone of voice
- Experimentation Tracking Sheet — *(link to be added at first test kickoff)*
- Pre-test sample size calculation workbook — *(link to be added at first test kickoff)*
