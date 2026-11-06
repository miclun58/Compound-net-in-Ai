# Open Research Challenge: Integrating Mixed Expert Knowledge

**A companion research note to Compound Net**  
**Status:** Open research agenda — not a claim of a solved problem  
**Date:** November 2026

## 1. Motivation

Compound Net explores a simple architectural idea: train specialized neural networks on separate domains, freeze them, and feed their predictions together with the original input features into a small combining model. The experiments CN1–CN4, documented in the [original research report](Compound%20Net%20in%20Ai.pdf), suggest that a small linear combiner can match or slightly outperform the specific standalone baselines tested, while requiring only 13–17 *trainable parameters in the combiner*.

However, prediction errors remained relatively high. This exposes a broader research challenge: **How should an AI system integrate specialized knowledge when its input contains different domains, mixtures of domains, and problems of varying complexity?**

A system may possess capable specialists yet still fail to combine their judgments reliably. The problem of *knowledge integration* deserves investigation in its own right.

## 2. What the experiments do—and do not—show

The Compound Net experiments use synthetic target functions, specialist networks trained on domain-specific examples, and a combiner trained on mixed examples. They establish results for the tested configurations only; they do not establish a general solution to mixed-domain reasoning or robust expert integration.

In CN4, the combiner has 17 trainable parameters, versus 449 in the standalone baseline. Importantly, the frozen specialist networks also have parameters. The four CN4 specialists total 3,172 parameters, so the complete Compound Net architecture has 3,189 parameters. **Combiner trainability, total parameter count, training compute, and inference cost must be evaluated separately.**

The observed errors alone do not identify the underlying cause. Possible contributors include limitations of fixed linear combination, insufficient domain identification, ambiguities in mixed training data, model capacity, optimization, and intrinsic noise. Each explanation requires a controlled test.

## 3. The integration problem

With frozen experts \(E_1, E_2, \ldots, E_k\), an ordinary linear combiner can be written as:

\[
\hat{y}(x) = b + w^\top x + \sum_{j=1}^{k} v_j E_j(x).
\]

The coefficients \(v_j\) are fixed across inputs. This is an important constraint if the relevance and reliability of each expert depend on the current example.

For instance, one input may be best handled by a mathematics specialist, another by a physics specialist, and a third may require interactions among several disciplines. Simple and difficult problems may also demand different forms of integration.

One hypothesis is that the combination mechanism needs *input-dependent selection and weighting* rather than a single fixed set of coefficients.

## 4. A possible direction: a dedicated integration model

A candidate architecture would keep the specialist models available while introducing a trained integration module that estimates which expert outputs matter for a particular input.

A schematic formulation is:

\[
\hat{y}(x) = h(x) + \sum_{j=1}^{k} g_j(x) E_j(x),
\]

where \(g_j(x)\) expresses context-dependent weighting or routing, and \(h(x)\) represents a direct path from the input.

Such a module might investigate three capabilities:

1. **Domain recognition:** Identify which specialist knowledge is relevant, including when domains overlap.
2. **Difficulty awareness:** Respond differently to simple, composite, or unfamiliar cases.
3. **Reliability estimation:** Detect when an expert is likely to be inaccurate, irrelevant, or overconfident.

This is a **research hypothesis**, not an established solution or proof that an entirely new class of AI is required.

## 5. Relationship to existing research

Methods such as stacking, gating networks, mixture-of-experts, routing, ensembles, and uncertainty-aware prediction already address parts of the problem. Their capabilities and limitations should be studied carefully rather than dismissed.

The open question is whether a tailored integration mechanism can improve performance on mixed-domain, variable-complexity tasks **under fair comparisons**, while remaining computationally and statistically efficient.

## 6. Suggested experiments

A future research program could proceed in stages:

1. **Reproduce the baseline.** Publish or reconstruct the data-generation procedures, training code, random seeds, hyperparameters, and multiple independent runs for CN1–CN4.
2. **Isolate the combination mechanism.** Compare the current fixed linear combiner against a linear model using only original features, expert-only averaging, stacking, nonlinear combiners, and input-dependent gating.
3. **Vary domain mixtures.** Test pure domains, known mixtures, shifted mixtures, overlapping targets, and previously unseen combinations.
4. **Vary complexity.** Construct transparent groups of easy, intermediate, and compositional tasks and report performance for each group.
5. **Test expert reliability.** Introduce imperfect, biased, noisy, missing, or out-of-distribution experts to measure when integration helps or harms.
6. **Move beyond synthetic data.** After controlled demonstrations, evaluate suitable real-world multi-domain tasks with explicit train/validation/test separation.

For every comparison, report predictive error, variability across runs, baseline tuning, total model parameters, trainable parameters at each stage, training cost, and inference cost. Where practical, compare systems at matched resource budgets.

## 7. Key research questions

- Can a model infer which expert should be trusted for each input?
- When does input-dependent routing outperform fixed combination?
- How should an integration model handle conflicting expert predictions?
- Can it recognize that none of the available experts is reliable?
- Does difficulty-aware integration generalize to unseen domain combinations?
- What efficiency gains remain when the *entire* expert system is counted?

## 8. Scope and limitations

This document proposes a research direction. It does not claim that the mixed-expert problem is unsolved in all settings, that existing approaches have been exhausted, or that Compound Net has proved a new general AI architecture. The original experiments are limited to synthetic tasks and selected baselines.

A central distinction should be preserved: **having specialized knowledge is not the same as being able to integrate it effectively.** Whether a dedicated integration model can close that gap is a question for future empirical work.

## 9. Invitation to continue the research

The original Compound Net research has been made public so others can scrutinize, reproduce, challenge, or extend it. Independent researchers, students, and AI engineers are welcome to take this research question forward, whether through a new combiner, a more capable routing model, better benchmarks, or an entirely different approach.

Start with the [Compound Net research report](Compound%20Net%20in%20Ai.pdf), and share questions or findings through [GitHub Issue #1 — Invitation](https://github.com/miclun58/Compound-net-in-Ai/issues/1).

**The challenge is not simply to develop capable experts, but to determine when and how their knowledge should be combined.**
