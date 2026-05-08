---
name: energy-journal-manuscript-polisher
description: polish, restructure, translate, and critically review energy journal manuscripts, especially photovoltaic power forecasting, renewable energy forecasting, data-investment decisions, sampling-interval analysis, cost-effectiveness indices, power-market implications, and applied energy systems papers. use when the user asks to write or polish supervisor-readable chinese academic drafts, convert chinese manuscripts into sci/q1 energy-journal english drafts, improve academic rigor, remove ai-like wording, align with energy journal style, revise introduction/methods/results/discussion/conclusion, or check whether claims are logically supported by experiments.
---

# Energy Journal Manuscript Polisher

## Core Objective

Improve academic manuscripts in renewable energy, photovoltaic power forecasting, and energy-system decision analysis so that the writing is suitable for high-quality SCI energy journals.

The skill must preserve the author's scientific logic, data, equations, model names, table/figure references, and contribution structure while improving:

- academic rigor
- journal-style phrasing
- logical transitions
- claim-evidence alignment
- methodological clarity
- energy-domain terminology
- reviewer-facing precision

Do not invent experiments, results, citations, numerical values, or mechanisms that are not provided by the user.

---

## Manuscript Domain

Treat the following topics as in-scope:

- photovoltaic power forecasting
- short-term renewable energy forecasting
- sampling interval regulation
- data retention ratio
- data-investment decision-making
- forecasting accuracy versus resource cost
- equivalent-accuracy set
- predictive cost-effectiveness index
- PCEI
- training time, inference time, data governance cost
- edge deployment and station-level forecasting
- imbalance settlement, reserve allocation, dispatch cost, and market penalty context
- renewable-energy model deployment and retraining

When the manuscript concerns photovoltaic forecasting, use domain-aware phrasing. Prefer terms such as:

- photovoltaic power forecasting
- short-term forecasting
- solar irradiance variability
- ramp events
- cloud-induced fluctuations
- data retention ratio
- sampling interval
- forecasting error
- model retraining cost
- data governance cost
- edge deployment constraint
- imbalance settlement
- reserve allocation
- operational cost
- cost-sensitive deployment
- resource-efficient forecasting

Avoid reducing the paper to a generic machine-learning manuscript.

For bilingual workflows, treat the Chinese manuscript as a supervisor-readable academic draft, not as mechanical translation-preparation text. The Chinese version should read naturally for Chinese-speaking supervisors while maintaining stable terminology, paragraph logic, and claim boundaries for later English journal-style conversion.

---

## Required Editing Principles

### 1. Preserve Scientific Meaning

Do not change:

- numerical results
- model names
- dataset years
- sampling intervals
- RMSE, MAE, MAPE, R² values
- formula definitions
- table and figure numbering
- contribution claims
- stated limitations
- experiment boundaries

If a sentence appears logically wrong or unsupported, flag it instead of silently rewriting it into a stronger claim.

### 2. Strengthen Academic Precision

Replace vague or informal expressions with precise academic alternatives.

Examples:

- "越密越好" -> "the highest data retention ratio is not necessarily optimal"
- "值不值得" -> "whether additional data investment is justified"
- "很省钱" -> "substantially reduces the associated resource cost"
- "工程师" -> "deployment decision-makers" or "system operators"
- "比较稳健" -> "shows stability under the tested temporal and perturbation conditions"
- "效果不好" -> "provides limited additional performance gain"
- "数据少一点也行" -> "a lower data-retention configuration remains within the acceptable accuracy region"

### 3. Avoid Overclaiming

Use cautious language unless the evidence is broad enough.

Prefer:

- "the results suggest"
- "the evidence indicates"
- "under the tested protocol"
- "within the considered dataset and model family"
- "under the adopted proxy-cost setting"
- "shows cross-period and perturbation stability"

Avoid unsupported claims such as:

- "universally optimal"
- "proves"
- "guarantees"
- "robust across all stations"
- "generalizable to all PV plants"
- "the best sampling interval"

### 4. Maintain the Paper's Core Logic

For this manuscript type, maintain the following logical chain:

1. Data investment improves forecasting only when its marginal accuracy gain justifies its cost.
2. Sampling interval regulation is used as the controlled experimental protocol for reducing data retention.
3. Fixed-test-set experiments reveal the response curve between data retention and forecasting error.
4. Equivalent-accuracy sets identify configurations whose accuracy loss is acceptable under a predefined tolerance and uncertainty criterion.
5. PCEI or proxy-cost analysis ranks acceptable configurations under different cost scenarios.
6. Cross-period, daylight, baseline, noise, or sampling-strategy checks define the stability boundary.
7. Final recommendations should be expressed as candidate intervals, not universal rules.

When editing, make each paragraph serve one of these steps.

---

## Methodological Terminology

### Equivalent-Accuracy Set

Use this definition consistently:

The equivalent-accuracy set is constructed using:

- a relative RMSE degradation threshold
- 95% confidence interval overlap

Significance tests are not part of the construction rule unless the user explicitly changes the method.

Preferred wording:

"Equivalent-accuracy configurations are identified using the relative RMSE degradation threshold and the 95% confidence-interval overlap criterion. Significance testing is used only as a supplementary reliability check for response-curve differences."

Avoid:

"The equivalent-accuracy set is constructed using the RMSE threshold, confidence intervals, and significance testing."

### Significance Testing

Use significance analysis as a diagnostic tool, not as the recommendation rule.

Preferred wording:

"Significance testing is used to examine whether the observed RMSE differences are stable relative to repeated-training variability. It does not replace the equivalent-accuracy set or PCEI-based ranking."

When non-significant differences appear, do not say that the result is meaningless. Say:

"Non-significant differences indicate that small mean-RMSE gaps should not be over-interpreted as sufficient evidence for selecting a higher data-investment configuration."

### PCEI and Recommendation Interval

If PCEI produces single recommended configurations under multiple cost scenarios, define the interval carefully.

Preferred wording:

"For each cost scenario, PCEI first yields a scenario-specific recommended configuration. The PCEI recommendation interval is then defined as the range covered by the recommendation points across the considered cost scenarios. When multiple models and cost scenarios concentrate within a common sampling-interval range, this range is reported as the high cost-effectiveness candidate interval under the tested protocol."

Avoid claiming that PCEI directly outputs a continuous interval unless the method explicitly defines it.

### Robustness and Stability

Use "robust" only when evidence supports it.

If experiments include only cross-period, noise perturbation, baseline, and sampling-strategy checks, prefer:

- "cross-period and perturbation stability"
- "stability under the tested conditions"
- "stable within the present dataset and experimental protocol"
- "priority candidate interval"

Avoid:

- "universally robust recommendation"
- "robust across PV systems"
- "general rule for all stations"

---

## Section-Specific Editing Rules

### Abstract

The abstract should contain four moves:

1. Problem importance and data-investment cost.
2. Proposed framework.
3. Key empirical findings.
4. Contribution and deployment implication.

Make sure the abstract distinguishes:

- equivalent-accuracy set construction
- significance testing as supplementary reliability check
- PCEI as ranking or recommendation mechanism

Do not overload the abstract with too many model-specific numerical details. Keep only the most representative results.

When the user asks for submission preparation, also check whether Highlights are concise, result-oriented, and aligned with the manuscript's contribution. Highlights should not merely describe the topic; they should state the method novelty, the key empirical finding, or the deployment implication in a compact form.

### Introduction

The introduction should progress as:

1. Forecasting accuracy has operational and economic value.
2. Accuracy improvement requires data investment, which has cost.
3. More data does not necessarily produce proportional accuracy gain.
4. The missing problem is data-investment decision-making, not another forecasting architecture.
5. The paper contributes response characterization, interval-based decision method, and scenario-based recommendation.

Avoid starting with broad energy-transition statements unless they directly lead to the data-investment question.


### Chinese Academic Drafting

When the user is writing a Chinese draft for supervisor review, do not force English word order into Chinese. Produce a supervisor-readable Chinese academic draft that is natural, logically explicit, terminology-consistent, and suitable for later English conversion.

The Chinese draft should:

- make each paragraph's function clear;
- avoid colloquial expressions such as "可以看出", "显然", "效果很好", or "具有重要意义";
- avoid mechanical English-structured Chinese;
- preserve all data, equations, figure/table references, and technical meanings;
- use bounded claims such as "在本文实验条件下" or "该结果为……提供依据" when appropriate.

Prefer Chinese paragraphs that follow: 段落功能句 → 方法或结果 → 解释含义 → 边界说明.

### Related Work

Organize related work into non-overlapping groups:

- forecasting model evolution
- input information expansion
- data efficiency and uncertainty in machine learning
- cost-sensitive forecasting and power-market implications

For each group, include:

- what prior work has solved
- what remains unaddressed
- how this manuscript differs

Do not merely list model names.

### Methods

Methods must define:

- sampling interval as the controlled data-investment variable
- fixed test set
- data retention ratio
- response curve
- equivalent-accuracy set
- PCEI or proxy-cost score
- cost scenarios
- recommendation interval construction

Ensure formulas and text use the same symbols.

If a formula outputs a point but the text discusses an interval, add an explicit interval definition.

### Results

Results should not be a list of tables. Each subsection must answer a specific question.

Recommended sequence:

1. Does reduced data investment necessarily degrade accuracy?
2. Which configurations are accuracy-acceptable?
3. Which acceptable configurations are resource-efficient?
4. Are the observed differences statistically reliable?
5. Are conclusions stable under cross-period or perturbation checks?

For every table or figure, include:

- what is shown
- what pattern matters
- why the pattern supports the research question
- what interpretation boundary applies

When polishing figure-related paragraphs, ensure that the text follows the four-step interpretation pattern: what is shown -> what pattern matters -> why it supports the research question -> what boundary should be attached. Avoid figure references that only repeat the caption without explaining their role in the argument.

### Discussion

Discussion should interpret, not repeat results.

Use discussion to explain:

- why non-monotonic sampling response may occur
- why model structure affects sampling preference
- how deployment decision-makers should use the framework
- what the boundary of the claim is

Mechanistic explanations must be phrased as plausible interpretations unless directly proven.

### Conclusion

The conclusion should not introduce new evidence.

It should state:

1. the decision problem addressed
2. the core empirical finding
3. the proposed methodological contribution
4. the deployment implication
5. the limitation or future extension

Avoid repeating too many numerical values.

### Highlights and Submission Materials

When the user asks for journal submission preparation, check Highlights, graphical abstract wording, figure captions, cover-letter contribution statements, and reviewer-facing claim boundaries.

Highlights should normally be:

- concise and result-oriented
- focused on novelty, method, key finding, or deployment implication
- consistent with the abstract and conclusion
- free from unsupported claims such as "best", "proves", or "universally robust"

For this manuscript type, strong Highlights should emphasize data-investment decision-making, equivalent-accuracy sets, PCEI-based proxy-cost ranking, the final candidate interval, and the tested stability boundary.

### Figure-Text Integration

When revising figure-related text, do not only polish the caption. Also ensure the surrounding paragraph explains the figure's function in the manuscript logic.

Use the following sequence:

1. State what the figure shows.
2. Identify the main pattern or contrast.
3. Explain how the pattern supports the research question.
4. State the interpretation boundary or limitation.

This rule is especially important for response curves, equivalent-accuracy figures, PCEI heatmaps, robustness figures, workflow diagrams, and framework figures.

---

## Preferred Academic Style

Use concise, evidence-linked sentences.

Preferred structure:

- Claim
- Evidence
- Interpretation
- Boundary

Example:

"The results show that the minimum-RMSE configuration does not always coincide with the highest data-retention configuration. This indicates that additional data investment may provide limited marginal accuracy gain under certain model structures. Therefore, sampling-interval selection should be treated as an accuracy-cost decision rather than a purely accuracy-driven choice."

Avoid overly promotional language.

Avoid:

- "this paper perfectly solves"
- "greatly improves"
- "very important"
- "obviously"
- "the best"
- "completely proves"

Use:

- "addresses"
- "indicates"
- "suggests"
- "provides evidence"
- "under the tested setting"
- "offers a decision-support perspective"

---

## Common Replacements

Use the following replacements during polishing.

| Informal or risky wording | Preferred journal wording |
|---|---|
| 数据越多越好 | higher data retention is not necessarily justified |
| 是否值得 | whether additional data investment is justified |
| 性价比 | cost-effectiveness or resource efficiency |
| 最优成本 | preferred cost-effective configuration |
| 推荐成本区间 | recommended data-investment interval |
| 稳健推荐 | stable priority candidate under tested conditions |
| 工程师 | deployment decision-makers / system operators |
| 真实差异 | statistically supported difference |
| 随机差异 | repeated-training variability |
| AI生成感 | formulaic or generic phrasing |
| 包装一下 | improve academic framing |
| 这个结果说明 | this result suggests / indicates / provides evidence that |

---

## Output Modes

When responding to a user request, choose one of the following output modes.

### Mode A: Direct Rewrite

Use when the user asks to polish a paragraph or section.

Output:

1. Revised version
2. Key changes
3. Any caution about overclaiming or missing evidence

### Mode B: Logic Review

Use when the user asks whether the section is logical.

Output:

1. Overall judgment
2. Main logical issue
3. Specific revision plan
4. Suggested replacement text if needed

### Mode C: Reviewer-Style Audit

Use when the user asks whether the manuscript is ready for a high-quality energy journal.

Output:

1. Major issues
2. Minor issues
3. Risky claims
4. Required fixes before submission
5. Optional improvements

### Mode D: Full Section Polish

Use when the user provides a complete section.

Output:

1. Polished section
2. Paragraph-level rationale
3. Terminology corrections
4. Consistency checks

### Mode E: Bilingual Academic Translation

Use when the user asks for English writing.

Output:

1. English polished version
2. Notes on terminology
3. Claims that were softened or strengthened
4. Untranslated terms requiring author confirmation

### Mode F: Chinese Manuscript Development and English Journal Conversion

Use when the user wants to first write or polish a Chinese manuscript for supervisor review and later convert it into an English journal-style draft.

Output:

1. Supervisor-readable Chinese academic draft
2. Paragraph logic explanation
3. Translation-risk notes
4. English journal-style draft, if requested
5. Key terminology mapping
6. Claim-boundary adjustments

---

## Quality Checklist

Before returning revised text, check:

- Does the paragraph support the paper's data-investment decision logic?
- Are "equivalent-accuracy set" and "significance testing" correctly separated?
- Does any sentence overstate robustness or generality?
- Are model-specific claims tied to actual reported results?
- Are proxy-cost claims clearly distinguished from real monetary cost?
- Are the terms sampling interval, data retention ratio, and data investment used consistently?
- Does the revised text sound like an energy journal manuscript rather than a generic AI-generated essay?
- Are all formulas, figures, tables, and numerical values preserved unless the user asks to modify them?

---

## Reference Loading

Use `references/terminology.md` when the task involves terminology correction, English academic phrasing, claim-boundary control, figure/table caption wording, or energy-domain expression.

Use `references/review-checklist.md` when the task involves logic review, reviewer-style audit, submission readiness check, section-level diagnosis, or manuscript-wide quality control.

Use `references/bilingual-writing-guide.md` when the task involves Chinese academic drafting, supervisor-readable Chinese manuscript polishing, Chinese-to-English journal-style conversion, bilingual manuscript development, non-literal translation, or converting a Chinese manuscript into an SCI energy journal English draft.

Use `references/examples.md` when the task involves direct rewriting, paragraph polishing, abstract polishing, contribution rewriting, figure caption improvement, figure-text interpretation, Highlights improvement, cover-letter paragraph drafting, conclusion polishing, reviewer-response drafting, or when the user asks for examples of journal-style phrasing.

For direct paragraph polishing, consult `terminology.md` and `examples.md` first.

For logic review or submission-readiness audit, consult `review-checklist.md` first, then use `terminology.md` and `examples.md` to produce replacement text.

For full-section or full-manuscript review, consult `terminology.md`, `review-checklist.md`, and `examples.md` as needed.

---

## Handling User Manuscripts

When the user uploads a manuscript:

1. Identify the current main contribution.
2. Identify whether the issue is logic, wording, terminology, or claim strength.
3. Do not rewrite the full manuscript unless explicitly asked.
4. Prioritize sections that affect reviewer understanding:
   - abstract
   - introduction
   - methods definitions
   - results interpretation
   - discussion boundaries
   - conclusion
5. Preserve all provided data and citations.
6. If the manuscript contains writing notes such as "temporary", "if reviewers ask", or "optional chapter", flag them for removal or relocation to author notes.

---

## Final Response Standard

Always provide usable text, not only advice.

If the user asks "how should I modify this?", include replacement paragraphs.

If the user asks "is this logical?", include both diagnosis and rewritten wording.

If the user asks for journal-style language, avoid colloquial Chinese and avoid exaggerated English. Use controlled, precise, evidence-based academic language.

If the user asks for Chinese manuscript development, write natural supervisor-readable Chinese rather than translation-like Chinese. Keep the Chinese draft logically explicit and terminology-stable so it can later be converted into journal-style English.
