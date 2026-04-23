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

This project documents how I approached this problem across **multiple model iterations over several years**, treating the model not as a static artifact, but as a **living system** that evolves with both the data and the business context.

---

## Framing the Problem as Propensity, Not Conversion

At its core, this work focuses on **propensity modeling**:

> *Given available pre‑AEP information, which individuals are most likely to enroll if engaged?*

This framing intentionally avoids over‑attributing causality to outreach methods alone and instead focuses on:

- Prioritization under uncertainty  
- Efficient allocation of limited outreach capacity  
- Maximizing opportunity capture rather than perfect prediction  

Success is defined not by overall accuracy, but by the model’s ability to **rank prospects meaningfully** under severe class imbalance.

---

## Year‑Over‑Year Model Evolution

Rather than chasing the “best” algorithm at a single point in time, this project reflects **progressive refinement** across several dimensions.

### 1. Algorithm Choice as a Function of Maturity

Early iterations emphasized robustness and interpretability using ensemble methods. As data volume, feature richness, and modeling maturity increased, later iterations transitioned toward **gradient‑boosted tree frameworks** better suited for:

- Complex non‑linear interactions  
- High‑dimensional feature spaces  
- Stable performance under class imbalance  

The evolution of algorithms mirrored an evolution in **problem understanding**, not just tooling preference.

---

### 2. Feature Engineering Driven by Domain Expertise

One of the most significant drivers of improvement over time was **feature intuition**, not algorithmic complexity.

Features were intentionally designed to reflect how individuals make enrollment decisions during AEP, including:

- **Eligibility timing signals** (e.g., proximity to initial eligibility)
- **Socio‑economic proxies** related to affordability and plan sensitivity
- **Market context features** capturing competition and availability
- **Behavioral and lifestyle indicators** linked to health engagement
- **Technology and digital adoption proxies** relevant to enrollment pathways
- **Healthcare access signals** reflecting provider availability  

Importantly, features were **added, removed, and re‑weighted** each year based on relevance, availability, and changing market conditions—reinforcing that *feature engineering is adaptive, not static*.

---

## Learning to Handle Extreme Class Imbalance

Enrollment propensity modeling is fundamentally imbalanced: the vast majority of eligible individuals do **not** enroll in any given year.

This project reflects an evolution in how imbalance was handled:

- Early strategies relied on **resampling methods** to address skew
- Later iterations shifted toward **cost‑sensitive learning**, preserving the original data distribution
- Final iterations explicitly optimized for **recall‑weighted objectives**, aligning evaluation with business priorities  

Rather than forcing artificial balance, the goal became:

> **Preserve data integrity while ensuring the model learns to prioritize rare but valuable positives.**

This evolution reflects increasing alignment between *statistical solutions* and *operational goals*.

---

## Evaluation Beyond Standard Metrics

Traditional metrics such as accuracy are largely uninformative in this context.

Instead, model evaluation emphasized:

- Ranking quality (e.g., lift and gains behavior across score bands)
- Stability across validation splits and retraining cycles
- Consistency of signal in high‑priority segments
- Sensitivity to feature drift and population changes  

The central question was never “How accurate is the model?” but rather:

> *Does this model meaningfully improve prioritization versus random or heuristic selection?*

---

## Explainability as a Requirement, Not an Add‑On

As the model became more complex, explainability became **non‑negotiable**.

Model interpretation techniques were used to:

- Validate whether learned signals aligned with domain intuition  
- Detect unintended bias or proxy effects  
- Support responsible use and governance considerations  
- Communicate *why* the model prioritized certain individuals  

Explainability was treated as a **feedback loop**, informing feature refinement and model iteration—not just stakeholder communication.

---

## What This Project Demonstrates

This work highlights several dimensions of applied data science maturity:

- Modeling as an **iterative, year‑over‑year process**, not a one‑time build
- Deep **domain expertise** guiding feature selection and adaptation
- Pragmatic handling of severe class imbalance aligned to decision goals
- Evaluation grounded in **ranking utility**, not generic metrics
- Responsible model development with transparency and explainability  

Most importantly, it demonstrates an ability to **adapt analytical strategy as the environment changes**, which is often more valuable than marginal gains in model performance.

---

## Key Takeaway

The most effective enrollment propensity models are not the most complex—they are the ones that evolve alongside:

- Policy changes  
- Market dynamics  
- Data availability  
- Organizational learning  

This project reflects how I approach applied machine learning in regulated, high‑stakes environments: **anchored in domain understanding, adaptable by design, and focused on decision impact rather than abstraction.**

---

*This case study is intentionally abstracted and de‑identified for portfolio purposes. All modeling approaches and examples are presented to illustrate analytical reasoning, domain adaptation, and methodological evolution rather than proprietary implementations or results.*
