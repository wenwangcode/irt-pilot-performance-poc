# Pilot Performance Prediction using Item Response Theory (IRT)

Predictive psychometric analytics framework for estimating pilot competency and forecasting future assessment performance using Rasch-based Item Response Theory (IRT) models in R.

---

## Overview

This project explores how historical assessment performance can be used to estimate latent pilot ability and predict future training or testing outcomes.

Instead of treating all test questions equally, the framework models:

- Pilot latent skill level
- Question/item difficulty
- Assessment fit and reliability
- Probability of future success

Using psychometric methods from Item Response Theory (IRT) and Extended Rasch Modeling (eRm), the system calibrates both individuals and assessment items to generate statistically grounded competency estimates.

---

## Motivation

Traditional scoring methods often fail to account for the varying difficulty of assessment items.

This framework was designed to answer questions such as:

- If a pilot performs well on difficult scenarios, how should their competency estimate change?
- Can historical performance predict success on future assessments?
- Which test items are most informative?
- Are some assessments unfairly biased or poorly calibrated?

The project applies psychometric modeling techniques commonly used in educational testing and adaptive assessments to aviation-style competency evaluation.

---

## Technical Architecture

The framework is built in R using the following ecosystem:

- `eRm`
- `ltm`
- `devtools`
- `roxygen2`

The project programmatically wraps and exposes large portions of the `eRm` modeling functionality into a reusable package structure for experimentation, diagnostics, and predictive workflows.

Core capabilities include:

- Person parameter estimation
- Item parameter estimation
- Model diagnostics
- Likelihood-ratio testing
- Simulation utilities
- Predictive performance evaluation
- Visualization tooling

---

## Example Workflow

```r
# Fit Rasch Model
res.rasch <- RM(raschdat1)

# Estimate pilot ability
pres.rasch <- person.parameter(res.rasch)

# Visualize person-item map
plotPImap(res.rasch, sorted = TRUE)

# Perform likelihood-ratio testing
lrres.rasch <- LRtest(res.rasch, splitcr = "mean")
```

---

## Research Background

The framework is inspired by psychometric modeling approaches commonly used in:

- Educational testing
- Aviation training systems
- Competency-based assessment
- Adaptive learning platforms
- Human performance analytics
