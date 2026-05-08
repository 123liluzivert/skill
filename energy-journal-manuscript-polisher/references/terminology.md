# Terminology for Energy Journal Manuscript Polishing

## Purpose

This file defines preferred terminology, phrasing conventions, and claim boundaries for manuscripts on photovoltaic power forecasting, data-investment decisions, sampling-interval regulation, equivalent-accuracy sets, and cost-effectiveness analysis.

Use this reference when polishing manuscripts for SCI energy journals such as Applied Energy, Energy, Energy Conversion and Management, Renewable Energy, Solar Energy, and Renewable and Sustainable Energy Reviews.

The goal is to make the manuscript sound like a rigorous energy-systems paper rather than a generic machine-learning report.

---

## 1. Core Framing

### Preferred high-level framing

Use:

- data-investment decision
- data-retention configuration
- sampling-interval regulation
- resource-efficient forecasting
- cost-effectiveness interval
- accuracy-cost trade-off
- forecasting accuracy versus data-processing cost
- statistically acceptable accuracy region
- deployment-oriented recommendation
- proxy-cost scenario analysis
- cross-period and perturbation stability

Avoid:

- data is more or less useful
- more data is always better
- sampling frequency is the only contribution
- the model is better because the RMSE is smaller
- the method proves the best interval
- the recommendation is universally robust

### Recommended core claim

Preferred wording:

> This study addresses data-investment decision-making in photovoltaic power forecasting. Sampling-interval regulation is used as a controlled protocol to vary the data-retention ratio, and the resulting accuracy-cost response is used to identify statistically acceptable and resource-efficient candidate intervals.

Avoid:

> This paper studies whether larger sampling intervals are better.

Reason:

The manuscript is not merely about sampling frequency. Sampling interval is the experimental protocol used to reduce data investment.

---

## 2. Photovoltaic Forecasting Terms

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 光伏功率预测 | photovoltaic power forecasting | PV power forecasting | solar prediction, PV prediction only |
| 短时预测 | short-term forecasting | short-horizon forecasting | short prediction |
| 预测时距 | forecast horizon | forecasting horizon | prediction distance |
| 1小时超前预测 | 1 h-ahead forecasting | one-hour-ahead forecasting | 1 hour prediction |
| 有功功率 | active power | PV active power output | effective power |
| 光伏出力 | PV power output | photovoltaic generation output | PV output value |
| 辐照波动 | irradiance variability | solar irradiance fluctuation | radiation randomness |
| 云遮挡 | cloud-induced variability | cloud-cover variation | cloud blocking |
| 功率爬坡 | power ramp events | ramping events | power mutation |
| 昼夜周期 | diurnal cycle | daily cycle | day-night law |
| 有效发电样本 | daylight generation samples | active-generation samples | daytime data only |
| 夜间近零样本 | near-zero nighttime samples | non-generating nighttime samples | invalid night data |

### Example sentence

Preferred:

> Photovoltaic power output is affected by irradiance variability, cloud-induced fluctuations, temperature, and local meteorological conditions, leading to strong intermittency and ramping behavior.

Avoid:

> PV output changes randomly because of weather.

---

## 3. Data Investment and Sampling Terms

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 数据投入 | data investment | data-processing investment | data input amount |
| 数据量 | data volume | data size | amount of data |
| 数据保留比例 | data-retention ratio | retained data ratio | data keeping rate |
| 采样间隔 | sampling interval | recording interval | sampling step, sample gap |
| 采样频率 | sampling frequency | recording frequency | frequency of data |
| 原始分辨率 | original temporal resolution | native temporal resolution | raw frequency |
| 增大采样间隔 | increasing the sampling interval | coarsening the temporal resolution | increasing sampling step |
| 降低数据投入 | reducing data investment | reducing data retention | reducing data input |
| 高数据保留比例 | high data-retention ratio | dense data-retention setting | more data |
| 低数据保留比例 | low data-retention ratio | sparse data-retention setting | less data |
| 数据治理成本 | data-governance cost | data acquisition, storage, and cleaning cost | data management fee |
| 训练数据投入 | training-data investment | historical-data processing effort | training data cost |

### Key rule

When discussing the current manuscript, write:

> Sampling-interval regulation is used as the experimental protocol for reducing the data-retention ratio.

Do not write:

> Sampling interval is the only form of data investment.

### Example sentence

Preferred:

> In this study, increasing the sampling interval reduces the number of retained observations per unit time and is therefore used as a controlled protocol for reducing data investment.

Avoid:

> Increasing the sampling interval means using less data, so it is the same as reducing the training set.

---

## 4. Forecast Accuracy Metrics

| Symbol or metric | Preferred expression | Notes |
|---|---|---|
| RMSE | root mean square error | Use for primary accuracy comparison |
| MAE | mean absolute error | Use as supplementary absolute error metric |
| MAPE | mean absolute percentage error | Apply carefully; avoid nighttime near-zero samples |
| R² | coefficient of determination | Use "R²" or "coefficient of determination" |
| 95% CI | 95% confidence interval | Use to describe repeated-run uncertainty |
| standard deviation | standard deviation across repeated runs | Avoid calling it uncertainty alone without context |
| repeated runs | repeated training runs | Prefer over "multiple experiments" |
| random seed | random seed | Mention when discussing repeated-training variability |

### Preferred expression

> RMSE is used as the primary accuracy metric, while MAE, MAPE, and R² are reported as supplementary indicators.

### Avoid

> RMSE is the final standard of the model.

---

## 5. Repeated Training and Statistical Reliability

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 重复训练 | repeated training runs | repeated model runs | repeated experiments only |
| 随机初始化 | random initialization | stochastic initialization | random start |
| 训练随机性 | repeated-training variability | training stochasticity | random error only |
| 显著性检验 | significance testing | statistical significance test | significant analysis |
| 成对 t 检验 | paired t-test | paired Student's t-test | t detection |
| Wilcoxon 符号秩检验 | Wilcoxon signed-rank test | non-parametric paired test | Wilcoxon rank test only |
| 多重比较校正 | multiple-comparison correction | false-discovery-rate correction | multiple test correction |
| BH 校正 | Benjamini-Hochberg correction | BH false-discovery-rate correction | BH method only |

### Correct role of significance testing

Preferred:

> Significance testing is used as a statistical reliability check for response-curve differences. It does not constitute the decision rule for the recommended interval.

Avoid:

> The equivalent-accuracy set is constructed using the RMSE threshold, confidence intervals, and significance testing.

Correct:

> The equivalent-accuracy set is constructed using the RMSE degradation threshold and the 95% confidence-interval overlap criterion. Significance testing is reported as a supplementary reliability check.

### Non-significant result

Preferred:

> A non-significant difference indicates that the mean-RMSE gap should not be over-interpreted as sufficient evidence for selecting a higher data-investment configuration.

Avoid:

> The difference is random and has no value.

---

## 6. Equivalent-Accuracy Set

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 等价精度集 | equivalent-accuracy set | accuracy-equivalent candidate set | same-accuracy set |
| 精度可接受配置 | accuracy-acceptable configuration | statistically acceptable configuration | qualified sample |
| 相对 RMSE 劣化阈值 | relative RMSE degradation threshold | RMSE tolerance threshold | error worsening threshold |
| 置信区间重叠 | confidence-interval overlap | overlap of 95% confidence intervals | CI intersection only |
| 工程容忍度 | engineering tolerance | deployment tolerance | subjective tolerance |
| 候选配置 | candidate configuration | candidate sampling configuration | candidate point |

### Required definition

Use:

> The equivalent-accuracy set does not imply identical prediction errors in a strict statistical sense. It denotes configurations whose accuracy degradation remains within the predefined RMSE tolerance and repeated-run uncertainty range.

Avoid:

> The equivalent-accuracy set proves that these configurations have the same accuracy.

### Recommended formula explanation

Use this order:

1. Define the accuracy-optimal configuration.
2. Define relative RMSE degradation.
3. Define the 95% confidence interval.
4. Define the equivalent-accuracy set using the degradation threshold and confidence-interval overlap.
5. State that significance testing is supplementary.

### Example sentence

Preferred:

> The equivalent-accuracy set provides the candidate space for cost-effectiveness ranking: configurations outside this set are not recommended even if they have lower resource consumption.

Avoid:

> The equivalent-accuracy set directly gives the final optimal interval.

---

## 7. PCEI and Proxy-Cost Terms

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 性价比 | cost-effectiveness | resource efficiency | price-performance ratio |
| 预测性价比综合指数 | predictive cost-effectiveness index | PCEI | cost performance index |
| 代理成本 | proxy cost | cost proxy | fake cost |
| 代理成本场景 | proxy-cost scenario | cost-weight scenario | simulated cost case |
| 成本权重 | cost weight | scenario weight | cost parameter only |
| 数据治理权重 | data-governance weight | data-retention cost weight | data weight only |
| 训练计算权重 | training-computation weight | retraining-cost weight | compute fee |
| 误差权重 | error weight | accuracy-loss weight | precision weight |
| 推荐配置 | recommended configuration | scenario-specific recommended configuration | final best point |
| 推荐区间 | recommendation interval | candidate data-investment interval | optimal interval only |
| 高性价比区间 | high cost-effectiveness candidate interval | resource-efficient candidate interval | best cost interval |

### Distinguish PCEI from real economic value

Preferred:

> PCEI is a proxy-cost indicator and should not be interpreted as a direct monetary return or market profit.

Avoid:

> PCEI calculates the real optimal cost.

### Point-to-interval definition

If PCEI produces a point under each scenario, use:

> For each cost scenario, PCEI first yields a scenario-specific recommended configuration. The recommendation interval is defined as the range covered by these scenario-level recommendation points.

Avoid:

> PCEI directly outputs an interval.

### Example sentence

Preferred:

> The PCEI analysis converts the equivalent-accuracy candidate set into deployment-oriented recommendations under different proxy-cost scenarios.

Avoid:

> PCEI proves the best cost.

---

## 8. Cost and Electricity-Market Context

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 偏差结算 | imbalance settlement | imbalance accounting | deviation settlement |
| 偏差成本 | imbalance cost | forecast-error cost | error fee |
| 市场投标 | market bidding | day-ahead bidding | market quote |
| 日前市场 | day-ahead market | day-ahead electricity market | tomorrow market |
| 实时运行 | real-time operation | real-time balancing | current-time running |
| 调度备用 | reserve allocation | reserve scheduling | backup arrangement |
| 备用容量 | reserve capacity | balancing reserve | spare capacity |
| 偏差惩罚 | imbalance penalty | penalty for forecast deviation | deviation punishment |
| 运行经济性 | operational economy | operational cost-effectiveness | economic operation |
| 系统运营商 | system operator | grid operator | power company only |
| 部署决策者 | deployment decision-maker | system operator, practitioner | engineer only |

### Preferred framing

> Forecasting errors can affect dispatch decisions, reserve allocation, imbalance settlement, and market participation. Therefore, accuracy improvements should be interpreted in relation to their operational value and implementation cost.

Avoid:

> Forecasting accuracy is money.

### Use "value" carefully

Preferred:

- forecast value
- economic value of forecasts
- operational value of improved forecasts

Avoid:

- money value of the model

---

## 9. Robustness, Stability, and Generalization

| Chinese concept | Preferred English term | Acceptable alternatives | Avoid |
|---|---|---|---|
| 稳健性 | robustness | stability | universal robustness |
| 跨时期验证 | cross-period validation | temporal out-of-sample validation | time proof |
| 外部有效性 | external validity | temporal external validity | outside validity |
| 扰动稳定性 | perturbation stability | stability under noise perturbation | noise robustness only |
| 采样策略敏感性 | sampling-strategy sensitivity | resampling-strategy sensitivity | sampling method effect |
| 边界 | scope boundary | validity boundary | limitation only |
| 候选区间 | candidate interval | priority candidate interval | final universal interval |

### Strong claim control

Use:

> stable under the tested temporal and perturbation conditions

Avoid:

> robust in all cases

Use:

> priority candidate interval under the present dataset and experimental protocol

Avoid:

> universally optimal interval

### Example sentence

Preferred:

> The cross-period and perturbation analyses indicate that the proposed candidate interval is not an artifact of a single year, model family, or resampling strategy. However, spatial generalization remains to be verified using additional PV stations.

Avoid:

> The interval is robust and generally applicable to all PV systems.

---

## 10. Results Interpretation Phrases

### To introduce a result

Preferred:

- The results show that...
- The results indicate that...
- The observed pattern suggests that...
- The comparison provides evidence that...
- The response curve reveals that...

Avoid:

- We can see that...
- It is obvious that...
- This fully proves that...
- The effect is very good.

### To interpret non-monotonicity

Preferred:

> The response curve is not strictly monotonic, indicating that higher data retention does not necessarily provide proportional accuracy improvement.

Avoid:

> The curve is messy.

### To interpret cost-effectiveness

Preferred:

> This configuration remains within the acceptable accuracy region while substantially reducing the data-retention ratio and training time.

Avoid:

> This point is cheap and good.

### To interpret model differences

Preferred:

> The model-dependent sampling preference suggests that data-retention decisions should be evaluated jointly with the forecasting architecture.

Avoid:

> Different models like different intervals.

---

## 11. Section Title Conventions

### Preferred titles

- Data-Investment Response under Sampling-Interval Regulation
- Equivalent-Accuracy Set and Resource-Efficiency Recommendation
- PCEI-Based Recommendation under Proxy-Cost Scenarios
- Statistical Reliability Check: Marginal Gain and Significance Testing
- Cross-Period Validation and Stability Boundary
- Discussion: Mechanistic Interpretation and Deployment Implications

### Avoid titles

- The result is good
- Robustness proof
- Best cost recommendation
- Significance proves the result
- Optional experiment
- Temporary section

Never leave author notes such as:

- "optional section"
- "if reviewers ask"
- "temporary"
- "not main line"

in a submission manuscript.

---

## 12. Figure and Table Caption Language

Figure captions and figure-related paragraphs should work together. The caption identifies the figure; the surrounding text explains why the figure matters. For major figures, use the four-step pattern: what is shown, what pattern matters, why it supports the research question, and what boundary applies.

### Framework figure

Preferred:

> Overall framework for data-investment decision-making in photovoltaic power forecasting under sampling-interval regulation.

### Response curve figure

Preferred:

> RMSE response curves under different data-retention ratios across forecasting models.

### Accuracy-cost trade-off figure

Preferred:

> Accuracy-resource trade-off between RMSE and training time across sampling configurations.

### Equivalent-accuracy figure

Preferred:

> Identification of equivalent-accuracy configurations under the 2% RMSE degradation threshold and 95% confidence-interval overlap criterion.

### PCEI heatmap

Preferred:

> Recommended sampling intervals under different proxy-cost scenarios.

### Robustness figure

Preferred:

> Stability of sampling-interval responses under cross-period, perturbation, and resampling-strategy checks.


### Figure-text interpretation phrases

Preferred:

- Fig. X illustrates the overall workflow used to connect data-retention control with resource-efficiency recommendation.
- The key pattern is that the recommended configurations are concentrated in a limited interval rather than scattered across all sampling settings.
- This pattern supports the central argument that data-retention selection should be evaluated as an accuracy-cost decision.
- This interpretation is limited to the tested dataset, model family, and proxy-cost settings.

Avoid:

- Fig. X shows the result.
- The figure proves the method is robust.
- The figure clearly shows the best interval.


---


## 13. Highlights and Submission Phrases

### Preferred Highlight Style

Use concise, result-oriented statements such as:

- Data-retention selection is formulated as a resource-efficiency decision problem.
- Equivalent-accuracy sets identify configurations with acceptable RMSE degradation.
- PCEI ranks accuracy-acceptable configurations under proxy-cost scenarios.
- A candidate interval balances forecasting accuracy and data investment under the tested protocol.
- Cross-period and perturbation checks define the stability boundary of the recommendation.

Avoid topic-only or overclaimed Highlights such as:

- PV forecasting is studied.
- Sampling intervals are compared.
- The best sampling interval is found.
- The recommendation is universally robust.

### Preferred submission wording

Use:

- high cost-effectiveness candidate interval
- proxy-cost-aware recommendation
- deployment-oriented decision support
- tested stability boundary
- station-specific validation before deployment

Avoid:

- universal optimal interval
- real economic optimum
- guaranteed robustness
- direct market profit

---

## 14. Recommended Claim Templates

### Abstract contribution sentence

> This study does not propose a new forecasting architecture; instead, it reformulates data-retention selection in photovoltaic forecasting as an interval-based resource-efficiency decision problem.

### Introduction gap sentence

> Existing studies have substantially improved forecasting accuracy through model and input innovations, but the response of forecasting performance to different data-investment levels remains insufficiently characterized.

### Method contribution sentence

> The proposed framework first identifies accuracy-acceptable configurations and then ranks them using proxy-cost-aware resource-efficiency metrics.

### Result summary sentence

> The main results show that the highest data-retention ratio is not consistently associated with the lowest RMSE, and several lower-data configurations remain within the equivalent-accuracy region while reducing training time.

### Discussion boundary sentence

> The proposed interpretation is limited to the fixed resampling protocol used in this study and should not be generalized to all possible forms of data reduction.

### Conclusion sentence

> Photovoltaic forecasting systems should not automatically default to the highest recording frequency; instead, they should identify statistically acceptable and resource-efficient data-retention configurations under the target deployment setting.

---

## 15. Phrases to Avoid or Replace

| Avoid | Replace with |
|---|---|
| more data is always better | additional data investment is not always justified |
| the best sampling interval | the preferred sampling interval under the tested setting |
| proves robustness | provides evidence of stability under tested conditions |
| significant means useful | statistical significance does not directly imply deployment value |
| non-significant means random | non-significant differences should not be over-interpreted |
| cost is low | proxy resource cost is lower |
| real cost | monetary cost or market-based cost |
| can save money | can reduce proxy resource consumption |
| this model performs best | this model achieves the lowest RMSE under the tested configuration |
| this method solves the problem | this framework provides a decision-support procedure |

---

## 16. Consistency Rules for This Manuscript Type

### Rule 1: Equivalent-accuracy set construction

Correct:

> RMSE degradation threshold + 95% confidence-interval overlap

Incorrect:

> RMSE degradation threshold + 95% confidence interval + significance testing

### Rule 2: Significance testing

Correct:

> supplementary statistical reliability check

Incorrect:

> recommendation rule

### Rule 3: PCEI

Correct:

> proxy-cost-aware ranking within or alongside accuracy-acceptable configurations

Incorrect:

> real monetary profit model

### Rule 4: Recommendation interval

Correct:

> range covered by scenario-level recommendation points

Incorrect:

> directly optimized continuous interval

### Rule 5: Robustness

Correct:

> cross-period and perturbation stability under the tested protocol

Incorrect:

> universal robustness across PV plants

---

## 17. Editing Checklist

Before finalizing a polished section, check whether:

- the term "data investment" is consistently linked to sampling-interval regulation;
- the equivalent-accuracy set is not confused with significance testing;
- PCEI is not described as a real economic-profit model;
- recommendation intervals are defined from scenario-level recommendation points;
- "robust" claims are bounded by the tested data and protocol;
- all model-specific claims are supported by tables or figures;
- no author notes remain in section titles;
- no causal mechanism is overstated;
- power-market terms are used only where relevant;
- the section reads like an energy-systems paper, not a generic AI-generated report.

---

## 18. Bilingual Chinese-English Writing Terms

Use this section when the manuscript is developed first in Chinese and then converted into English.

### Chinese manuscript positioning

Preferred Chinese description:

> 导师可读型中文学术稿

Meaning:

A Chinese manuscript that reads naturally to a supervisor, has clear logic, and maintains stable terminology for later English conversion.

Avoid describing the Chinese draft as:

> 翻译友好型中文稿

Reason:

This can lead to unnatural Chinese that follows English word order.

### Common Chinese expressions and preferred English conversion

| Chinese expression | Better Chinese revision | English journal-style conversion |
|---|---|---|
| 可以看出 | 结果表明 / 该结果说明 | The results show / This pattern indicates |
| 具有重要意义 | 对……具有应用价值 / 为……提供依据 | is relevant to / provides evidence for |
| 证明了鲁棒性 | 为稳定性提供支持 | provides supporting evidence for stability |
| 数据不用太多 | 较高数据投入并不必然带来相匹配的精度收益 | higher data investment is not necessarily justified by proportional accuracy improvement |
| 效果比较好 | 在……指标上表现更优 / 保持在可接受范围内 | achieves lower RMSE / remains within the acceptable accuracy region |

### Bilingual style rule

Chinese should be natural and supervisor-readable. English should be non-literal and journal-oriented. Both versions must preserve the same scientific meaning, numerical values, equations, and claim boundaries.
