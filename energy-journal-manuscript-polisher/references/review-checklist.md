# Review Checklist for Energy Journal Manuscript Polishing

## Purpose

This checklist is designed for reviewing manuscripts on photovoltaic power forecasting, data-investment decisions, sampling-interval regulation, equivalent-accuracy sets, and cost-effectiveness analysis before submission to high-quality SCI energy journals.

Use this file together with `SKILL.md` and `references/terminology.md` when polishing, auditing, or revising manuscripts for journals such as Applied Energy, Energy, Energy Conversion and Management, Renewable Energy, Solar Energy, and Renewable and Sustainable Energy Reviews.

The checklist focuses on:

- logic closure
- claim-evidence consistency
- energy-journal style
- methodological precision
- statistical interpretation
- proxy-cost framing
- reviewer-facing risk control
- submission readiness

---

## 0. Reference Basis

This checklist reflects common author-facing expectations in major energy journals, especially:

- concise and factual abstracts;
- clear novelty and importance statements;
- 3-5 highlights with strong novelty or result focus;
- editable equations and tables rather than images;
- clearly numbered equations;
- professional figures, graphical abstracts, and figure captions;
- explicit distinction between methods, results, discussion, limitations, and conclusions;
- transparent handling of statistics, uncertainty, assumptions, and evidence boundaries.

When reviewing a manuscript, do not only ask whether the writing is fluent. Ask whether every claim is supported by a method, a figure, a table, or a bounded interpretation.

---

## 1. Manuscript-Level Logic Check

### 1.1 Core problem clarity

The manuscript should clearly state the central problem:

> Additional data investment in photovoltaic power forecasting may increase resource cost, but its marginal accuracy gain may be limited, saturated, or non-monotonic.

The manuscript should not be framed merely as:

- a model comparison paper;
- a sampling-frequency experiment;
- a generic deep-learning benchmark;
- a paper that only asks which model has the lowest RMSE.

Preferred framing:

> The study evaluates whether additional data retention is justified under accuracy and resource constraints.

### 1.2 Required logical chain

Confirm that the manuscript follows this chain:

1. Photovoltaic forecasting accuracy has operational and economic value.
2. Higher data retention has acquisition, storage, governance, training, and deployment costs.
3. Sampling-interval regulation is used as a controlled protocol to vary data retention.
4. Fixed-test-set experiments reveal the accuracy response curve.
5. The response curve may be non-monotonic or show diminishing marginal gain.
6. Equivalent-accuracy sets identify accuracy-acceptable configurations.
7. PCEI or proxy-cost analysis ranks candidate configurations under deployment scenarios.
8. Cross-period, daylight, perturbation, baseline, and sampling-strategy checks define the evidence boundary.
9. The final recommendation is a candidate interval under the tested protocol, not a universal rule.

### 1.3 Red flags

Flag the manuscript if it:

- jumps from RMSE minimum directly to engineering recommendation;
- treats significance testing as the recommendation rule;
- treats proxy cost as real monetary cost;
- claims universal robustness from a single station or single data source;
- describes sampling interval as the whole contribution rather than the experimental protocol;
- fails to explain why a lower-data configuration is acceptable in accuracy terms.

---

## 2. Abstract Checklist

### 2.1 Required content

The abstract should include four elements:

1. **Problem**: forecasting accuracy is valuable, but data investment is costly.
2. **Method**: sampling-interval regulation, equivalent-accuracy set, and PCEI/proxy-cost scenarios.
3. **Results**: main empirical finding with representative numerical evidence.
4. **Contribution**: data-retention selection is reframed as an interval-based resource-efficiency decision.

### 2.2 Accuracy of method description

Check that the abstract states:

Correct:

> The equivalent-accuracy set is constructed using a relative RMSE degradation threshold and 95% confidence-interval overlap.

Correct:

> Significance testing is used as a supplementary reliability check.

Incorrect:

> The equivalent-accuracy set is constructed using the RMSE threshold, confidence intervals, and significance testing.

### 2.3 Claim strength

Avoid overstrong abstract claims such as:

- proves the optimal sampling interval;
- robust recommendation for PV systems;
- real cost optimization;
- universally applicable interval.

Preferred wording:

- under the tested dataset and model family;
- under the adopted proxy-cost setting;
- provides a decision-support framework;
- identifies a high cost-effectiveness candidate interval.

### 2.4 Standalone quality

The abstract should be understandable without reading the main text. It should define uncommon abbreviations at first use, such as:

- Predictive Cost-Effectiveness Index (PCEI)
- root mean square error (RMSE), if appropriate

### 2.5 Highlights quality

When Highlights are required by the target journal, check whether they are:

- concise and result-oriented;
- aligned with the contribution statements;
- focused on method novelty, empirical findings, or deployment implications;
- free from vague claims such as "the model performs well";
- bounded when referring to stability, robustness, or recommendation intervals.

For this manuscript type, strong Highlights may emphasize:

- data-retention selection as a resource-efficiency decision problem;
- equivalent-accuracy sets for identifying acceptable configurations;
- PCEI ranking under proxy-cost scenarios;
- the final high cost-effectiveness candidate interval;
- cross-period and perturbation checks defining the stability boundary.

Avoid Highlights that only repeat the topic, such as:

- "PV forecasting is studied."
- "Different sampling intervals are compared."
- "The proposed method is robust."

---

## 3. Introduction Checklist

### 3.1 Motivation structure

The introduction should progress as:

1. PV forecasting accuracy affects dispatch, reserve allocation, imbalance settlement, and deployment.
2. Accuracy improvement often requires denser data and larger data-processing effort.
3. Higher data investment has acquisition, storage, governance, training, retraining, and deployment costs.
4. More data may not always provide proportional accuracy gain.
5. Therefore, the research question is data-investment decision-making, not merely model improvement.

### 3.2 Related work grouping

Related work should be grouped by function, not listed chronologically.

Recommended groups:

- forecasting model evolution;
- input information expansion;
- data efficiency and repeated-run uncertainty;
- cost-sensitive forecasting and power-market implications.

For each group, check whether the manuscript states:

- what prior work has solved;
- what remains unaddressed;
- how the present paper differs.

### 3.3 Research gap

A strong gap statement should follow this form:

> Although prior work has improved forecasting accuracy through model and input innovations, the accuracy response to different data-investment levels remains insufficiently characterized. In particular, the field lacks an interval-based method for identifying accuracy-acceptable and resource-efficient data-retention configurations.

Avoid vague gaps such as:

- few people have studied this;
- this problem is very important;
- there are great challenges.

### 3.4 Contributions

Each contribution should map to one research gap and one experiment.

Check:

- Contribution 1: response curve characterization.
- Contribution 2: equivalent-accuracy set and PCEI framework.
- Contribution 3: scenario-based recommendation and stability checks.

Avoid contribution claims that sound like:

- a new deep-learning model, if the paper does not propose one;
- universal sampling rules, if the evidence is single-site or single-data-source;
- full economic optimization, if only proxy costs are used.

---

## 4. Methodology Checklist

### 4.1 Sampling interval as data-investment protocol

The manuscript must state clearly:

> Sampling interval regulation is used as the controlled experimental protocol for changing the data-retention ratio.

Check whether it avoids saying:

> Sampling interval is the only form of data investment.

### 4.2 Fixed test set

Confirm that:

- the test period is fixed across sampling intervals;
- model comparisons are performed on the same test horizon;
- the manuscript avoids changing both training and test distributions without explanation.

### 4.3 Input window and sampling interval

Check whether the manuscript clarifies:

- whether the historical coverage length is fixed;
- whether the number of input time steps changes as sampling interval changes;
- why this is consistent with the data-investment protocol.

### 4.4 Equivalent-accuracy set

The method must define:

1. repeated-run RMSE;
2. accuracy-optimal configuration;
3. relative RMSE degradation;
4. 95% confidence interval;
5. equivalent-accuracy set rule.

Correct construction:

> relative RMSE degradation threshold + 95% confidence-interval overlap

Incorrect construction:

> relative RMSE threshold + CI overlap + significance testing

### 4.5 Significance testing

Check whether the manuscript states:

- significance testing is supplementary;
- it examines whether RMSE differences are stable relative to repeated-training variability;
- it does not directly determine the recommended configuration;
- non-significance does not prove equality.

Preferred wording:

> Significance testing is used as a statistical reliability check rather than a recommendation rule.

### 4.6 PCEI and proxy-cost method

Confirm that PCEI or proxy-cost analysis specifies:

- what variables enter the score;
- how each variable is normalized;
- what the cost weights mean;
- whether inference time is included or only retained as an interface;
- whether PCEI is applied inside the equivalent-accuracy set or alongside it;
- what output is used for the recommendation heatmap.

### 4.7 Point-to-interval definition

If a formula outputs a point but the text reports an interval, the manuscript must define how the interval is obtained.

Preferred definition:

> For each cost scenario, PCEI first yields a scenario-specific recommended configuration. The recommendation interval is defined as the range covered by these scenario-level recommendation points.

Flag the manuscript if it says:

> PCEI directly outputs a continuous interval.

### 4.8 Proxy cost versus real cost

Check whether the manuscript distinguishes:

- proxy cost;
- computational cost;
- data-governance cost;
- real monetary cost;
- market profit or imbalance-settlement value.

Preferred statement:

> PCEI is a proxy-cost indicator and should not be interpreted as a direct monetary return or market profit.

---

## 5. Experimental Design Checklist

### 5.1 Dataset description

Check whether the manuscript reports:

- data period;
- original temporal resolution;
- missing timestamp ratio;
- active power range;
- mean active power;
- role of each period;
- variables used for modeling.

### 5.2 Training protocol

Check whether the manuscript reports:

- training/validation/test split;
- repeated training runs;
- random seeds;
- optimizer;
- learning rate;
- batch size;
- early stopping;
- maximum epochs;
- whether hyperparameters are fixed across sampling intervals.

### 5.3 Resource measurement

Check whether the manuscript reports:

- training time measurement rule;
- inference time measurement rule, if used;
- hardware environment;
- software environment;
- whether wall-clock time is comparable across settings.

### 5.4 Experimental module alignment

Each experiment should map to a research question.

Recommended mapping:

- E1: sampling interval scan -> response curve and model dependence.
- E2: marginal gain and significance testing -> statistical reliability and diminishing return.
- E3: equivalent-accuracy set -> candidate space.
- E4: PCEI/proxy-cost scenarios -> recommendation interval.
- E5: daylight, cross-period, noise, baseline, sampling strategy -> boundary and stability checks.

### 5.5 Non-main experiments

If an experiment is not central, do not label it in the manuscript as:

- optional;
- temporary;
- if reviewers ask;
- non-main line.

Instead, phrase it as:

- supplementary validity check;
- auxiliary contrast;
- sensitivity analysis;
- stability-boundary analysis.

---

## 6. Results Section Checklist

### 6.1 Section order

A strong results section should answer the main question before presenting secondary checks.

Recommended order:

1. Accuracy response under reduced data investment.
2. Marginal gain and statistical reliability.
3. Equivalent-accuracy set and resource-efficient candidates.
4. PCEI/proxy-cost recommendation interval.
5. Daylight, training-history, cross-period, and robustness checks.

### 6.2 Each subsection should answer one question

For every subsection, check whether the first sentence states the purpose.

Examples:

- "This subsection examines whether reducing data retention necessarily degrades RMSE."
- "This subsection identifies configurations that remain accuracy-acceptable under the predefined tolerance."
- "This subsection converts the candidate set into proxy-cost-aware deployment recommendations."

### 6.3 Table and figure interpretation

For every table or figure, the manuscript should state:

1. what is shown;
2. which pattern matters;
3. why it supports the research question;
4. what the boundary of the interpretation is.

Avoid only restating values.

### 6.4 Non-monotonic response

Check whether the manuscript explains:

- which models prefer dense input;
- which models achieve best or near-best performance at lower data retention;
- whether the result is model-dependent;
- why "higher data retention" should not be automatically selected.

### 6.5 Equivalent-accuracy results

Check whether the results clarify:

- the recommended interval is not always the minimum-RMSE interval;
- it is selected within the accuracy-acceptable candidate set;
- a lower data-retention option can be recommended only if accuracy loss is within tolerance.

### 6.6 PCEI recommendation

Check whether the results provide a final answer such as:

> Under the present dataset, model family, and proxy-cost setting, the high cost-effectiveness candidate interval is concentrated in 15-40 min, corresponding to approximately 12.50%-33.33% data retention.

This statement must be bounded by:

- dataset;
- model family;
- proxy-cost setting;
- tested protocol.

### 6.7 Statistical testing interpretation

Check whether the manuscript avoids saying:

- non-significant differences are meaningless;
- significant differences directly determine the recommendation;
- significance proves deployment value.

Preferred interpretation:

> Significance testing helps identify which RMSE differences are stable relative to repeated-run variability. It does not replace the equivalent-accuracy set or PCEI-based ranking.

### 6.8 Robustness and stability

Check whether stability is bounded.

Preferred:

> The candidate interval shows cross-period and perturbation stability under the tested conditions.

Avoid:

> The interval is robust for all PV systems.

---

## 7. Discussion Checklist

### 7.1 Discussion should interpret, not repeat

The discussion should not simply repeat tables. It should explain:

- why non-monotonic response may occur;
- why sampling preference differs by model structure;
- how deployment decision-makers can use the framework;
- what is not proven.

### 7.2 Mechanistic explanation

Mechanistic interpretations should be cautious.

Preferred:

> The non-monotonic response may arise from a balance between high-frequency noise retention under dense sampling and loss of ramp information under overly sparse sampling.

Avoid:

> Dense sampling causes overfitting and sparse sampling loses dynamics.

unless directly proven.

### 7.3 Model-structure discussion

The manuscript may state:

> Model-dependent sampling preference suggests that data-retention decisions should be evaluated jointly with forecasting architecture.

Avoid:

> This model definitely works better because of its structure.

### 7.4 Engineering implications

The discussion should translate the framework into a deployment procedure:

1. run a fixed-test-set sampling interval scan;
2. construct the equivalent-accuracy set;
3. calculate PCEI or proxy-cost score under relevant cost weights;
4. identify stable candidate intervals;
5. validate the interval on the target station and forecast horizon.

### 7.5 Limitations

The limitations should include:

- single station or limited data source;
- proxy cost rather than full monetary cost;
- one forecast horizon if applicable;
- sampling interval changes both sample number and temporal resolution;
- need for pure sample-size control experiments, if not central;
- need for more stations and climate zones.

---

## 8. Conclusion Checklist

### 8.1 Conclusion structure

A strong conclusion should include:

1. what decision problem was addressed;
2. what empirical response pattern was found;
3. what methodological framework was proposed;
4. what interval or deployment implication was identified;
5. what boundary remains.

### 8.2 Avoid new evidence

The conclusion should not introduce:

- new numerical results;
- new mechanisms;
- new literature;
- new claims not supported earlier.

### 8.3 Correct method summary

Check that the conclusion says:

Correct:

> The equivalent-accuracy set is constructed using the relative RMSE threshold and 95% CI overlap, with significance testing used as a supplementary reliability check.

Incorrect:

> The equivalent-accuracy set is constructed using significance testing.

### 8.4 Final deployment message

Preferred final message:

> Photovoltaic forecasting systems should not automatically default to the highest recording frequency; instead, they should identify statistically acceptable and resource-efficient data-retention configurations under the target deployment setting.

---

## 9. Figures and Tables Checklist

### 9.1 General requirements

Check whether figures and tables are:

- necessary for the argument;
- readable in grayscale or black-and-white print;
- self-contained with clear captions;
- referenced in the text before or near appearance;
- not duplicating each other without purpose.

For each important figure, the surrounding text should follow the four-step interpretation pattern:

1. What the figure shows.
2. What pattern or contrast matters.
3. Why the pattern supports the research question.
4. What boundary or limitation applies.

Flag figure-related paragraphs that only say "Fig. X shows..." without explaining why the figure matters.

### 9.2 Framework figure

The framework figure should show:

1. fixed dataset and sampling interval regulation;
2. model training and response-curve characterization;
3. equivalent-accuracy set;
4. PCEI/proxy-cost ranking;
5. final recommendation interval;
6. robustness or stability checks.

### 9.3 Response curve figure

The response curve figure should show:

- x-axis as data-retention ratio or sampling interval;
- y-axis as RMSE or another primary metric;
- consistent model labeling;
- confidence intervals if available.

### 9.4 Equivalent-accuracy figure

The equivalent-accuracy figure should show:

- accuracy-optimal configuration;
- configurations inside the equivalent-accuracy set;
- configurations outside the set;
- threshold used.

### 9.5 PCEI heatmap

The heatmap should clearly show:

- models;
- cost scenarios;
- recommended sampling intervals;
- final interval concentration.

Caption should not overclaim. Preferred:

> Recommended sampling intervals under different proxy-cost scenarios.

Avoid:

> The universally optimal sampling interval.

### 9.6 Tables

Tables should be editable text, not images. Each table should have:

- units in column headings;
- abbreviations explained in notes;
- consistent precision;
- no row-label mismatch;
- no mixed English-Chinese labels unless intended.

---

## 10. Chinese Draft and English Conversion Checklist

### 10.1 Supervisor-readable Chinese draft

When reviewing a Chinese draft intended for supervisor review, check whether:

- the Chinese reads naturally rather than like translated English;
- each paragraph has a clear function;
- terminology is consistent across sections;
- claims are bounded by the experiment;
- colloquial phrases such as "可以看出", "显然", "效果很好", and "具有重要意义" are avoided;
- the paragraph structure supports later English conversion without sacrificing Chinese readability.

### 10.2 English journal-style conversion

When reviewing an English conversion, check whether:

- the English is non-literal rather than word-by-word translation;
- the paragraph has a clear topic sentence;
- Chinese long sentences are split into readable English sentences;
- verbs such as show, indicate, suggest, demonstrate, and provide evidence are used with appropriate strength;
- all numerical values, equations, model names, and figure/table references are preserved;
- claim boundaries are explicit.

### 10.3 Bilingual consistency

Check whether the Chinese and English versions preserve the same scientific meaning while using language appropriate to each audience. The Chinese version should serve supervisor review; the English version should serve journal submission.

## 11. Language and Style Checklist

### 10.1 Replace informal wording

Avoid:

- very important;
- obviously;
- great difficulty;
- whether it is worth it;
- cheap and good;
- the best model;
- proves robustness.

Use:

- operationally relevant;
- provides evidence that;
- raises a deployment-oriented question;
- whether additional data investment is justified;
- resource-efficient;
- achieves the lowest RMSE under the tested setting;
- shows stability under the tested conditions.

### 10.2 Avoid AI-like generic writing

Flag sentences that are:

- broad but unsupported;
- repetitive;
- filled with generic transitions;
- not tied to a figure, table, method, or result.

Examples to revise:

- "This issue is very important."
- "The results are meaningful."
- "This paper has certain innovation."
- "The model has good performance."

### 10.3 Preferred sentence pattern

Use:

> Claim + evidence + interpretation + boundary.

Example:

> The results show that CNN and CNN-LSTM-Attention achieve their lowest RMSE at 40 min and 20 min, respectively. This indicates that the highest data-retention ratio is not always necessary under the tested protocol. However, this finding remains model-dependent and should be validated for the target station before deployment.

---

## 12. Statistical and Methodological Risk Checklist

### 11.1 Small repeated-run count

If the manuscript uses few repeated runs, avoid overclaiming statistical power.

Preferred:

> The repeated-run analysis provides a reliability check rather than a definitive equivalence proof.

### 11.2 Confidence interval overlap

Do not treat CI overlap as a formal equivalence test unless the method uses formal equivalence testing.

Preferred:

> The CI-overlap rule is used as a practical criterion for identifying accuracy-acceptable configurations.

### 11.3 Multiple testing

If many pairwise tests are performed, check whether the manuscript uses or mentions multiple-comparison correction.

Preferred:

> Benjamini-Hochberg correction is used to control false-discovery risk across multiple comparisons.

### 11.4 Proxy cost

If proxy cost is used, check whether the manuscript avoids real monetary conclusions.

Preferred:

> The score provides a proxy-cost ranking rather than a direct market-profit calculation.

### 11.5 Sampling interval interpretation

Check whether the manuscript acknowledges:

> Changing sampling interval changes both sample count and temporal resolution.

This prevents overclaiming that the experiment isolates pure sample-size effects.

---

## 13. Reviewer-Risk Checklist

### Major reviewer risks

Flag and fix before submission:

- Method definition inconsistent across abstract, methods, and conclusion.
- Significance testing described as part of equivalent-accuracy set construction.
- PCEI formula outputs a point, but text claims an interval without definition.
- Robustness claim exceeds tested data scope.
- Proxy-cost score treated as actual monetary value.
- Optional or temporary section labels remain.
- Formula symbols differ between text and equation.
- Tables contain row-label or unit errors.
- Figures are not referenced or not interpreted.
- The conclusion introduces claims not shown in results.

### Moderate reviewer risks

- Too many model-specific numbers in abstract.
- Related work is a list rather than a structured gap.
- Discussion repeats results rather than explaining them.
- The final recommended interval lacks a boundary statement.
- Cost scenarios are not explained in practical deployment terms.
- The role of inference time is unclear.

### Minor reviewer risks

- Inconsistent capitalization of RMSE, PCEI, PV.
- Mixed "sampling frequency" and "sampling interval" without distinction.
- "Robust" and "stable" used interchangeably.
- Chinese-style long sentences in English translation.
- Excessive passive voice or formulaic AI transitions.

---

## 14. Final Pre-Submission Checklist

Before submission, verify:

- [ ] Abstract correctly separates equivalent-accuracy construction from significance testing.
- [ ] Contributions map to research questions and experiments.
- [ ] Sampling interval is described as the protocol for changing data retention.
- [ ] Fixed test set is explicitly stated.
- [ ] Equivalent-accuracy set formula matches the text.
- [ ] PCEI or proxy-cost formula matches the implementation.
- [ ] Recommendation interval is formally defined from scenario-level outputs.
- [ ] The final high cost-effectiveness interval is stated with boundaries.
- [ ] Robustness claims are limited to tested conditions.
- [ ] Limitations acknowledge single-source or limited spatial evidence.
- [ ] Tables are editable and units are clear.
- [ ] Figures are readable and cited in the text.
- [ ] Each major figure is interpreted using the pattern: shown content -> key pattern -> research relevance -> boundary.
- [ ] Highlights are concise, result-oriented, and aligned with the contribution and conclusion.
- [ ] No author notes remain in section titles.
- [ ] All formulas are editable and numbered consistently.
- [ ] References are formatted according to the target journal.
- [ ] Highlights and cover letter claims match the manuscript.

---

## 15. Recommended Reviewer-Style Summary Template

Use this template when auditing a manuscript section:

### Overall judgment

State whether the section is logically sound, partially sound, or needs restructuring.

### Main issue

Identify the most important problem, not every small wording issue.

### Required fix

Give the exact change needed.

### Suggested replacement

Provide a ready-to-use rewritten paragraph if possible.

### Risk if not fixed

Explain how a reviewer may criticize the issue.

---

## 16. Example Reviewer Comments and Fixes

### Comment 1

> The manuscript appears to confuse significance testing with equivalent-accuracy set construction.

Fix:

> State that the equivalent-accuracy set is constructed using the RMSE degradation threshold and 95% CI overlap. Move significance testing to a supplementary reliability-check role.

### Comment 2

> The method outputs single recommended configurations, whereas the conclusion claims a recommendation interval.

Fix:

> Define the recommendation interval as the range covered by scenario-level recommendation points across the considered cost scenarios.

### Comment 3

> The robustness claim is too strong for the available evidence.

Fix:

> Replace "robust recommendation" with "priority candidate interval under the tested cross-period and perturbation conditions."

### Comment 4

> The economic interpretation is overstated.

Fix:

> Clarify that PCEI is a proxy-cost index and not a direct monetary profit or market-settlement model.

### Comment 5

> The paper reads like a model-performance comparison rather than a data-investment decision study.

Fix:

> Reframe the results around data-retention response, equivalent-accuracy candidates, and proxy-cost recommendation intervals instead of only ranking models by RMSE.
