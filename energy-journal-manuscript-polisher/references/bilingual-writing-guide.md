# Bilingual Writing Guide for Energy Journal Manuscripts

## Purpose

This guide supports a two-stage manuscript workflow for energy-journal papers, especially photovoltaic power forecasting manuscripts involving data-investment decisions, sampling-interval regulation, equivalent-accuracy sets, PCEI, and proxy-cost recommendation.

The workflow is:

1. Develop a supervisor-readable Chinese academic draft.
2. Convert the approved Chinese draft into an English journal-style manuscript draft.

The Chinese draft should be natural and readable for a supervisor. It should not be written as awkward English-structured Chinese. At the same time, its logic, terminology, and claim boundaries should be stable enough to support later English conversion.

Use this file together with:

- `references/terminology.md`
- `references/review-checklist.md`
- `references/examples.md`
- `references/literature-taxonomy.md`

---

## 1. Correct Positioning of the Writing Workflow

The skill should not treat Chinese writing as a direct pre-translation exercise. The Chinese manuscript has its own reader: the supervisor, committee members, and Chinese-speaking collaborators.

The correct positioning is:

> Supervisor-readable Chinese academic manuscript first; English journal-style conversion second.

The Chinese draft should be:

- logically smooth;
- natural in Chinese academic style;
- precise in terminology;
- free from colloquial expressions;
- free from empty rhetorical claims;
- structured enough for later English conversion;
- not written in mechanical English word order.

The English draft should be:

- non-literal;
- journal-oriented;
- concise and evidence-linked;
- aligned with energy-journal conventions;
- explicit about claim boundaries;
- consistent in terminology and figure/table references.

---

## 2. Stage 1: Supervisor-Readable Chinese Academic Draft

### 2.1 Goal

The goal is to produce a Chinese draft that a supervisor can read smoothly and evaluate scientifically. The draft should make the research logic explicit before the English translation stage begins.

A good Chinese draft should answer:

1. What problem is being addressed?
2. Why is the problem important in PV forecasting or energy operation?
3. What method or framework is used?
4. What result is observed?
5. What does the result imply?
6. What is the boundary of the claim?

### 2.2 Preferred Chinese paragraph structure

Use this structure when possible:

> 段落功能句 → 方法或结果 → 解释含义 → 边界说明

Example:

> 本节进一步分析 PCEI 在不同代理成本场景下的推荐结果。结果显示，推荐配置主要集中在 15–40 min 区间，而 5 min 配置仅在强误差敏感场景下保留。该结果说明，在多数资源约束场景中，最高数据保留比例并不是默认最优选择。需要说明的是，该推荐区间仍受本文数据源、模型族和代理成本设定限制，不能直接解释为所有光伏电站的普适采样规则。

Why this works:

- It is natural Chinese.
- It is clear for a supervisor.
- It contains a result, interpretation, and boundary.
- It can be converted into English without major logic reconstruction.

### 2.3 Avoid translation-like Chinese

Avoid Chinese that mechanically follows English syntax.

Poor version:

> 本研究解决光伏功率预测中的数据投入决策问题，并且采样间隔调节被用于作为控制协议以变化数据保留比例。

Better version:

> 本文关注光伏功率预测中的数据投入决策问题。为刻画数据投入变化对预测精度和资源消耗的影响，本文将采样间隔调节作为降低数据保留比例的实验手段。

Reason:

The better version is natural Chinese and still easy to convert into English.

### 2.4 Avoid colloquial or empty Chinese expressions

Avoid:

- 可以看出
- 显然
- 众所周知
- 效果很好
- 具有重要意义
- 本文完美解决了
- 充分证明了
- 数据越多越好
- 值不值得
- 很省钱

Prefer:

- 结果表明
- 该结果说明
- 这一现象表明
- 在本文实验条件下
- 该发现为……提供了依据
- 该结果支持……判断
- 该结论仍受……限制
- 较高数据投入并不必然带来相匹配的精度收益

### 2.5 Chinese terminology consistency

Use stable Chinese terms throughout the manuscript:

| Concept | Preferred Chinese term | Avoid inconsistent alternatives |
|---|---|---|
| data investment | 数据投入 | 数据量投入、数据使用量、输入量, unless explicitly defined |
| data-retention ratio | 数据保留比例 | 数据保存率、数据保留率, unless standardized |
| sampling interval regulation | 采样间隔调节 | 采样频率变化, unless discussing frequency explicitly |
| equivalent-accuracy set | 等价精度集 | 相同精度集、精度等同集合 |
| significance testing | 显著性检验 | 显著分析、差异检验, unless defined |
| proxy cost | 代理成本 | 虚拟成本、模拟成本 |
| PCEI | 预测性价比综合指数（PCEI） | 性价比指标, unless after definition |
| candidate interval | 候选区间 | 最优区间, unless truly optimized |
| stability boundary | 稳定性边界 | 鲁棒性证明 |

### 2.6 Chinese claim-boundary rules

Do not overstate results in Chinese.

Avoid:

> 本文证明了 15–40 min 是最优采样区间。

Prefer:

> 在本文数据源、模型族和代理成本设定下，15–40 min 可作为高性价比数据投入候选区间。

Avoid:

> 本文方法具有很强的鲁棒性。

Prefer:

> 跨时期和扰动实验表明，该候选区间在本文实验条件下具有一定稳定性。

---

## 3. Stage 2: English Journal-Style Conversion

### 3.1 Translation principle

Do not translate the Chinese draft word by word. Convert it into an English journal-style paragraph.

The English conversion should preserve:

- scientific meaning;
- numerical values;
- equations;
- model names;
- table and figure references;
- contribution structure;
- stated limitations.

The English conversion should improve:

- topic sentence clarity;
- sentence concision;
- terminology consistency;
- claim-evidence-boundary structure;
- journal-style phrasing.

### 3.2 English paragraph structure

Use this structure when converting Chinese to English:

> Topic sentence → Evidence or method → Interpretation → Boundary or implication

Example:

Chinese:

> 本节进一步分析 PCEI 在不同代理成本场景下的推荐结果。结果显示，推荐配置主要集中在 15–40 min 区间，而 5 min 配置仅在强误差敏感场景下保留。该结果说明，在多数资源约束场景中，最高数据保留比例并不是默认最优选择。需要说明的是，该推荐区间仍受本文数据源、模型族和代理成本设定限制，不能直接解释为所有光伏电站的普适采样规则。

English:

> This subsection further examines the PCEI-based recommendations under different proxy-cost scenarios. The recommended configurations are concentrated in the 15–40 min interval, while the 5 min configuration is retained only under strongly error-sensitive settings. This pattern indicates that the highest data-retention ratio should not be treated as the default choice in most resource-constrained deployment scenarios. The recommendation remains bounded by the dataset, model family, and proxy-cost settings considered in this study, and should not be interpreted as a universal sampling rule for all PV stations.

### 3.3 Verb selection for English claims

Translate Chinese verbs carefully.

| Chinese expression | Preferred English choice | Strength |
|---|---|---|
| 表明 | show / indicate | medium |
| 说明 | indicate / suggest | medium to cautious |
| 证明 | demonstrate / provide evidence that | strong, use carefully |
| 验证 | validate / evaluate / provide supporting evidence | context-dependent |
| 可以看出 | the results show / the observed pattern indicates | replace, do not translate literally |
| 具有重要意义 | is relevant to / has implications for | avoid empty phrasing |

Avoid using `prove` unless the manuscript contains formal proof.

### 3.4 Common Chinese-to-English transformations

Chinese:

> 数据越多并不一定越好。

English:

> Higher data retention is not necessarily justified by proportional accuracy improvement.

Chinese:

> 本文研究数据投入是否值得。

English:

> This study examines whether additional data investment is justified by the resulting forecasting improvement.

Chinese:

> 可以看出，PCEI 推荐区间比较稳定。

English:

> The PCEI-based recommendation remains concentrated within a limited interval under the tested proxy-cost scenarios.

Chinese:

> 该方法具有较强鲁棒性。

English:

> The candidate interval shows stability under the tested cross-period and perturbation conditions.

---

## 4. Section-Specific Bilingual Rules

### 4.1 Abstract

Chinese draft should be concise but readable for the supervisor. It should state:

1. 研究问题;
2. 方法框架;
3. 主要结果;
4. 贡献边界.

English conversion should follow:

1. problem and motivation;
2. framework and method;
3. key empirical results;
4. implication and boundary.

Avoid literal translation of Chinese abstract phrases such as:

- 本文以……为研究对象
- 本文具有重要理论和现实意义
- 结果证明了本文方法的有效性

Use journal-style English instead:

- This study addresses...
- The results indicate...
- The proposed framework provides...

### 4.2 Introduction

Chinese draft should help the supervisor see the logic chain:

> 精度有价值 → 数据投入有成本 → 更多数据不一定值得 → 需要数据投入决策框架

English conversion should make the same chain more compact:

> Forecast value → data cost → uncertain marginal gain → decision gap

### 4.3 Methods

Chinese draft should prioritize clarity of definitions.

English conversion should prioritize precision and symbol consistency.

For formulas, do not paraphrase too loosely. Preserve the same symbols and definitions.

### 4.4 Results

Chinese draft should explain what the result means for the research question.

English conversion should explicitly connect each figure or table to the claim.

Use:

> Fig. X shows... The key pattern is... This supports... This interpretation is bounded by...

### 4.5 Discussion

Chinese draft may include more explanatory transitions for supervisor readability.

English conversion should be more concise and cautious.

Avoid turning plausible explanations into causal proof.

### 4.6 Conclusion

Chinese conclusion should summarize the problem, finding, method, recommendation, and limitation.

English conclusion should avoid new evidence and should state the final contribution with boundary language.

---

## 5. Recommended Output Format for Bilingual Tasks

When the user asks for Chinese drafting or Chinese-to-English conversion, use this output format when appropriate.

### 1. 中文学术稿

Provide a supervisor-readable Chinese academic version.

### 2. 段落功能说明

Explain the paragraph's role in the manuscript logic.

### 3. 翻译风险提示

Identify Chinese expressions that should not be translated literally.

### 4. English journal-style draft

Provide a non-literal English journal-style draft if requested.

### 5. 术语映射

List key Chinese-English terminology mappings.

### 6. 主张边界调整

Explain whether any claim was softened or bounded.

---

## 6. Examples

### Example 1: Chinese polishing before English conversion

Raw Chinese:

> 可以看出，15–40 min 的采样间隔效果比较好，说明数据不用太多。

Supervisor-readable Chinese:

> 结果表明，在本文数据源、模型族和代理成本设定下，推荐配置主要集中在 15–40 min 区间。该区间对应较低的数据保留比例，同时仍处于等价精度集范围内，说明较高数据投入并不必然带来与资源消耗相匹配的精度收益。

English journal-style draft:

> The results show that, under the considered dataset, model family, and proxy-cost settings, the recommended configurations are concentrated in the 15–40 min interval. This interval corresponds to a lower data-retention ratio while remaining within the equivalent-accuracy region, indicating that higher data investment is not necessarily justified by proportional accuracy improvement.

### Example 2: Method definition

Raw Chinese:

> 显著性检验用来证明误差是不是随机的。

Supervisor-readable Chinese:

> 显著性检验用于辅助判断不同采样配置之间的 RMSE 差异是否稳定，而不是直接作为推荐区间的判定规则。

English journal-style draft:

> Significance testing is used as a supplementary reliability check to examine whether RMSE differences across sampling configurations are stable. It does not constitute the decision rule for the recommended interval.

### Example 3: Boundary control

Raw Chinese:

> 本文证明了推荐区间具有鲁棒性。

Supervisor-readable Chinese:

> 跨时期和扰动实验为推荐区间的稳定性提供了支持，但该结论仍限于本文数据源、模型族和实验协议。

English journal-style draft:

> The cross-period and perturbation experiments provide supporting evidence for the stability of the recommended interval. However, this conclusion remains bounded by the dataset, model family, and experimental protocol used in this study.

---

## 7. Final Checklist

Before finalizing a Chinese draft, check:

- Does the paragraph read naturally in Chinese?
- Would a supervisor understand the paragraph without English context?
- Is each paragraph's function clear?
- Are the key terms consistent?
- Are conclusions bounded by the experiment?
- Are there colloquial or empty expressions?
- Is the paragraph structured enough for later English conversion?

Before finalizing an English conversion, check:

- Is the translation non-literal?
- Does the English paragraph have a clear topic sentence?
- Are Chinese long sentences split appropriately?
- Are claim verbs chosen carefully?
- Are overstrong claims softened?
- Are data, symbols, models, and figure/table references preserved?
- Does the paragraph sound like an energy-journal manuscript rather than translated Chinese?
