# Literature Taxonomy for Photovoltaic Forecasting Manuscripts

## Purpose

This file supports literature-review writing and gap construction for manuscripts on photovoltaic (PV) power forecasting, especially papers involving data-investment decisions, sampling-interval regulation, data-retention ratio, equivalent-accuracy sets, and proxy-cost-aware recommendation.

Use this file together with:

- `SKILL.md`
- `references/terminology.md`
- `references/review-checklist.md`
- `references/examples.md`

The goal is to help the assistant write literature reviews in the style of high-quality energy journals such as Applied Energy, Energy, Energy Conversion and Management, Renewable Energy, Solar Energy, and Renewable and Sustainable Energy Reviews.

Do not use this taxonomy as a source of factual claims without user-provided references or web-verified references. Use it as an organizing logic for grouping literature, identifying gaps, and avoiding unstructured model lists.

---

## 1. Core Rule for Related Work

A strong literature review should not list papers one by one. It should group prior studies by the function they serve in the research problem.

For this manuscript type, the literature review should answer four questions:

1. What has prior PV forecasting research already solved?
2. Which stream of work is closest to the present manuscript?
3. What remains insufficiently addressed?
4. Why does the current manuscript need a data-investment and resource-efficiency framing rather than another model-comparison framing?

Preferred structure:

> Prior studies have improved PV forecasting through model innovation, input expansion, uncertainty modeling, and cost-sensitive operation. However, most of these studies optimize prediction accuracy or uncertainty quality, while the response of forecasting performance to different data-investment levels remains insufficiently characterized.

Avoid:

> Many scholars have proposed CNN, LSTM, GRU, Transformer, and hybrid models.

---

## 2. Recommended Literature Review Structure for This Manuscript

Use the following structure when the manuscript is about data-retention selection or sampling-interval regulation in PV forecasting.

### Stream 1: Forecasting model evolution

Function:

Explain that prior studies have improved forecasting accuracy by developing stronger model architectures.

Typical subgroups:

- statistical models
- machine learning models
- deep learning models
- hybrid deep learning models
- attention and transformer-based models
- decomposition-assisted models
- graph-based and spatiotemporal models

Connection to this manuscript:

These studies improve model expressiveness, but they usually treat the data configuration as fixed or as a secondary setting.

Gap statement:

> Model-oriented studies have substantially improved forecasting accuracy, but they generally do not examine whether the additional data retained for training and model updating is justified by the marginal accuracy gain.

### Stream 2: Input information expansion

Function:

Explain that prior studies improve forecasts by adding more information sources.

Typical input sources:

- historical PV power records
- ground meteorological measurements
- numerical weather prediction (NWP)
- satellite images
- sky images
- cloud motion vectors
- neighboring-site information
- calendar and solar-position variables

Connection to this manuscript:

These studies answer "what information should be added?" but usually not "how much temporal information should be retained?"

Gap statement:

> Input-oriented studies expand the information available to the forecasting model, but the temporal granularity and data-retention level of this information are rarely treated as decision variables.

### Stream 3: High-resolution and long-sequence forecasting

Function:

Explain that recent research studies high temporal resolution, long forecast horizons, and long input sequences.

Typical methods:

- long short-term memory networks
- temporal convolutional networks
- self-attention and transformer models
- patch-based long-sequence modeling
- frequency-domain modeling
- decomposition into trend and residual components
- multi-scale temporal feature extraction

Connection to this manuscript:

These studies are close to sampling-resolution questions, but they often focus on architecture design rather than the cost-effectiveness of data retention.

Gap statement:

> High-resolution forecasting studies show the importance of temporal granularity, but they generally aim to improve accuracy at fine resolutions rather than determine when dense temporal records are no longer resource-efficient.

### Stream 4: Data quality, missing data, and preprocessing

Function:

Explain that real PV data are incomplete, noisy, and non-stationary, requiring preprocessing and quality control.

Typical topics:

- missing timestamps
- outlier detection
- data reconstruction
- data cleaning
- anomaly filtering
- weather-type clustering
- bias correction
- statistical post-processing
- non-stationarity handling

Connection to this manuscript:

These studies demonstrate that data are not cost-free or neutral; preprocessing and governance introduce practical deployment burden.

Gap statement:

> Data-quality studies recognize that forecasting performance depends on data integrity, but they rarely quantify whether retaining denser data records produces sufficient improvement relative to the additional governance and processing burden.

### Stream 5: Probabilistic and uncertainty-aware forecasting

Function:

Explain that uncertainty-aware forecasts provide prediction intervals or distributions rather than only point forecasts.

Typical methods:

- quantile regression
- Bayesian neural networks
- ensemble learning
- probabilistic deep learning
- prediction interval construction
- reliability and sharpness evaluation

Connection to this manuscript:

These studies handle uncertainty in forecast outputs, while the present manuscript handles uncertainty in repeated training and data-retention decisions.

Gap statement:

> Probabilistic forecasting studies quantify output uncertainty, but they do not directly address the decision of selecting a data-retention configuration under resource constraints.

### Stream 6: Transfer learning, domain adaptation, and generalization

Function:

Explain that some studies improve cross-site, cross-season, or data-scarce forecasting.

Typical topics:

- transfer learning
- domain adaptation
- meta-learning
- cross-station forecasting
- newly-built PV plants
- limited historical data
- cross-climate generalization

Connection to this manuscript:

These studies are relevant to deployment scalability, but they usually aim to improve model portability, not to decide how much data should be retained.

Gap statement:

> Generalization-oriented studies improve model transferability under data scarcity, but they do not provide an interval-based rule for reducing data investment while preserving acceptable accuracy.

### Stream 7: Cost-sensitive forecasting and market-oriented operation

Function:

Explain that forecasting errors have operational and economic consequences.

Typical contexts:

- dispatch scheduling
- reserve allocation
- imbalance settlement
- market bidding
- building energy management
- storage operation
- demand response
- grid integration

Connection to this manuscript:

This is the closest stream for motivating why accuracy should be evaluated together with cost.

Gap statement:

> Market- and operation-oriented studies link forecasting errors to economic outcomes, but the cost of obtaining and processing the forecasting data itself is usually not modeled as part of the forecasting decision.

---

## 3. Standard Taxonomy of PV Forecasting Methods

### 3.1 Physical models

Definition:

Physical models use system parameters, irradiance models, solar geometry, and PV conversion equations to estimate PV output.

Typical strengths:

- interpretable
- useful when physical system information is reliable
- suitable for physics-based reasoning

Typical limitations:

- require detailed system parameters
- sensitive to installation information and environmental assumptions
- may be computationally demanding when high fidelity is required

Use in literature review:

> Physical models are interpretable and can represent PV conversion mechanisms, but their practical use is often limited by the need for detailed system parameters and environmental information.

### 3.2 Statistical models

Definition:

Statistical models use historical time-series relationships and linear or semi-linear assumptions.

Typical methods:

- autoregressive model
- ARMA
- ARIMA
- SARIMA
- regression models
- grey models
- Markov models

Typical strengths:

- simple
- interpretable
- efficient
- suitable as baselines

Typical limitations:

- limited nonlinear modeling capability
- weaker performance under unstable or cloudy weather
- rely on stationarity assumptions in some cases

Use in literature review:

> Statistical models provide efficient and interpretable baselines, but their linear assumptions restrict their ability to model nonlinear weather-driven PV fluctuations.

### 3.3 Machine learning models

Definition:

Machine learning models learn nonlinear relationships from historical power and meteorological data.

Typical methods:

- support vector regression
- random forest
- gradient boosting
- XGBoost
- artificial neural networks
- decision trees

Typical strengths:

- stronger nonlinear fitting than statistical methods
- useful for tabular meteorological features
- relatively easier to train than deep networks

Typical limitations:

- feature engineering remains important
- temporal dependencies may not be fully captured
- performance can depend strongly on hyperparameter tuning

Use in literature review:

> Machine learning models improve nonlinear fitting capability but often require careful feature engineering and may not fully capture temporal dependencies in PV output.

### 3.4 Deep learning models

Definition:

Deep learning models learn temporal, spatial, and nonlinear representations from large-scale PV and meteorological time series.

Typical methods:

- CNN
- RNN
- LSTM
- GRU
- BiLSTM
- TCN
- seq2seq
- attention networks
- transformers

Typical strengths:

- end-to-end feature learning
- strong nonlinear representation
- effective for temporal dependencies and multivariate sequences

Typical limitations:

- high computational cost
- sensitivity to training protocol
- possible overfitting under limited or noisy data
- reduced interpretability

Use in literature review:

> Deep learning models have improved PV forecasting accuracy by learning complex temporal and nonlinear representations, but they often require large training datasets and substantial computational effort.

### 3.5 Hybrid models

Definition:

Hybrid models combine multiple mechanisms or model families to exploit complementary strengths.

Typical combinations:

- CNN-LSTM
- CNN-BiLSTM
- decomposition + deep learning
- attention + recurrent networks
- AR + neural networks
- graph neural networks + temporal models
- physical constraints + deep learning
- ensemble models

Typical strengths:

- combine linear and nonlinear modeling
- improve robustness and accuracy
- capture multi-scale or multi-source features

Typical limitations:

- more complex architecture
- higher tuning cost
- harder attribution of improvement
- increased computational burden

Use in literature review:

> Hybrid models integrate complementary modeling mechanisms and often achieve higher accuracy, but their growing complexity further strengthens the need to examine whether additional data and computational investment are justified.

---

## 4. Taxonomy by Forecast Horizon

### 4.1 Ultra-short-term forecasting

Typical horizon:

Seconds to minutes, or up to several hours depending on the study.

Typical applications:

- real-time dispatch
- short-term balancing
- ramp-event response
- equipment control
- grid security

Typical data:

- high-frequency PV output
- local meteorological measurements
- sky images
- cloud motion

Writing template:

> Ultra-short-term PV forecasting supports real-time dispatch and grid security by capturing rapid fluctuations in PV output.

### 4.2 Short-term forecasting

Typical horizon:

Hours to one day.

Typical applications:

- day-ahead scheduling
- electricity market bidding
- reserve allocation
- storage scheduling
- building energy management

Typical data:

- historical PV output
- measured weather
- NWP data
- calendar and solar-position features

Writing template:

> Short-term and day-ahead PV forecasting is closely related to dispatch planning, market participation, and reserve scheduling.

### 4.3 Medium- and long-term forecasting

Typical horizon:

Days to weeks, months, or years.

Typical applications:

- maintenance planning
- capacity planning
- energy management strategy
- long-term generation assessment

Typical data:

- historical generation records
- climatological features
- seasonal information

Writing template:

> Medium- and long-term PV forecasting is generally used for planning-oriented applications rather than real-time operational control.

---

## 5. Taxonomy by Input Information

### 5.1 Historical PV power only

Use this category when studies use only previous PV output values.

Common claim:

> Historical PV power contains temporal autocorrelation and diurnal patterns, but it cannot fully explain weather-driven variability.

### 5.2 Historical PV power plus measured meteorology

Typical variables:

- irradiance
- temperature
- humidity
- wind speed
- wind direction
- pressure
- cloud cover

Common claim:

> Measured meteorological variables improve the model's ability to capture weather-driven PV fluctuations.

### 5.3 NWP-enhanced forecasting

Use this category when studies use weather forecast data for future horizons.

Common claim:

> NWP data provide forward-looking weather information and are particularly important for day-ahead forecasting.

### 5.4 Image-based and remote-sensing inputs

Typical inputs:

- sky images
- satellite images
- cloud images
- remote-sensing irradiance
- cloud-motion features

Common claim:

> Image-based and remote-sensing inputs improve the representation of cloud dynamics and spatial weather variability.

### 5.5 Multi-source and multi-modal inputs

Use this category when studies combine power, weather, NWP, images, and neighboring station data.

Common claim:

> Multi-source inputs can improve forecast accuracy, but they also increase data acquisition, synchronization, storage, and governance requirements.

Connection to this manuscript:

This category is highly relevant because multi-source forecasting increases data investment. Use it to motivate why data cost should be considered.

---

## 6. Taxonomy by Modeling Challenge

### 6.1 Nonlinearity

PV output is affected by nonlinear interactions among irradiance, temperature, cloud movement, and system characteristics.

Related methods:

- deep learning
- kernel methods
- hybrid models
- attention mechanisms

### 6.2 Temporal dependency

PV output has diurnal cycles, short-term fluctuations, and temporal autocorrelation.

Related methods:

- RNN
- LSTM
- GRU
- TCN
- transformer
- seq2seq

### 6.3 Multi-scale behavior

PV power contains slow global trends and fast local fluctuations.

Related methods:

- decomposition
- patch segmentation
- multi-scale convolution
- frequency-domain learning
- trend-residual modeling

### 6.4 Weather-driven variability

PV output changes under cloud cover, irradiance transitions, and rapid weather shifts.

Related methods:

- weather clustering
- NWP integration
- sky image analysis
- satellite data fusion
- weather-type models

### 6.5 Data imperfection

Real-world PV datasets may contain missing values, outliers, noise, and non-stationarity.

Related methods:

- data quality routines
- imputation
- anomaly detection
- robust learning
- missingness-aware forecasting

### 6.6 Resource cost

Forecasting systems may face costs from data acquisition, storage, preprocessing, model training, retraining, and inference.

Related methods:

- data-efficiency analysis
- cost-sensitive forecasting
- proxy-cost scoring
- resource-efficient model selection
- data-retention optimization

This is the core challenge of the user's manuscript.

---

## 7. How to Position the User's Manuscript

The user's manuscript should not be positioned as:

- a new forecasting architecture paper;
- a pure sampling-frequency comparison;
- a generic deep learning benchmark;
- a pure statistical significance analysis.

It should be positioned as:

> a deployment-oriented data-investment decision framework for PV forecasting.

Recommended positioning sentence:

> Unlike model-oriented PV forecasting studies that primarily pursue lower prediction error through architectural innovation, this study examines whether additional data retention is justified under accuracy and resource constraints. It uses sampling-interval regulation as a controlled protocol to characterize the response of forecasting performance to reduced data investment and combines equivalent-accuracy sets with proxy-cost-aware ranking to identify resource-efficient candidate intervals.

---

## 8. Gap Construction Templates

### Template A: From model innovation to data-investment gap

> Existing PV forecasting studies have substantially improved prediction accuracy through model-architecture innovation, including recurrent networks, convolutional networks, attention mechanisms, transformers, decomposition strategies, and hybrid models. However, these studies usually evaluate models under predetermined data configurations. The question of how forecasting accuracy responds to different data-retention levels, and whether denser records are worth their additional resource cost, remains insufficiently characterized.

### Template B: From input expansion to data-governance gap

> Input-oriented studies improve PV forecasting by incorporating meteorological measurements, NWP data, sky images, satellite features, or neighboring-site information. While these additional inputs can enhance prediction accuracy, they also increase data acquisition, synchronization, storage, and governance requirements. Therefore, the forecasting literature still lacks a systematic evaluation of the accuracy gain obtained per unit of additional data investment.

### Template C: From high-resolution forecasting to cost-effectiveness gap

> High-resolution PV forecasting is important for capturing short-term fluctuations and ramp events. Nevertheless, finer temporal resolution also increases the volume of retained records and the computational burden of model updating. Existing high-resolution forecasting studies mainly focus on improving accuracy at fine time scales, while the cost-effectiveness of retaining dense temporal records remains underexplored.

### Template D: From uncertainty analysis to equivalent-accuracy gap

> Uncertainty-aware PV forecasting quantifies prediction uncertainty through intervals, distributions, or ensemble outputs. However, uncertainty in repeated model training and configuration selection has received less attention. In deployment settings, small RMSE differences may not be sufficient to justify substantially higher data retention, motivating the use of equivalent-accuracy sets before resource-efficiency ranking.

### Template E: From market operation to proxy-cost gap

> Market-oriented PV forecasting studies emphasize that prediction errors affect dispatch, reserve allocation, bidding, and imbalance settlement. Yet the cost of producing the forecast, including data retention, preprocessing, model training, and model updating, is often treated as external. This motivates a proxy-cost-aware framework that evaluates forecasting configurations jointly in terms of accuracy and resource consumption.

---

## 9. Contribution Mapping for the User's Manuscript

Use this mapping when polishing the contribution section.

### Contribution 1: Response characterization

Linked literature gap:

Model-oriented and high-resolution forecasting studies do not systematically characterize the accuracy response to reduced data investment.

Preferred wording:

> This study characterizes the response of PV forecasting accuracy to data-retention changes under a fixed-test-set and repeated-training protocol.

### Contribution 2: Equivalent-accuracy and PCEI framework

Linked literature gap:

Single-point RMSE optimization does not address practical accuracy tolerance or resource cost.

Preferred wording:

> This study proposes an interval-based resource-efficiency framework that first identifies accuracy-acceptable configurations and then ranks them using a proxy-cost-aware PCEI.

### Contribution 3: Scenario-based recommendation and stability boundary

Linked literature gap:

Deployment settings differ in data-governance, retraining, and inference constraints.

Preferred wording:

> This study reports high cost-effectiveness candidate intervals under multiple proxy-cost scenarios and evaluates their stability through cross-period, perturbation, baseline, and sampling-strategy checks.

---

## 10. Related Work Paragraph Blueprint

Use this blueprint to write or revise a complete related-work subsection.

### Paragraph 1: Model evolution

Start with:

> PV forecasting methods have evolved from physical and statistical approaches to machine learning, deep learning, and hybrid architectures.

Then explain:

- physical/statistical methods provide interpretability and baselines;
- machine learning and deep learning improve nonlinear temporal modeling;
- hybrid and attention-based methods further improve representation.

End with gap:

> However, these methods are primarily designed to improve accuracy under fixed data configurations.

### Paragraph 2: Input expansion and high-resolution forecasting

Start with:

> Another stream of research improves forecasting by expanding input information or increasing temporal resolution.

Then explain:

- meteorology, NWP, sky images, satellite images, neighboring sites;
- high-resolution data capture fluctuations and ramp events;
- long-sequence models and multi-scale methods address temporal complexity.

End with gap:

> These studies show the value of richer data, but they do not determine when additional data retention becomes resource-inefficient.

### Paragraph 3: Uncertainty, reliability, and cost-sensitive operation

Start with:

> Recent studies have also considered uncertainty, robustness, and operational value in PV forecasting.

Then explain:

- probabilistic forecasting handles output uncertainty;
- transfer and robustness studies handle cross-site or data-quality issues;
- market-oriented studies link errors to dispatch and settlement outcomes.

End with gap:

> Nevertheless, the cost of retaining and processing forecasting data itself remains underrepresented in the forecasting decision.

### Paragraph 4: Present study

Start with:

> To address this gap, the present study reformulates data-retention selection as an interval-based resource-efficiency problem.

Then explain:

- sampling-interval regulation;
- fixed-test-set response curve;
- equivalent-accuracy set;
- PCEI ranking;
- stability-boundary validation.

---

## 11. What Not to Do in Related Work

Do not write a model-name list:

> CNN is used in [1]. LSTM is used in [2]. GRU is used in [3]. Transformer is used in [4].

Rewrite as a functional synthesis:

> Recurrent architectures such as LSTM and GRU are widely used to capture temporal dependencies in PV output, while convolutional and attention-based models improve local feature extraction and long-range dependency modeling. Hybrid models combine these mechanisms to improve accuracy, but they also increase data and computational requirements.

Do not say:

> Few studies have studied data investment.

Rewrite as:

> The accuracy response to different data-investment levels remains insufficiently characterized, particularly when prediction accuracy, repeated-training variability, and resource cost must be evaluated jointly.

Do not say:

> Existing studies ignore cost.

Rewrite as:

> Existing studies generally focus on forecast accuracy or forecast uncertainty, while the resource cost of data retention, preprocessing, and model updating is often treated as external to the forecasting decision.

---

## 12. Taxonomy-to-Manuscript Alignment Checklist

Before finalizing the literature review, check whether:

- physical, statistical, machine learning, deep learning, and hybrid methods are grouped rather than listed;
- input expansion is separated from model architecture evolution;
- high-resolution and long-sequence forecasting are discussed as temporal-granularity studies;
- data quality and preprocessing are linked to data-governance cost when appropriate;
- uncertainty-aware forecasting is not confused with equivalent-accuracy configuration selection;
- market-oriented forecasting is used to motivate operational value, not to claim real monetary optimization;
- the final gap clearly leads to data-investment decision-making;
- the present manuscript is framed as a decision-support framework, not a new model architecture.

---

## 13. Preferred Keywords and Search Terms

Use these terms when the user asks for literature search, related work drafting, or reference expansion.

### PV forecasting terms

- photovoltaic power forecasting
- PV power prediction
- day-ahead photovoltaic forecasting
- short-term PV forecasting
- ultra-short-term PV forecasting
- high-resolution PV forecasting
- multi-step PV forecasting

### Model taxonomy terms

- physical model
- statistical model
- machine learning
- deep learning
- hybrid forecasting model
- LSTM
- GRU
- CNN
- TCN
- transformer
- attention mechanism
- graph neural network
- decomposition
- frequency-domain learning
- patch-based forecasting

### Input taxonomy terms

- numerical weather prediction
- weather forecast data
- meteorological measurements
- sky image
- satellite image
- cloud motion
- neighboring PV station
- multi-source data
- multi-modal forecasting

### Data-investment terms

- data retention
- sampling interval
- temporal resolution
- data efficiency
- data volume
- training data size
- model retraining cost
- data governance cost
- resource-efficient forecasting
- cost-sensitive forecasting

### Market and operation terms

- dispatch planning
- reserve allocation
- imbalance settlement
- market bidding
- building energy management
- grid integration
- operational value of forecasts

---

## 14. Recommended Related-Work Section Titles

Use titles such as:

- PV forecasting model evolution
- Input information and temporal granularity in PV forecasting
- High-resolution and long-sequence PV forecasting
- Data quality, uncertainty, and generalization
- Cost-sensitive forecasting and data-investment gap
- Research gap and positioning of this study

Avoid titles such as:

- Literature review
- Model introduction
- Previous algorithms
- Research status
- Existing methods summary

---

## 15. Final Taxonomy Rule

Every related-work paragraph should end by moving one step closer to the manuscript's gap:

1. Model studies improve accuracy.
2. Input studies increase information.
3. High-resolution studies show temporal granularity matters.
4. Data-quality studies show data are not free or neutral.
5. Uncertainty studies show small differences should not be over-interpreted.
6. Market-oriented studies show accuracy has operational value.
7. Therefore, the missing problem is how to decide data-retention levels under accuracy and resource constraints.

If a paragraph does not move toward this chain, revise or remove it.
