# AI Bias in Skin Disease Diagnosis

## Overview

This project investigates **skin-tone-related bias and fairness in automated skin disease diagnosis systems**. The study evaluates whether a deep learning model performs consistently across different skin-tone groups and examines whether targeted mitigation strategies can reduce observed disparities without substantially compromising diagnostic performance.

The project follows a two-stage evaluation design:

- **Internal evaluation:** Fitzpatrick17k
- **External evaluation:** DDI (Diverse Dermatology Images)

The study evaluates multiple mitigation strategies targeting different sources of bias, including **data-level augmentation, class/skin-tone reweighting, and representation-level adversarial mitigation**.

---

## Research Objectives

The main objectives of this project are to:

1. Measure the baseline performance of a skin disease classification model across different skin-tone groups.
2. Characterize disparities in diagnostic performance between skin-tone groups.
3. Investigate the effectiveness of targeted bias mitigation strategies.
4. Evaluate whether mitigation strategies improve fairness while preserving diagnostic utility.
5. Examine the generalization of mitigation strategies to an external dermatology dataset.
6. Analyze whether representation-level mitigation reduces the amount of skin-tone information encoded in learned representations.

---

## Datasets

### Fitzpatrick17k

Fitzpatrick17k is used as the primary **development and internal evaluation dataset**.

It provides dermatological images associated with skin-tone information based on the Fitzpatrick skin type scale and disease labels.

In this project, Fitzpatrick17k is used for:

- Dataset preparation
- Baseline model training
- Skin-tone bias characterization
- Internal mitigation experiments
- Fairness evaluation
- Comparison of mitigation strategies

### DDI

The **Diverse Dermatology Images (DDI)** dataset is used as an **external evaluation dataset**.

DDI is not used as the primary development dataset. Instead, it is used to evaluate whether the learned diagnostic behavior and selected mitigation strategies transfer beyond the development dataset.

The external evaluation focuses on:

- Baseline generalization
- M2 reweighting
- M3 representation mitigation
- Combined M2 + M3 mitigation
- External fairness
- Representation-level analysis

---

## Evaluation Design

The experimental design separates **internal mitigation evaluation** from **external generalization evaluation**.

### Fitzpatrick17k — Internal Evaluation

The internal experiments compare:

```text
Baseline
   ↓
M1
   ↓
M2
   ↓
M1 + M2
