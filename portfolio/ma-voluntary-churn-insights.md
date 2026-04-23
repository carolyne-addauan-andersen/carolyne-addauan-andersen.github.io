# Translating Medicare Advantage Churn Models Into Retention Strategy

*A decision‑focused machine learning and applied insights case study*

---

## Problem Context

Predicting voluntary churn in Medicare Advantage is only the starting point.

While churn models are often framed as tools for **risk identification**, their real value emerges when model outputs are translated into **actionable insight**—informing benefit strategy, member messaging, and marketing design ahead of Annual Enrollment Period (AEP).

This project deliberately extends beyond prediction to address a critical follow‑up question:

> **Once the model is trained and members are scored—then what?**

---

## From Prediction to Decision Support

In this work, a voluntary churn model was developed to identify members most likely to disenroll during AEP. Rather than stopping at risk scores, the analysis focused on how model outputs could meaningfully support decision‑making, including:

- Understanding *why* members churn  
- Distinguishing predictors that remain **stable vs. transient** over time  
- Identifying signals that can be **operationalized** in retention and marketing strategy  

Model explainability and post‑model validation were treated as **core deliverables**, not secondary artifacts.

---

## Explainability as a Strategic Tool

Model explainability techniques were used to surface the primary drivers of churn risk across key domains, including:

- **Household stability**
- **Affordability and benefit fit**
- **Customer service friction**
- **Clinical and utilization complexity**
- **Local market competition**

By quantifying feature influence rather than relying solely on rankings or coefficients, this approach enabled clearer interpretation of how member characteristics and experiences translate into switching behavior.

Importantly, these insights were shared in a form readily consumable by **non‑technical stakeholders**, helping bridge advanced analytics and business strategy.

---

## Validating Predictors Against Real‑World Outcomes

A central component of this project was a **retrospective validation** using subsequent enrollment outcomes to test whether predictors identified during model development continued to reflect real member behavior.

This validation process enabled:

- Confirmation of **persistent churn drivers**
- Identification of **signals that lost relevance** due to market or benefit changes
- Discovery of **emerging patterns** not previously emphasized

Rather than assuming year‑to‑year stability, predictors were explicitly stress‑tested against actual outcomes to guard against stale assumptions.

---

## What Stayed Consistent

Several signals demonstrated strong consistency across modeling and validation cycles:

- **Household stability** remained one of the most protective factors against churn
- **Tenure effects** persisted, with newer members exhibiting higher switching behavior
- **Customer service friction**—including high inquiry volume, appeals, and grievances—continued to be one of the strongest behavioral indicators of churn
- **Local market competitiveness** maintained a meaningful influence on member decision‑making

These stable predictors represent **high‑confidence levers** for retention planning.

---

## What Changed — And Why That Matters

Equally important were predictors that **lost significance** during the validation period.

Several previously reliable signals—particularly those tied to affordability proxies and certain clinical acuity measures—no longer differentiated churners from stayers. This shift likely reflects a combination of:

- Benefit design changes reducing variability
- Market convergence among competing plans
- Operational or policy interventions
- Changes in member decision criteria

Identifying *what no longer matters* is just as important as identifying what does—helping prevent outdated assumptions from driving future strategy.

---

## Deep‑Dive Insights: Utilization and Clinical Signals

Supplementary analyses explored how churn risk varied across utilization and clinical dimensions.

### Pharmacy Utilization
- Minimal medication engagement appeared stabilizing  
- Higher regimen complexity, specialty medication use, and elevated out‑of‑pocket pharmacy costs were associated with increased churn risk  

### Clinical Conditions
- Neurodegenerative conditions showed protective effects, likely driven by continuity‑of‑care needs
- Metabolic, pulmonary, and behavioral health conditions were associated with higher churn, reflecting affordability and access pressures  

### Healthcare Utilization
- Overall **intensity of care**, rather than acute events, was most predictive  
- High claim volume, denials, and repeated specialty visits correlated with increased churn
- Emergency and inpatient utilization alone did not meaningfully differentiate churn once adjusted for overall utilization intensity  

Together, these findings help distinguish **experience‑driven churn** from churn related to isolated health events.

---

## Turning Insights Into Action

The outcome of this work is not simply a better model, but a clearer roadmap for **pre‑AEP strategy**:

- Which member experiences warrant proactive engagement
- Which messaging themes align with true churn drivers
- Which signals should inform segmentation and creative design
- Where operational improvements may reduce avoidable churn

By validating model insights against real behavior, this approach supports **evidence‑based prioritization** rather than reactive outreach.

---

## What This Project Demonstrates

This project highlights applied data science strengths beyond model training:

- Treating models as **decision inputs**, not final products
- Using explainability to connect analytics with strategy
- Applying year‑over‑year validation to manage feature drift
- Translating complex signals into actionable business insight
- Operating effectively in regulated, high‑stakes healthcare environments

Most importantly, it reflects a mindset anchored in the question **“Then what?”**—ensuring analytics lead to meaningful change.

---

*This project is presented in a de‑identified, non‑proprietary form for portfolio purposes. All descriptions focus on analytical approach, reasoning, and learnings rather than internal systems, metrics, or employer‑specific implementations.*
