# Translating Medicare Advantage Churn Models Into Retention Strategy

*A decision‑focused machine learning and applied insights case study*

---

## Problem Context

Predicting voluntary churn in Medicare Advantage is only the starting point.

While churn models are often framed as tools for **risk identification**, their real value emerges when model outputs are translated into **actionable insight**—informing benefit strategy, member messaging, and marketing design ahead of Annual Enrollment Period (AEP).

This project extends beyond predictive modeling to answer a critical follow‑up question:

> **Once the model is trained and members are scored, then what?**

---

## From Prediction to Decision Support

In this work, a voluntary churn model was developed to identify members most likely to disenroll during AEP. Rather than stopping at risk scores, the analysis focused on:

- Understanding *why* members churn  
- Determining which predictors remain **stable vs. transient** over time  
- Identifying signals that can be **operationalized** in retention and marketing strategy  

Model explainability and post‑model validation were treated as **core deliverables**, not secondary artifacts.

---

## Model Explainability as a Strategic Tool

Explainability techniques were used to surface the primary drivers of churn risk across several domains:

- **Household stability**
- **Affordability and benefit fit**
- **Customer service friction**
- **Clinical and utilization complexity**
- **Local market competition**

By quantifying feature influence rather than relying solely on model coefficients or rankings, this approach enabled clear interpretation of how member characteristics and experiences translate into switching behavior.

Importantly, these insights were shared in a form consumable by **non‑technical stakeholders**, bridging data science and business strategy.

---

## Validating Predictors Against Real‑World Outcomes

A key component of this project was a **retrospective validation** using subsequent enrollment outcomes to test whether predictors identified during model development continued to reflect real member behavior.

This validation allowed for:

- Confirmation of **persistent churn drivers**  
- Identification of **signals that lost relevance** due to market or benefit changes  
- Discovery of **emerging patterns** not previously emphasized  

Rather than assuming year‑to‑year stability, predictors were explicitly stress‑tested against actual outcomes to guard against stale assumptions.

---

## What Stayed Consistent

Several signals showed strong consistency across modeling and validation cycles:

- **Household stability** remained one of the most protective factors against churn  
- **Tenure effects** persisted, with newer members exhibiting higher switching behavior  
- **Customer service friction** (high inquiry volume, appeals, grievances) continued to be one of the strongest behavioral indicators of churn  
- **Local market competitiveness** maintained a meaningful influence on member decision‑making  

These stable predictors represent **high‑confidence levers** for retention planning.

---

## What Changed — And Why That Matters

Equally important were predictors that **lost significance** in the validation period.

Several previously reliable signals—particularly those tied to affordability proxies and certain clinical acuity measures—no longer differentiated churners from stayers. This shift likely reflects:

- Benefit design changes reducing variability  
- Market convergence among competing plans  
- Operational or policy interventions  
- Changes in member decision criteria  

Identifying *what no longer matters* is just as important as knowing what does—preventing outdated assumptions from driving future strategy.

---

## Deep‑Dive Insights: Utilization and Clinical Signals

Supplementary analyses explored churn relationships across:

### Pharmacy Utilization
- Minimal medication engagement appeared stabilizing  
- Higher regimen complexity, specialty medications, and elevated out‑of‑pocket pharmacy costs increased churn risk  

### Clinical Conditions
- Neurodegenerative conditions showed protective effects, likely due to continuity‑of‑care needs  
- Metabolic, pulmonary, and behavioral health conditions were associated with higher churn, reflecting affordability and access pressures  

### Healthcare Utilization
- Overall intensity of care—not acute events—was most predictive  
- High claim volume, denials, and repeated specialty visits correlated with increased churn  
- Emergency and inpatient utilization alone did not meaningfully differentiate churn once corrected for intensity  

These findings help distinguish **experience‑driven churn** from episodic health events.

---

## Turning Insights Into Action

The outcome of this work is not just a better model—but a clearer roadmap for **pre‑AEP strategy**:

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

Most importantly, it reflects a mindset oriented around **“Then what?”**—ensuring analytics lead to meaningful change.

---

*This project is presented in a de‑identified, non‑proprietary form for portfolio purposes. All descriptions focus on analytical approach, reasoning, and learnings rather than internal systems, metrics, or employer‑specific implementations.*
