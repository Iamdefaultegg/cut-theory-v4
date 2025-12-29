# Appendix B — Tests & Falsifiability (Cut Theory v4.0)

This appendix expands the minimum test set referenced in the Core Canon.

## B1 — T1: Permeability sweep (identity collapse)

**Goal:** Demonstrate that increasing inter-region coupling collapses multiple local identities into a single global stationary behavior.

**Setup:**
- Build a Markov/CA world with two regions A and B.
- Set coupling (permeability) parameter ε controlling cross-region transitions.
- Initialize A and B with distinct local patterns.

**Measure:**
- Block marginals over time (mass in A vs B).
- Stationary distribution(s) as ε varies.
- Spectral gap γ(ε) if using a Markov kernel.

**Prediction:**
- ε=0: multiple stationary behaviors (one per closed region).
- ε>0: gradual leakage; above a threshold, a unique global stationary behavior dominates.

**Falsification signal:**
- No localized persistence at ε=0 across generic initializations, or no systematic collapse with increasing ε.

## B2 — T2: Linear response near separation

**Goal:** Verify that near ε≈0, identity leakage is first-order in ε for the perturbation model.

**Setup:**
- Start with block-separated kernel M (ε=0).
- Add perturbation εS introducing cross-block transitions.

**Measure:**
- d/dε of block marginal m_A(ε) at ε→0.

**Prediction:**
- Leading-order change is linear in ε (before higher-order effects dominate).

**Falsification signal:**
- Strong nonlinear response at arbitrarily small ε under controlled perturbations.

## B3 — T3: Fabric geodesics (network test)

**Goal:** Test whether observed propagation in an empirical recurrence network follows paths minimizing a chosen “tension cost”.

**Setup:**
- Build a recurrence graph from data (neural co-activation, interaction logs, etc.).
- Assign edge weights from recurrence strength.

**Measure:**
- Compare observed propagation routes to shortest paths under a cost function (e.g., -log(weight)).

**Prediction:**
- Propagation is biased toward tension-minimizing paths more than chance baselines.

**Falsification signal:**
- No better-than-baseline alignment between observed propagation and predicted paths.

## B4 — Reporting template

For each test, report:
- Model/data description
- Parameter ranges
- Metrics used
- Plots (ε vs marginals, ε vs γ, path-alignment scores)
- Whether results support / challenge the interface mapping
