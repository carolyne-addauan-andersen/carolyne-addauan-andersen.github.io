# Understanding Multi‑Channel Marketing Impact During Annual Enrollment Period

*A transparent, incrementality‑focused attribution case study bridging marketing analytics, time‑series modeling, and business decision support.*

---

## Why This Problem Matters

During Annual Enrollment Period (AEP), health insurance organizations invest across a mix of **digital and offline marketing channels** to drive consumer awareness and plan applications. While activity increases across Paid Search, Paid Social, TV, Digital Display, Direct Mail, and Email, measuring **which channels actually drive incremental demand** remains a persistent challenge.

Traditional attribution methods—such as last‑touch or rule‑based heuristics—tend to over‑credit lower‑funnel channels and understate the value of upper‑funnel demand creation. Conversely, many modern black‑box approaches lack transparency, making them difficult to trust or operationalize.

This project addresses a core question faced by marketing and analytics teams:

> **How do daily marketing exposures across multiple channels contribute to application volume, once baseline demand and seasonality are accounted for?**

The goal is not just attribution—but **actionable, defensible insight** that stakeholders can understand and use.

---

## What I Built

I designed a **time‑series–based marketing attribution framework** that estimates the **incremental contribution** of multiple online and offline channels to daily application volume during a peak enrollment period.

Key design principles include:

- **Aggregate, privacy‑safe modeling** (no user‑level identity resolution)
- **Incrementality‑first attribution**, not touchpoint sequencing
- **Explicit handling of lag and carryover effects**
- **Interpretable statistical modeling** aligned with the data‑generating process
- **Transparency** suitable for both data scientists and business stakeholders

Rather than asking *who converted*, the analysis asks:

> *When marketing activity increases, do applications increase—and by how much?*

---

## Unit of Analysis and Data Design

To keep interpretation clean and aligned to business reality, the dataset was intentionally simple and aggregated:

- **Unit of analysis:** Calendar date  
- **Outcome:** Daily application count  
- **Predictors:** Daily channel‑level exposure metrics  
- **Controls:**  
  - Day‑of‑week effects  
  - Seasonal indicators  
  - Time trend terms  

Each row answers a single question:

> *Given what happened on this day, what application volume would we expect?*

This structure enables inclusion of both digital and offline channels while avoiding identity and privacy constraints.

---

## Modeling Approach (High Level)

### Conceptual Framework

The attribution framework follows a clear, auditable structure:

**Daily Marketing Inputs**  
↓  
**Time‑Aware Feature Engineering**  
- Same‑day exposure  
- Lagged effects (e.g., t‑1 to t‑7)  
- Carryover / decay terms  

↓  
**Count‑Based Time‑Series Model**  
(Poisson / Negative Binomial)  
+ Seasonality and trend controls  

↓  
**Counterfactual Prediction**  

↓  
**Incremental Channel Contributions**

This design makes modeling assumptions explicit while reflecting real‑world marketing behavior.

---

### Why Count‑Based Models?

Rather than defaulting to complex machine learning, I used **generalized linear models (GLMs)** designed for count outcomes.

Advantages:

- Naturally handle non‑negative integer outcomes
- Support over‑dispersion via Negative Binomial models
- Produce **interpretable coefficients**
- Enable transparent counterfactual analysis

The objective is not maximum predictive accuracy, but **stable estimation of incremental effects**.

---

## Capturing Lag and Carryover Effects

Marketing influence is rarely instantaneous—especially for upper‑funnel channels like TV, Display, or Direct Mail.

To reflect this reality, channel exposures are modeled using:

- Same‑day exposure terms
- Short‑term lag windows
- Distributed lag or decay representations

This avoids systematically undervaluing channels that influence decisions earlier in the consideration cycle.

---

## Attribution Logic: Incrementality Over Credit

Attribution is computed using **counterfactual prediction**, not touchpoint ordering.

Conceptually:

```python
# Fit count-based time-series model
model = fit_glm(Y, X_channels, X_controls)

# Baseline prediction
baseline_pred = model.predict(X_full)

channel_contributions = {}

for channel in channels:
    X_cf = X_full.copy()
    X_cf[channel] = 0  # remove channel exposure
    f_pred = model.predict(X_cf)

    channel_contributions[channel] = sum(baseline_pred - cf_pred)

```

This answers a more actionable question:

> **How many applications would be expected to disappear if a given channel were removed, holding everything else constant?**

The result is **incremental contribution**, not attribution driven by sequence position.

---

## Handling Multi‑Channel Correlation

Channels rarely operate independently:

- Paid Search often intensifies during TV campaigns  
- Email frequently coincides with other outreach  
- Channels move together during high‑intent periods  

Instead of forcing artificial separation, the model:

- Estimates channels jointly  
- Attributes marginal contribution *conditional on others*  
- Naturally shares credit when channels co‑vary  

This reflects real marketing environments more honestly than strict single‑touch attribution.

---

## Validation and Model Trust

Model confidence comes from **consistency across diagnostics**, not a single metric:

- Distribution comparison (Poisson vs. Negative Binomial)  
- Over‑dispersion testing  
- Time‑series residual inspection  
- Sensitivity to lag and carryover assumptions  
- Directional stability across holdout periods  

Trust is built through **repeatability and transparency**—key for marketing analytics adoption.

---

## From Analysis to Decision Support

For business partners, the value lies in **directional insight**:

- Which channels consistently drive incremental demand  
- Which channels support others indirectly  
- Where diminishing returns may emerge over time  

For data scientists, the value lies in:

- Explicit assumptions  
- Counterfactual logic  
- Reproducible attribution mechanics  

This dual focus ensures the analysis is both **technically sound** and **operationally useful**.

---

## What This Project Demonstrates

- Incrementality‑focused attribution can be both **rigorous and interpretable**  
- Aggregate time‑series modeling remains highly effective for marketing problems  
- Transparency outperforms black boxes when decisions are at stake  
- Attribution is as much a communication problem as a modeling one  

---

## Skills Demonstrated

- Multi‑channel marketing analytics  
- Time‑series modeling for count data  
- Incrementality‑based attribution design  
- Lag and carryover feature engineering  
- Counterfactual analysis  
- Translating technical outputs into business insight  

---

*This case study is intentionally abstracted and de‑identified for portfolio purposes. All channel descriptions, modeling approaches, and examples are presented to illustrate methodology and analytical thinking rather than disclose proprietary data, metrics, or results.*
