# Examples for Energy Journal Manuscript Polishing

## Purpose

This file provides reusable before-and-after examples for polishing manuscripts on photovoltaic power forecasting, data-investment decisions, sampling-interval regulation, equivalent-accuracy sets, PCEI, and proxy-cost recommendation.

Use this file together with:

- `SKILL.md`
- `references/terminology.md`
- `references/review-checklist.md`

The examples are written to approximate the style of high-quality energy journals such as Applied Energy, Energy, Energy Conversion and Management, Renewable Energy, Solar Energy, and Renewable and Sustainable Energy Reviews.

The goal is not to imitate any individual paper, but to reproduce common journal-facing writing patterns:

- clear problem motivation;
- structured method description;
- claim-evidence-interpretation-boundary logic;
- cautious discussion of generalization;
- precise separation between prediction accuracy, statistical reliability, and engineering recommendation.

---

## 1. Core Framing Example

### Weak version

> This paper studies whether the sampling interval should be increased. If the sampling interval is larger, the amount of data becomes smaller. We want to know whether this is worth it.

### Polished version

> This study addresses data-investment decision-making in photovoltaic power forecasting. Sampling-interval regulation is used as a controlled protocol to vary the data-retention ratio, and the resulting accuracy-cost response is examined to identify configurations that remain statistically acceptable while reducing resource consumption.

### Why this works

- It frames the paper as a decision problem, not merely a sampling-frequency experiment.
- It uses “data-retention ratio” and “accuracy-cost response,” which sound closer to energy systems and deployment literature.
- It avoids informal wording such as “whether this is worth it.”

---

## 2. Abstract Opening Example

### Weak version

> Photovoltaic power forecasting is very important. However, collecting more data costs more. Therefore, this paper studies the effect of data size.

### Polished version

> Accurate photovoltaic power forecasting is essential for renewable-energy integration, dispatch planning, and market-oriented operation. However, improving forecasting performance often requires denser historical records and larger data-processing effort, which increases acquisition, storage, governance, and model-retraining costs. This raises a deployment-oriented question: whether additional data investment is justified by the resulting accuracy improvement.

### Why this works

- It connects forecasting accuracy to grid and market operation.
- It specifies concrete cost categories.
- It introduces the research question in a precise and non-colloquial way.

---

## 3. Abstract Method Example

### Weak version

> We use several models and different sampling intervals, and then propose PCEI to recommend the best interval.

### Polished version

> A unified experimental protocol is developed by varying the sampling interval while maintaining a fixed test set and consistent model-training settings. The framework first characterizes the response of forecasting error to data-retention changes, then constructs equivalent-accuracy sets using a relative RMSE degradation threshold and 95% confidence-interval overlap, and finally ranks the candidate configurations through a proxy-cost-aware Predictive Cost-Effectiveness Index (PCEI).

### Why this works

- It follows the sequence used in strong methodology abstracts: protocol -> response characterization -> candidate construction -> decision index.
- It correctly separates equivalent-accuracy construction from significance testing.
- It states that PCEI is proxy-cost-aware, not a real market-profit model.

---

## 4. Abstract Result Example

### Weak version

> The results show that less data can sometimes be better and the final recommended interval is 15-40 min.

### Polished version

> The results show that the highest data-retention ratio is not consistently associated with the lowest RMSE. Under the considered dataset, model family, and proxy-cost settings, the high cost-effectiveness candidate interval is concentrated in 15-40 min, corresponding to approximately 12.50%-33.33% data retention. This indicates that lower-data configurations can remain competitive when evaluated jointly with forecasting accuracy and resource consumption.

### Why this works

- It states the final result clearly.
- It gives the interval and data-retention ratio.
- It bounds the claim by dataset, model family, and proxy-cost setting.

---

## 5. Introduction Motivation Example

### Weak version

> Many researchers improve models such as CNN, LSTM, GRU, and Transformer. But we think the problem of data amount is also important.

### Polished version

> Existing photovoltaic forecasting studies have substantially improved prediction accuracy through model-structure innovation, including convolutional, recurrent, attention-based, and hybrid architectures. These studies have clarified how forecasting models can better extract nonlinear temporal patterns from historical power and meteorological inputs. However, the deployment decision is not determined by accuracy alone. In practical forecasting systems, higher temporal resolution and longer data retention also increase data acquisition, storage, cleaning, synchronization, and model-retraining effort. Therefore, it remains necessary to characterize how forecasting performance responds to different data-investment levels.

### Why this works

- It acknowledges prior model progress without dismissing it.
- It transitions from model accuracy to deployment cost.
- It identifies the unresolved problem as response characterization.

---

## 6. Related Work Gap Example

### Weak version

> Previous studies mainly improve accuracy, but few studies discuss data cost.

### Polished version

> Prior work on photovoltaic forecasting can be broadly divided into model-oriented and input-oriented research streams. The former improves forecasting accuracy through neural architectures, decomposition strategies, attention mechanisms, and hybrid statistical-learning models. The latter expands the information available to the forecaster by incorporating historical power, meteorological measurements, numerical weather prediction, sky images, or satellite-derived features. Although these studies have advanced forecasting accuracy, they rarely quantify whether the marginal gain from additional data retention is sufficient to justify the associated resource cost. This leaves a gap between prediction-oriented model design and deployment-oriented data-investment decision-making.

### Why this works

- It groups literature by function.
- It explains what prior work solved.
- It states the remaining gap without saying “few people studied this” in a weak way.

---

## 7. Contribution Statement Example

### Weak version

> The first contribution is that we analyze the effect of data. The second contribution is that we propose PCEI. The third contribution is that we recommend intervals.

### Polished version

> The contributions of this study are threefold. First, it characterizes the response of photovoltaic forecasting accuracy to data-retention changes under a fixed-test-set and repeated-training protocol, revealing model-dependent non-monotonicity and diminishing marginal gain. Second, it proposes an interval-based resource-efficiency framework that combines equivalent-accuracy sets with a proxy-cost-aware PCEI ranking procedure. Third, it reports a high cost-effectiveness candidate interval under multiple proxy-cost scenarios and evaluates its stability through cross-period and perturbation checks.

### Why this works

- Each contribution maps to an experiment.
- It avoids claiming a new forecasting architecture.
- It uses “candidate interval” rather than “universal optimum.”

---

## 8. Method: Sampling Interval as Protocol

### Weak version

> We increase the sampling interval to reduce the amount of data.

### Polished version

> In this study, sampling-interval regulation is used as the experimental protocol for changing the data-retention ratio. Increasing the sampling interval reduces the number of retained observations per unit time, thereby providing a controlled way to examine how reduced data investment affects forecasting accuracy and resource consumption.

### Why this works

- It prevents reviewers from thinking the paper is only about sampling frequency.
- It clarifies that sampling interval is a protocol, not the entire theoretical contribution.

---

## 9. Method: Fixed Test Set

### Weak version

> The training data are changed, and the test set is fixed.

### Polished version

> To ensure comparability across data-retention configurations, all models are evaluated on the same fixed test period. The sampling-interval manipulation is applied to the training-side data configuration, while the test set remains unchanged. This design allows differences in forecasting performance to be attributed primarily to the data-retention setting rather than to changes in the evaluation period.

### Why this works

- It explains why fixed test sets matter.
- It strengthens the causal interpretation of the experiment.

---

## 10. Method: Equivalent-Accuracy Set

### Weak version

> We use 2% RMSE and confidence interval overlap to select similar configurations.

### Polished version

> The equivalent-accuracy set is introduced to avoid over-interpreting small RMSE differences as deployment-relevant accuracy gaps. A configuration is included in this set when its relative RMSE degradation remains within the predefined tolerance and its 95% confidence interval overlaps with that of the accuracy-optimal configuration. The set therefore represents configurations that are acceptable under the adopted engineering tolerance and repeated-run uncertainty criterion, rather than configurations that are strictly identical in a formal statistical sense.

### Why this works

- It explains why the set is needed.
- It clarifies that “equivalent” means practical/engineering acceptability.
- It prevents statistical overclaiming.

---

## 11. Method: Significance Testing

### Weak version

> Significance testing is used to prove whether the result is real.

### Polished version

> Significance testing is used as a supplementary statistical reliability check for the response curves. It examines whether the observed RMSE differences are stable relative to repeated-training variability caused by random initialization, batch ordering, and early-stopping behavior. It does not constitute the decision rule for the recommended interval, which is determined by the equivalent-accuracy set and PCEI-based ranking.

### Why this works

- It separates statistical reliability from engineering recommendation.
- It avoids saying significance “proves” the result.
- It prevents conflict with the equivalent-accuracy set.

---

## 12. Method: PCEI and Proxy Cost

### Weak version

> PCEI calculates the best cost and gives the optimal interval.

### Polished version

> PCEI is formulated as a proxy-cost-aware ranking index rather than a direct monetary-profit model. For each cost scenario, PCEI first identifies a scenario-specific recommended configuration within the accuracy-acceptable candidate space. The recommendation interval is then defined as the range covered by the scenario-level recommendation points. This construction allows deployment decision-makers to adjust the cost weights according to data-governance, retraining, or inference constraints.

### Why this works

- It clarifies that PCEI is not real economic profit.
- It solves the point-to-interval logic issue.
- It explains how cost scenarios become recommendations.

---

## 13. Results: Response Curve Interpretation

### Weak version

> From the figure, we can see that some models do not perform best at 5 min, so more data is not always better.

### Polished version

> The response curves indicate that the minimum-RMSE configuration does not always coincide with the highest data-retention ratio. Several models achieve their best or near-best performance at intermediate sampling intervals, suggesting that additional data retention does not necessarily provide proportional accuracy improvement. This pattern supports the need to evaluate data-retention configurations as an accuracy-cost decision rather than as a purely accuracy-driven selection problem.

### Why this works

- It avoids “we can see.”
- It turns the figure into a logical argument.
- It links the result to the paper’s decision framework.

---

## 14. Results: Equivalent-Accuracy Interpretation

### Weak version

> The recommended interval is not necessarily the one with the lowest RMSE, but it is better overall.

### Polished version

> The recommended interval should not be interpreted as the global minimum-RMSE configuration. Instead, it denotes the configuration that remains within the equivalent-accuracy region while providing greater resource efficiency. This distinction is important because small RMSE differences may not be sufficient to justify substantially higher data retention when training time and data-governance effort are considered.

### Why this works

- It prevents confusion between accuracy optimum and deployment recommendation.
- It explains the role of resource efficiency.

---

## 15. Results: PCEI Heatmap Interpretation

### Weak version

> The heatmap shows that 15-40 min is good, and 40 min appears many times.

### Polished version

> The PCEI heatmap shows that the recommended configurations are not randomly distributed across the full sampling-interval range. Instead, they are concentrated in the 15-40 min interval, corresponding to approximately 12.50%-33.33% data retention. The 40 min configuration appears most frequently under cost-sensitive scenarios, whereas the 20 min configuration provides a stable intermediate option for models requiring a stronger accuracy-resource balance. The 5 min configuration is retained only under strongly error-sensitive conditions, indicating that the highest data-retention setting should be treated as a conservative candidate rather than a default choice.

### Why this works

- It extracts the main pattern from the heatmap.
- It distinguishes cost-sensitive, balanced, and error-sensitive settings.
- It gives the final interval with boundary language.

---

## 16. Results: Marginal Gain

### Weak version

> The marginal gain becomes smaller when data increases.

### Polished version

> The marginal-gain analysis shows that increasing the data-retention ratio from low to intermediate levels can improve RMSE for several models. However, further increasing data retention yields progressively smaller or inconsistent accuracy gains. This indicates that the benefit of additional data investment is stage-dependent and model-dependent, rather than uniformly increasing with denser sampling.

### Why this works

- It avoids an overly universal diminishing-return claim.
- It states that the pattern is stage-dependent and model-dependent.

---

## 17. Results: Non-Significant Differences

### Weak version

> Many results are not significant, so the differences may be random.

### Polished version

> Several configurations do not show statistically significant differences from the high-data baseline after correction for multiple comparisons. This does not imply strict equality; rather, it indicates that small mean-RMSE gaps should not be over-interpreted as sufficient evidence for selecting a higher data-retention configuration. These results further support the use of equivalent-accuracy sets and proxy-cost ranking instead of single-point RMSE minimization.

### Why this works

- It explains non-significance correctly.
- It turns non-significance into support for interval-based recommendation.

---

## 18. Discussion: Mechanistic Interpretation

### Weak version

> The curve is non-monotonic because too much data introduces noise and too little data loses information.

### Polished version

> A plausible explanation for the non-monotonic response is the balance between two competing effects. Dense sampling retains more high-frequency information, but it may also preserve measurement noise and short-lived fluctuations that are difficult to generalize. Conversely, overly sparse sampling reduces data volume and computational cost, but it can miss ramp events and localized irradiance-driven variations. The intermediate configurations may therefore provide a better balance between informative temporal resolution and noise exposure. This interpretation should be regarded as a mechanism-consistent explanation rather than a direct causal proof.

### Why this works

- It provides a plausible mechanism.
- It explicitly limits the claim.
- It avoids overclaiming causality.

---

## 19. Discussion: Deployment Implication

### Weak version

> Engineers can use our result to choose a better sampling interval.

### Polished version

> For deployment decision-makers, the proposed framework provides a practical screening procedure. A target forecasting system can first evaluate several data-retention configurations under a fixed test set, then identify the equivalent-accuracy region, and finally apply cost weights that reflect the deployment context, such as data-governance burden, retraining frequency, or edge-device inference constraints. The resulting recommendation should be treated as a station-specific candidate interval that requires validation before operational adoption.

### Why this works

- It gives a step-by-step deployment procedure.
- It avoids claiming immediate universal adoption.

---

## 20. Discussion: Boundary Statement

### Weak version

> Our method is robust, but more experiments are needed.

### Polished version

> The reported candidate interval is stable under the tested cross-period, perturbation, baseline, and sampling-strategy checks. Nevertheless, the present evidence does not establish a universal rule across all photovoltaic stations, climate zones, forecast horizons, or data-quality conditions. Spatial generalization and monetary cost calibration remain important directions for future work.

### Why this works

- It states what has been validated.
- It states what has not been proven.
- It sounds reviewer-safe.

---

## 21. Conclusion Example

### Weak version

> This paper proves that 15-40 min is the best sampling interval and data does not need to be too dense.

### Polished version

> This study reformulates data-retention selection in photovoltaic power forecasting as an interval-based resource-efficiency decision problem. Under the tested dataset, model family, and proxy-cost scenarios, the highest data-retention ratio is not consistently associated with the best forecasting performance. The proposed equivalent-accuracy and PCEI-based framework identifies 15-40 min as a high cost-effectiveness candidate interval, corresponding to approximately 12.50%-33.33% data retention. This finding suggests that photovoltaic forecasting systems should not automatically default to the densest recording configuration, but should instead select data-retention settings according to accuracy tolerance and deployment cost structure.

### Why this works

- It provides the final answer clearly.
- It uses bounded language.
- It avoids “proves” and “best.”

---

## 22. Highlight Examples

### Weak highlights

- We study sampling intervals.
- PCEI is proposed.
- The model gets good results.
- The interval is robust.

### Polished highlights

- Data-retention selection is formulated as a resource-efficiency decision problem.
- Equivalent-accuracy sets identify configurations with acceptable RMSE degradation.
- PCEI ranks accuracy-acceptable configurations under proxy-cost scenarios.
- A 15-40 min candidate interval balances forecasting accuracy and data investment.
- Cross-period and perturbation checks define the stability boundary of the recommendation.

### Why this works

- Each highlight states a concrete contribution or result.
- The wording is concise and journal-facing.
- It avoids unsupported claims of universal robustness.

---

## 23. Figure Caption Examples

### Framework figure

Weak:

> Flowchart of this paper.

Polished:

> Overall framework for data-investment decision-making in photovoltaic power forecasting under sampling-interval regulation.

### Response curve

Weak:

> RMSE under different intervals.

Polished:

> RMSE response curves under different data-retention ratios across forecasting models.

### Equivalent-accuracy set

Weak:

> Recommended intervals.

Polished:

> Identification of equivalent-accuracy configurations under the 2% RMSE degradation threshold and 95% confidence-interval overlap criterion.

### PCEI heatmap

Weak:

> Heatmap of optimal intervals.

Polished:

> Recommended sampling intervals under different proxy-cost scenarios.

### Robustness checks

Weak:

> Robustness results.

Polished:

> Stability of sampling-interval responses under cross-period, perturbation, and resampling-strategy checks.

---

## 24. Cover Letter Contribution Paragraph

### Draft template

> This manuscript addresses an underexplored deployment problem in photovoltaic power forecasting: whether additional data retention is justified by the resulting accuracy gain. Rather than proposing another forecasting architecture, the study develops an interval-based resource-efficiency framework that combines fixed-test-set response characterization, equivalent-accuracy sets, and proxy-cost-aware PCEI ranking. The results show that the highest data-retention ratio is not consistently optimal and that a 15-40 min candidate interval can provide a favorable accuracy-resource balance under the tested protocol. We believe this work is relevant to readers interested in renewable-energy forecasting, data-efficient model deployment, and cost-sensitive operation of photovoltaic systems.

### Use case

Use this when drafting a cover letter for Applied Energy, Energy, Energy Conversion and Management, Renewable Energy, or Solar Energy.

---

## 25. Reviewer-Response Example: Significance Testing

### Reviewer concern

> The manuscript reports significance tests, but it is unclear whether they determine the recommended interval.

### Response template

> We thank the reviewer for pointing out this potential ambiguity. We have revised the manuscript to clarify that significance testing is not used as the decision rule for the recommended interval. The equivalent-accuracy set is constructed using the relative RMSE degradation threshold and 95% confidence-interval overlap. Significance testing is reported only as a supplementary reliability check to examine whether observed RMSE differences are stable relative to repeated-training variability. The final recommendation is obtained through PCEI-based ranking within the accuracy-acceptable candidate space.

---

## 26. Reviewer-Response Example: Proxy Cost

### Reviewer concern

> The proposed PCEI may not represent real economic cost.

### Response template

> We agree with the reviewer. PCEI is intended as a proxy-cost-aware ranking index rather than a direct monetary-profit model. We have revised the manuscript to make this distinction explicit. The current implementation uses normalized data-retention ratio, training time, and inference time as resource proxies, allowing the framework to compare configurations under different deployment priorities. Real monetary calibration, including market settlement and data-management cost coefficients, is identified as an important extension for future work.

---

## 27. Reviewer-Response Example: Generalization

### Reviewer concern

> The recommended interval may not generalize to all PV stations.

### Response template

> We agree that the recommended interval should not be interpreted as a universal sampling rule. We have revised the text to describe it as a high cost-effectiveness candidate interval under the present dataset, model family, proxy-cost setting, and experimental protocol. Cross-period, perturbation, baseline, and sampling-strategy checks are used to evaluate stability within the tested conditions, while spatial generalization across additional PV stations and climate zones is left for future work.

---

## 28. Quick Editing Patterns

### Pattern A: Avoid overclaiming

Before:

> This proves that the proposed interval is robust.

After:

> This provides evidence that the candidate interval remains stable under the tested temporal and perturbation conditions.

### Pattern B: Clarify proxy cost

Before:

> The proposed method finds the optimal cost.

After:

> The proposed method identifies a proxy-cost-efficient configuration under the specified cost-weight scenario.

### Pattern C: Separate significance testing

Before:

> The equivalent-accuracy set is constructed based on RMSE, confidence interval, and significance test.

After:

> The equivalent-accuracy set is constructed using the RMSE degradation threshold and 95% confidence-interval overlap, while significance testing is used as a supplementary reliability check.

### Pattern D: Emphasize decision logic

Before:

> The model performs well at 40 min.

After:

> The 40 min configuration remains within the acceptable accuracy region while substantially reducing data retention and training time, making it a resource-efficient candidate under the tested protocol.

### Pattern E: Bound the final result

Before:

> The optimal interval is 15-40 min.

After:

> Under the considered dataset, model family, and proxy-cost settings, the high cost-effectiveness candidate interval is concentrated in 15-40 min.

---

## 29. Final Rule

When polishing any paragraph, make sure the revised text answers at least one of these questions:

1. What decision problem is being addressed?
2. What evidence supports the claim?
3. What does the evidence mean for data-investment selection?
4. What is the boundary of the claim?
5. How does this sentence help the reader follow the paper's logic?

If a sentence answers none of these questions, remove or rewrite it.

---

## 30. Figure-Text Integration Example

### Weak version

> Fig. 9 shows the PCEI heatmap. The recommended intervals are different under different scenarios.

### Polished version

> Fig. 9 summarizes the scenario-specific sampling intervals selected by the PCEI ranking procedure. The recommended configurations are concentrated in the 15-40 min range rather than being uniformly distributed across all tested intervals. This concentration supports the interpretation that the equivalent-accuracy set can be converted into a practical high cost-effectiveness candidate interval when resource proxies are considered. The result should be interpreted within the present dataset, model family, and proxy-cost settings rather than as a universal sampling rule.

### Why this works

- It states what the figure shows.
- It identifies the key visual pattern.
- It connects the figure to the paper's central decision logic.
- It adds the correct boundary statement.

---

## 31. Response-Curve Figure Interpretation Example

### Weak version

> Fig. 4 shows the RMSE curves of different models, and the curves are not the same.

### Polished version

> Fig. 4 presents the RMSE response curves across data-retention configurations for the evaluated forecasting models. The curves show that the lowest RMSE does not consistently occur at the highest data-retention ratio, and several models achieve comparable performance at intermediate sampling intervals. This pattern provides empirical support for treating sampling-interval selection as an accuracy-cost decision rather than a default preference for dense data retention. However, the model-dependent curve shapes indicate that the candidate interval should be validated for the target architecture and station before deployment.

### Why this works

- It turns a descriptive sentence into a claim-evidence-boundary paragraph.
- It avoids saying "the figure proves".
- It explicitly links response curves to the paper's contribution.

---

## 32. Highlight Refinement Example

### Weak highlights

- The influence of sampling interval is studied.
- PCEI is proposed for PV forecasting.
- The results are robust.
- The method is useful for engineering.

### Polished highlights

- Data-retention selection is formulated as a resource-efficiency decision problem.
- Equivalent-accuracy sets identify sampling configurations with acceptable RMSE loss.
- PCEI ranks accuracy-acceptable configurations under proxy-cost scenarios.
- A 15-40 min candidate interval balances forecasting accuracy and data investment.
- Cross-period and perturbation checks define the stability boundary of the interval.

### Why this works

- Each Highlight states a contribution or result.
- The wording is concise and submission-oriented.
- The claims are bounded and do not overstate robustness.

---

## 33. Graphical Abstract Description Example

### Weak version

> The graphical abstract should show the process of this paper.

### Polished version

> The graphical abstract should present the decision pipeline from data-retention control to deployment recommendation. A suitable layout is: fixed PV dataset and sampling-interval regulation -> repeated model training and response-curve characterization -> equivalent-accuracy set construction -> PCEI ranking under proxy-cost scenarios -> high cost-effectiveness candidate interval with stability checks.

### Why this works

- It converts a vague figure request into a journal-style workflow.
- It aligns the figure with the manuscript's logic chain.
- It avoids overloading the graphical abstract with secondary experiments.

---

## 34. Supervisor-Readable Chinese Draft Example

### Raw Chinese

> 可以看出，15–40 min 的采样间隔效果比较好，说明数据不用太多。

### Supervisor-readable Chinese academic draft

> 结果表明，在本文数据源、模型族和代理成本设定下，推荐配置主要集中在 15–40 min 区间。该区间对应较低的数据保留比例，同时仍处于等价精度集范围内，说明较高数据投入并不必然带来与资源消耗相匹配的精度收益。

### English journal-style draft

> The results show that, under the considered dataset, model family, and proxy-cost settings, the recommended configurations are concentrated in the 15–40 min interval. This interval corresponds to a lower data-retention ratio while remaining within the equivalent-accuracy region, indicating that higher data investment is not necessarily justified by proportional accuracy improvement.

### Why this works

- The Chinese version is natural for supervisor review.
- The English version is not a literal translation.
- Both versions preserve the same claim boundary.

---

## 35. Avoid Translation-Like Chinese Example

### Translation-like Chinese

> 本研究解决光伏功率预测中的数据投入决策问题，并且采样间隔调节被用于作为控制协议以变化数据保留比例。

### Supervisor-readable Chinese academic draft

> 本文关注光伏功率预测中的数据投入决策问题。为刻画数据投入变化对预测精度和资源消耗的影响，本文将采样间隔调节作为降低数据保留比例的实验手段。

### English journal-style draft

> This study addresses data-investment decision-making in photovoltaic power forecasting. Sampling-interval regulation is used as a controlled protocol to reduce the data-retention ratio and characterize the effects of data-investment changes on forecasting accuracy and resource consumption.

### Why this works

- The revised Chinese does not follow mechanical English word order.
- The English conversion uses standard journal phrasing.
- The concept of sampling-interval regulation remains an experimental protocol, not the entire contribution.

---

## 36. Chinese-to-English Claim Boundary Example

### Raw Chinese

> 本文证明了推荐区间具有很强鲁棒性。

### Supervisor-readable Chinese academic draft

> 跨时期和扰动实验为推荐区间的稳定性提供了支持，但该结论仍限于本文数据源、模型族和实验协议。

### English journal-style draft

> The cross-period and perturbation experiments provide supporting evidence for the stability of the recommended interval. However, this conclusion remains bounded by the dataset, model family, and experimental protocol used in this study.

### Why this works

- The Chinese version is acceptable for supervisor review.
- The English version avoids overclaiming robustness.
- The evidence boundary is explicit in both languages.
