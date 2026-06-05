---

title: "Understanding Logistic Regression in Program Evaluation"
date: 2026-06-05
categories:
- Analytics

tags:
- Statistics
- Logistic Regression
- Program Evaluation
- Data Science
layout: single
author_profile: true

---

Logistic regression is one of the most useful tools in a program evaluator's toolkit. Unlike linear regression, which predicts a continuous outcome, logistic regression predicts the probability that an event occurs.

In program evaluation, these models are particularly valuable when trying to understand which participants are most likely to exhibit a specific behavior or outcome.

## A Practical Example

Consider a statewide electric vehicle incentive program.

One question administrators may ask is:

> Which participants would have purchased an electric vehicle even without receiving an incentive?

This phenomenon is commonly referred to as **free ridership**.

Using survey data, a logistic regression model can estimate how participant characteristics influence the likelihood of belonging to this group.

## Why Not Use Simple Percentages?

Simple cross-tabulations can be useful for exploratory analysis, but they often fail to account for multiple factors simultaneously.

For example:

* Income may influence purchase decisions.
* Vehicle ownership history may influence purchase decisions.
* Environmental attitudes may influence purchase decisions.
* Demographic characteristics may influence purchase decisions.

A logistic regression model allows these variables to be evaluated together.

## Example Code

The following example demonstrates a simple logistic regression model in R.

```r
model <- glm(
  free_rider ~ income + age + ethnicity + environmental_attitudes,
  data = survey_data,
  family = "binomial"
)

summary(model)
```

## Interpreting Odds Ratios

One of the most useful outputs from a logistic regression model is the odds ratio.

An odds ratio greater than 1 indicates increased odds of the outcome occurring.

An odds ratio less than 1 indicates decreased odds of the outcome occurring.

For example:

| Variable              | Odds Ratio |
| --------------------- | ---------- |
| High Income           | 1.75       |
| Previous EV Ownership | 2.10       |
| Incentive Importance  | 0.55       |

In this hypothetical example:

* High-income participants are more likely to be free riders.
* Previous EV owners are substantially more likely to be free riders.
* Participants who strongly value incentives are less likely to be free riders.

## Limitations

Like any statistical method, logistic regression has limitations.

Researchers should consider:

* Sample size requirements
* Multicollinearity
* Missing data
* Survey design effects
* Variable selection

Model outputs should always be interpreted alongside subject matter expertise and program context.

## Final Thoughts

Statistical models should not replace decision-making, but they can provide valuable evidence to support it.

In program evaluation, logistic regression is particularly effective for identifying the factors most strongly associated with participant outcomes and helping organizations make more informed, data-driven decisions.
