# Predicting Frequent Emergency Department Utilization in Medicare Advantage

*A domain-driven machine learning case study integrating healthcare expertise, predictive modeling, and actionable insight.*

---

## Why This Problem Matters

Emergency Department (ED) overutilization among Medicare Advantage (MA) members is both a **clinical and business challenge**. Repeated ED visits often signal fragmented care, unmet social and medical needs, and gaps in preventive or primary care access.

For payers operating in a value-based environment, avoidable ED utilization directly impacts **member experience, quality performance, and total cost of care**.

Rather than reacting after utilization has already escalated, this project focuses on **anticipating risk**—identifying members most likely to experience *two or more ED visits in the next year* so that care teams can intervene earlier and redirect care to more appropriate settings.

---

## What I Built

I designed and validated a **machine learning prototype model** that prospectively identifies Medicare Advantage members (age 65+) at risk of frequent ED utilization over a 12-month horizon using only historical, pre-index data.

Key design principles include:

- **Prospective, operationally realistic modeling** (no data leakage)
- **Domain-informed feature engineering** grounded in clinical pathways
- **Interpretability-first design** to support trust and adoption
- **Actionability** aligned to care management and outreach workflows

The model is designed to run **monthly**, scoring currently enrolled members with continuous enrollment, and to integrate seamlessly with downstream intervention strategies.

---

## Population and Scope

To ensure clinical and operational relevance, the model targets a clearly defined population:

- Medicare Advantage PPO and HMO members
- Age 65 years and older
- Continuously enrolled for the prior 12 months
- Actively enrolled at time of scoring

Populations such as D-SNP and group plans were intentionally excluded due to differences in benefit design, care models, and social complexity—highlighting a key domain-driven modeling decision to preserve interpretability and fairness.

---

## Modeling Approach (High Level)

### Temporal Design

The model uses strict, non-overlapping time windows:

- **Feature Window:** Prior 12 months
- **Prediction Window:** Subsequent 12 months
- **Outcome:** ≥2 ED visits in the prediction window

This structure mirrors real-world deployment and ensures that model performance reflects true prospective risk.

### Feature Engineering Guided by Healthcare Domain Knowledge

Rather than relying on raw utilization alone, features were engineered across **clinically meaningful domains**, including:

- **ED utilization patterns** (frequency, recency, persistence)
- **ED visit severity**, using the **NYU Emergency Department Algorithm** to distinguish avoidable vs. unavoidable visits
- **Chronic disease burden and multimorbidity**
- **Frailty and functional risk signals**
- **Medication complexity and high-risk drug classes**
- **Primary care access and continuity**
- **Preventive care gaps**
- **Social determinants of health (SDOH)**

This domain-driven approach ensures that predictions reflect **underlying care gaps and modifiable risk factors**, not just historical volume.

---

## Explainability as a First-Class Requirement

In healthcare, prediction alone is not sufficient. Stakeholders must understand **why** a member is identified as high risk.

To support transparency and adoption, the model leverages **SHAP (SHapley Additive exPlanations)** to explain predictions at both levels:

- **Global explainability:** Identifies consistent drivers of ED risk across the population (e.g., avoidable ED patterns, chronic burden, medication complexity)
- **Individual-level explainability:** Clearly articulates why a specific member is flagged, enabling meaningful outreach conversations

This interpretability layer bridges analytics and operations—helping care teams move from *risk scores* to *targeted actions*.

---

## From Risk Scores to Action

Model outputs are designed to support real operational decisions:

- Risk stratification using deciles or flags
- Alignment of intervention type (not just intensity) based on dominant risk drivers
- Identification of members most appropriate for:
  - Primary care engagement
  - Urgent care or telehealth diversion
  - Care management or medication review

By combining predictive risk with explainability, the model supports **right-touch interventions**, not one-size-fits-all outreach.

---

## What Makes This Work Stand Out

This project highlights the intersection of **machine learning and healthcare domain expertise**:

- Predictive modeling grounded in clinical and operational reality
- Thoughtful population definition and bias-aware design
- Clear temporal alignment and governance readiness
- Strong emphasis on interpretability and trust
- Direct connection between analytics and care delivery impact

---

## Skills Demonstrated

- Healthcare analytics and Medicare Advantage domain expertise
- Predictive modeling (classification, temporal validation)
- Feature engineering using claims and administrative data
- Model explainability (SHAP)
- Translating technical outputs into business and clinical insight
- Designing analytics for real-world operational use

---

*This case study is intentionally de-identified and abstracted for portfolio purposes while preserving the core analytic and domain-driven principles of the work.*
