# Multi‑Channel Attribution in Practice: Modeling Assumptions, Tradeoffs, and Failure Modes

*A technical deep dive into aggregate‑level marketing attribution, focused on modeling decisions, statistical tradeoffs, and practical lessons learned.*

---

## Why a Second Article?

The companion case study focuses on **what** the attribution framework does and **why** it is useful for decision‑making.  
This article focuses on **how** the model works under the hood—and, just as importantly, the choices and compromises involved.

This write‑up is intended for:

- Data scientists evaluating attribution approaches  
- Analysts implementing time‑series models in practice  
- Technically curious marketing and analytics stakeholders  

The goal is not to present a single “correct” solution, but to surface the **engineering and statistical decisions** that materially shape attribution outcomes.

---

## Data‑Generating Reality (and Why It Matters)

Before selecting a model, it is important to clarify the implicit data‑generating process:

- Baseline demand evolves continuously over time  
- Marketing exposure perturbs that baseline  
- Different channels influence behavior on different time horizons  
- Channels are often correlated by design  

Any attribution method that ignores these realities—explicitly or implicitly—will struggle with biased credit assignment.

This framing immediately rules out naïve approaches (e.g., independent per‑channel regressions) and motivates **joint, time‑aware modeling**.

---

## Feature Engineering *Is* the Model

In practice, attribution performance is driven less by the estimator and more by **feature construction**.

### Core Feature Groups

- **Same‑day exposure terms**  
  Capture immediate response, common for lower‑funnel channels such as Paid Search or Email.

- **Lagged exposure terms**  
  Represent short‑term consideration windows typical of Display or Paid Social.

- **Carryover representations**  
  Approximate ad stock for upper‑funnel channels such as TV or Direct Mail.

- **Baseline demand controls**  
  Day‑of‑week effects, seasonal indicators, and trend components.

> The model can only learn what is encoded—**lag structure is attribution structure**.

---

## Why GLMs Instead of Machine Learning?

A natural question is why not use tree‑based models, neural networks, or sequence models.

The choice to use **Poisson and Negative Binomial generalized linear models (GLMs)** was deliberate.

### Advantages

- Distribution aligns naturally with count outcomes  
- Coefficients are interpretable on the log scale  
- Models remain stable under moderate multicollinearity  
- Counterfactual predictions behave predictably  

### Tradeoffs

- Linear effects on the log scale  
- Limited automatic interaction discovery  
- Less flexible than non‑parametric models  

In applied attribution, **interpretability and stability often dominate marginal gains in predictive accuracy**.

---

## Handling Over‑Dispersion Explicitly

Operational demand data frequently violates Poisson assumptions.

Over‑dispersion is handled by:

- Inspecting mean–variance relationships  
- Using Negative Binomial regression when variance exceeds the mean  

Ignoring over‑dispersion typically leads to:

- Inflated confidence  
- Unstable contribution estimates  
- Over‑interpretation of noise  

Distributional diagnostics are therefore not optional—they directly affect attribution credibility.

---

## Joint Estimation and the Correlation Problem

Marketing channels are rarely independent:

- Upper‑funnel activity often lifts downstream demand signals  
- Email and promotional outreach cluster around high‑intent periods  
- Budgets shift together over time  

Joint estimation does not “solve” correlation, but it does something essential:

> It attributes contribution **conditional on other channels being present**.

This naturally produces shared credit where appropriate and discourages false precision.

---

## Counterfactual Attribution Mechanics

Attribution is derived via **model‑based counterfactuals**, not path enumeration.

At a high level:

- Fit the full model  
- Predict baseline outcomes using observed data  
- Remove exposure for one channel  
- Re‑predict outcomes  
- Attribute the difference  

This approach aligns closely with causal thinking—even in the absence of randomized experiments—and avoids the brittleness of:

- Touchpoint ordering rules  
- Arbitrary attribution windows  
- Credit dilution across long conversion paths  

---

## Sensitivity Analysis and Failure Modes

No attribution model is universally robust.

Key sensitivities include:

- Lag window length  
- Carryover decay assumptions  
- Channel scaling and normalization  
- Time aggregation level (daily vs. weekly)  

Rather than optimizing a single specification, I stress‑tested alternative assumptions to assess **directional stability**, not precision.

---

## Relationship to Marketing Mix Modeling (MMM)

This framework shares conceptual DNA with Marketing Mix Models, but differs in emphasis:

- Shorter time horizons  
- Finer temporal granularity  
- Operational decision support rather than long‑range budget optimization  

Think of this approach as **decision‑oriented attribution**, not spend allocation optimization.

---

## What I Would Do With More Data

With experimental lift measurement or richer user‑level linkage, I would:

- Calibrate models using geo‑ or time‑based experiments  
- Explicitly model cross‑channel interactions  
- Introduce hierarchical structures across markets or segments  
- Combine aggregate models with micro‑level insight  

Attribution improves fastest when **modeling is paired with measurement**.

---

## Final Lessons Learned

- Feature engineering dictates credit allocation  
- Attribution is conditional, not absolute truth  
- Transparent models earn more trust than complex ones  
- Sensitivity analysis is more valuable than precision  

At its best, attribution modeling does not deliver *answers*—it delivers **better decisions**.

---

*This case study is intentionally abstracted and de‑identified for portfolio purposes. All modeling approaches, examples, and design choices are presented to illustrate analytical reasoning and engineering judgment rather than proprietary data, systems, or implementations.*
