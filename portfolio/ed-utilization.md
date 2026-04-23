# Predicting Frequent Emergency Department Utilization in Medicare Advantage

*A domain-driven machine learning case study integrating healthcare expertise, predictive modeling, and actionable insight.*


---
## Why This Problem Matters

Emergency Department (ED) overutilization among Medicare Advantage (MA) members presents both a **clinical and business challenge**. Repeated ED visits often signal fragmented care, unmet social and medical needs, and gaps in preventive or primary care access.

For payers operating in a value-based environment, avoidable ED utilization directly impacts **member experience, quality performance, and total cost of care**.

Rather than reacting after utilization has already escalated, this model focuses on **anticipating risk**—identifying members most likely to experience *two or more ED visits in the next year* so that care teams can intervene earlier and redirect care to more appropriate settings.

### ED Utilization Risk Lifecycle

    Chronic illness, access barriers, SDOH
                    ↓
            Initial ED utilization
                    ↓
          Repeated / frequent ED use
                    ↓
      Higher cost, poorer experience,
      fragmented care pathways

This framing positions ED utilization as a signal of upstream care gaps—not an isolated event.


---
## What I Built

I designed and validated a **machine learning model** that prospectively identifies Medicare Advantage members (age 65+) at risk of frequent ED utilization over a 12-month horizon using only historical, pre-index data.

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

Populations such as D-SNP and group plans were intentionally excluded due to differences in benefit design, care models, and social complexity—highlighting a key domain-driven modeling decision to preserve interpretability, fairness, and governance readiness.

---
## Modeling Approach (High Level)

### End-to-End Modeling Flow

    Enrollment & Eligibility
              ↓
    Claims & Administrative Data
              ↓
    Feature Engineering
    • Utilization patterns
    • NYU ED severity
    • Chronic conditions
    • Medication risk
    • Access & SDOH
              ↓
    ED Risk Model (Monthly Scoring)
              ↓
    SHAP Explainability
    • Global drivers
    • Member-level rationale
              ↓
    Risk Stratification
              ↓
    Targeted Interventions

### Temporal Model Design

    Feature Window        Prediction Window
    Prior 12 months   →   Next 12 months

    Outcome: ≥ 2 ED visits

This strict separation mirrors real-world deployment and ensures that model performance reflects **true prospective risk**, not retrospective pattern recognition.

### Feature Engineering Guided by Healthcare Domain Knowledge

Rather than relying on raw utilization alone, features were engineered across **clinically meaningful domains**, including:

- **ED utilization patterns** (frequency, recency, persistence)
- **ED visit severity**, using the **NYU Emergency Department Algorithm**
- **Chronic disease burden and multimorbidity**
- **Frailty and functional risk signals**
- **Medication complexity and high-risk drug classes**
- **Primary care access and continuity**
- **Preventive care gaps**
- **Social determinants of health (SDOH)**

### Feature Domain Map

    Utilization Patterns     | Clinical Complexity    | Medication Risk
    -------------------------|------------------------|-------------------------
    Prior ED use             | Chronic conditions     | Polypharmacy
    Recency / persistence    | Multimorbidity         | High-risk medications

    Severity & Acuity        | Functional Risk        | Access & Context
    -------------------------|------------------------|-------------------------
    NYU ED Algorithm         | Frailty indicators     | PCP continuity, SDOH


---
## Explainability as a First‑Class Requirement

In healthcare, prediction alone is not sufficient—stakeholders must understand **why** a member is identified as high risk.

To support transparency and adoption, the model leverages **SHAP (SHapley Additive exPlanations)** at two levels:

- **Global explainability:** Identifies consistent drivers of ED risk across the population
- **Individual‑level explainability:** Articulates why a specific member is flagged, enabling meaningful outreach conversations

This interpretability layer bridges analytics and operations, moving teams from *risk scores* to *targeted actions*.


---
## Key Insights From the Analysis

> The model revealed more than *who* is high risk—
> it clarified *why* interventions succeed or fail.

- Prior ED utilization reflects **unresolved care gaps**, not transient events
- Patterns of **avoidable ED use** are more actionable than raw visit counts
- **Frailty and medication complexity** often outweigh single diagnoses
- Effective outreach depends on *why* ED care is sought—not just frequency
- Risk stratification is strongest when paired with **driver-specific interventions**


---
## From Risk Scores to Action

Model outputs are intentionally designed to support real operational decisions:

- Risk stratification using deciles or actionable flags
- Alignment of **intervention type**, not just intensity, based on dominant risk drivers
- Identification of members best suited for:
  - Primary care re‑engagement
  - Urgent care or telehealth diversion
  - Care management or medication review

By combining predictive risk with explainability, the model enables **right‑touch interventions**, avoiding one‑size‑fits‑all outreach.

---
## What Makes This Work Stand Out

- Predictive modeling grounded in clinical and operational reality
- Thoughtful population definition and bias‑aware design
- Clear temporal alignment and governance readiness
- Strong emphasis on interpretability and trust
- Direct connection between analytics and care delivery impact

---
## Skills Demonstrated

- Medicare Advantage analytics and domain expertise
- Predictive modeling and temporal validation
- Feature engineering using claims and administrative data
- Model explainability (SHAP)
- Translating technical outputs into clinical and business insight
- Designing analytics for real‑world operational use

*This case study is intentionally de‑identified and abstracted for portfolio purposes while preserving the core analytic and domain‑driven principles of the work.*
