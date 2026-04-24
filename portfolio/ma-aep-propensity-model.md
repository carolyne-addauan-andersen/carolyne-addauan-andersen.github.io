# Modeling Medicare Advantage Enrollment Propensity During Annual Enrollment Period

*A multi‑year, domain‑driven machine learning case study focused on adaptation, feature evolution, and decision‑aligned modeling.*


---
## Why This Problem Is Hard

Predicting which individuals will enroll in a Medicare Advantage (MA) plan during Annual Enrollment Period (AEP) is not a one‑time modeling exercise—it is an **ongoing, adaptive problem**.

Each enrollment season introduces new sources of variation:

- Changing CMS regulations and benefit designs
- Shifts in market competition and plan availability
- A growing population aging into Medicare eligibility
- Evolving consumer behavior and marketing channels
- Year‑over‑year drift in prospect composition

A model that performs well one year may degrade the next if it is not intentionally **re‑evaluated, re‑designed, and re‑aligned** with current market conditions.

This narrative documents how I approached enrollment propensity modeling across **multiple years and model iterations**, treating the model not as a static artifact, but as a **living system** that evolves alongside both the data and the business context.

### Enrollment Propensity as an Adaptive System

    Regulatory changes
           ↓
    Market & plan shifts
           ↓
    Prospect population drift
           ↓
    Feature relevance changes
           ↓
    Model re‑evaluation & iteration

This framing treats enrollment modeling as an evolving system rather than a fixed prediction task.

---
## Framing the Problem as Propensity, Not Conversion

At its core, this work focuses on **propensity modeling**:

> *Given available pre‑AEP information, which individuals are most likely to enroll if engaged?*

This framing intentionally avoids over‑attributing causality to outreach methods alone and instead emphasizes:

- Prioritization under uncertainty
- Efficient allocation of limited outreach capacity
- Maximizing opportunity capture rather than perfect prediction

Success is therefore defined not by overall accuracy, but by the model’s ability to **rank prospects meaningfully** under conditions of severe class imbalance.


---
## Year‑Over‑Year Model Evolution

Rather than chasing a single “best” algorithm, this project reflects **progressive refinement** across multiple modeling dimensions.

### Algorithm Choice as a Function of Maturity

Early model iterations emphasized robustness and interpretability using ensemble approaches. As data volume, feature richness, and analytical maturity increased, later iterations transitioned toward **gradient‑boosted tree frameworks** better suited for:

- Capturing complex non‑linear interactions
- Handling high‑dimensional feature spaces
- Maintaining stability under extreme class imbalance

Algorithm evolution mirrored deeper **problem understanding**, not tooling preference alone.


### Modeling Maturity Progression

    Problem understanding increases
              ↓
    Feature richness expands
              ↓
    Algorithmic flexibility increases
              ↓
    Evaluation aligns more closely with decisions

Model evolution followed analytical maturity, not novelty.


### Feature Engineering Driven by Domain Expertise

One of the most significant drivers of improvement over time was **feature intuition**, not algorithmic complexity.

Features were designed to reflect how individuals make enrollment decisions during AEP, including:

- **Eligibility timing signals** (e.g., proximity to initial eligibility)
- **Socio‑economic proxies** related to affordability and plan sensitivity
- **Market context features** capturing competition and availability
- **Behavioral and lifestyle indicators** linked to health engagement
- **Technology and digital adoption proxies** relevant to enrollment pathways
- **Healthcare access signals** reflecting provider availability

Critically, features were **added, removed, and re‑weighted each year** based on relevance, availability, and market changes—reinforcing that *feature engineering is adaptive, not static*.


---
## Learning to Handle Extreme Class Imbalance

Enrollment propensity modeling is inherently imbalanced: the vast majority of eligible individuals do **not** enroll in any given year.

This project reflects a deliberate evolution in how imbalance was handled:

- Early strategies relied on **resampling methods**
- Later iterations shifted toward **cost‑sensitive learning**
- Final approaches optimized **recall‑weighted objectives** aligned to outreach goals

Rather than forcing artificial balance, the guiding principle became:

> **Preserve data integrity while ensuring the model prioritizes rare but valuable positives.**

This evolution reflects increasing alignment between *statistical techniques* and *operational realities*.


---
## Evaluation Beyond Standard Metrics

Traditional metrics such as accuracy provide little value in this context.

Instead, evaluation emphasized:

- Ranking quality (lift and gains behavior across score bands)
- Stability across validation splits and retraining cycles
- Consistency of signal within high‑priority segments
- Sensitivity to feature drift and population change

The guiding evaluation question was never “How accurate is the model?” but:

> *Does this model meaningfully improve prioritization versus random or heuristic selection?*


---
## Explainability as a Requirement, Not an Add‑On

As the modeling approach became more complex, explainability became **non‑negotiable**.

Interpretability techniques were used to:

- Validate learned signals against domain intuition
- Detect unintended bias or proxy effects
- Support responsible use and governance considerations
- Communicate *why* specific individuals were prioritized

Explainability functioned as a **feedback loop**, informing feature refinement and model iteration—not merely stakeholder communication.


---
## What This Project Demonstrates

This work highlights several dimensions of applied data science maturity:

- Modeling as an **iterative, year‑over‑year process**
- Deep **domain expertise** guiding feature evolution
- Pragmatic handling of extreme class imbalance
- Evaluation aligned to **ranking utility**, not generic metrics
- Responsible model development with explainability and transparency

Most importantly, it demonstrates an ability to **adapt analytical strategy as the environment changes**, which is often more valuable than marginal improvements in model performance.


---
## Key Takeaway

The most effective enrollment propensity models are not the most complex—they are the ones that evolve alongside:

- Policy changes
- Market dynamics
- Data availability
- Organizational learning

This reflects how I approach applied machine learning in regulated, high‑stakes environments: **anchored in domain understanding, adaptable by design, and focused on decision impact rather than abstraction.**

---
*This case study is intentionally abstracted and de‑identified for portfolio purposes. All modeling approaches and examples are presented to illustrate analytical reasoning, domain adaptation, and methodological evolution rather than proprietary implementations or results.*
