# AI Bias in Skin Disease Diagnosis

An empirical study of skin-tone bias, fairness, representation bias, mitigation strategies, and cross-dataset generalization in automated skin disease diagnosis.

---

## Overview

This project investigates whether automated skin disease classification models exhibit performance disparities across different skin-tone groups and evaluates several mitigation strategies designed to reduce these disparities.

The study combines:

- Diagnostic performance evaluation
- Skin-tone-specific performance analysis
- Fairness metric analysis
- Data-level augmentation
- Training-level reweighting
- Representation-level bias analysis
- External dataset evaluation
- Cross-dataset generalization analysis

The primary development dataset is **Fitzpatrick17k**, while the **DDI (Diverse Dermatology Images)** dataset is used for external evaluation.

The central analytical perspective of the project is:

**Diagnostic Performance → Skin-Tone Fairness → Representation Bias → External Generalization**

---

## Research Objectives

The project investigates the following key questions:

1. Does the baseline skin disease classifier exhibit performance disparities across skin-tone groups?
2. Can targeted mitigation strategies reduce observed skin-tone performance gaps?
3. How do different mitigation strategies affect overall diagnostic performance?
4. Does skin-tone information remain recoverable from learned image representations?
5. Can representation-level mitigation reduce skin-tone-related information?
6. Do mitigation strategies improve performance when evaluated on an external dermatology dataset?
7. How does dataset shift affect model performance and fairness?

---

## Datasets

### Fitzpatrick17k

Fitzpatrick17k is used as the primary development and internal evaluation dataset.

It provides dermatological images associated with disease labels and Fitzpatrick skin-tone annotations.

The dataset is used for:

- Model development
- Baseline evaluation
- Skin-tone-specific analysis
- Fairness analysis
- Mitigation experiments
- Representation analysis

### DDI

The DDI dataset is used as an external evaluation dataset.

It is used to assess how the trained models behave under dataset shift and whether the observed performance characteristics transfer beyond the development dataset.

The external evaluation focuses on:

- Overall diagnostic performance
- Fairness-related metrics
- Generalization behavior
- Representation mitigation analysis

---

## Experimental Design

The project uses two complementary experimental tracks.

### Internal Mitigation — Fitzpatrick17k

The internal mitigation experiments evaluate:

**Baseline → M1 → M2 → M1 + M2**

Where:

- **Baseline** = Original classification model
- **M1** = Data-level skin-tone augmentation
- **M2** = Training-level reweighting
- **M1 + M2** = Combined augmentation and reweighting

These experiments are used to study mitigation effects within the development dataset.

### External Evaluation — DDI

The external evaluation evaluates:

**Baseline → M2 → M3 → M2 + M3**

Where:

- **Baseline** = Original classification model
- **M2** = Training-level reweighting
- **M3** = Representation-level adversarial mitigation
- **M2 + M3** = Combined reweighting and representation mitigation

The DDI evaluation is designed to examine external/generalization behavior under dataset shift.

---

## Important Experimental Note

The mitigation strategies are not evaluated in an identical factorial design across both datasets.

M1 and M2 are evaluated on Fitzpatrick17k as internal mitigation experiments.

M2, M3, and M2 + M3 are evaluated on DDI as external/generalization experiments.

Therefore, the experimental design should not be interpreted as a complete factorial comparison of every mitigation strategy across both datasets.

Instead, the study follows the actual experimental protocol:

**Internal Mitigation**

Fitzpatrick17k

**Baseline → M1 → M2 → M1 + M2**

↓

**External Evaluation**

DDI

**Baseline → M2 → M3 → M2 + M3**

This separation avoids unsupported cross-dataset claims and reflects the actual evaluation pipeline.

---

## Mitigation Strategies

### M1 — Skin-Tone Augmentation

M1 uses targeted augmentation to increase representation of underrepresented skin-tone groups during model development.

The goal is to investigate whether improving representation at the data level can reduce skin-tone-related performance disparities.

### M2 — Reweighting

M2 applies training-level reweighting to account for differences in representation across groups.

The objective is to encourage the model to give greater consideration to underrepresented groups during optimization.

### M3 — Representation-Level Mitigation

M3 uses representation-level adversarial mitigation to investigate whether skin-tone information can be reduced in learned image representations.

A representation probe is used to evaluate how much skin-tone information remains recoverable from the learned representations.

### M1 + M2

M1 + M2 combines data-level augmentation with training-level reweighting.

This experiment investigates whether combining two mitigation strategies produces different fairness and performance outcomes compared with applying either strategy independently.

### M2 + M3

M2 + M3 combines training-level reweighting with representation-level mitigation.

This configuration is evaluated on the external DDI dataset to investigate whether combining mitigation at the training and representation levels affects external performance and fairness.

---

## Evaluation Metrics

The project evaluates both conventional diagnostic performance and fairness-related behavior.

### Diagnostic Performance

The main performance metrics include:

- Accuracy
- Balanced Accuracy
- Macro Precision
- Macro Recall
- Macro F1
- Weighted F1

These metrics provide complementary views of model performance, particularly under class imbalance.

### Fairness Metrics

The project evaluates multiple fairness-related measures, including:

- Accuracy Gap
- Macro-F1 Gap
- Worst-Group Accuracy (WGA)
- Equalized Odds Difference (EOD)
- Demographic Parity Difference (DPD)
- Equal Opportunity Difference (EqOD)

These metrics are used together rather than relying on a single fairness criterion.

### Representation Analysis

Representation-level analysis includes:

- Skin-tone probe performance
- Probe Balanced Accuracy
- Changes in representation predictability
- Comparison of representation behavior before and after mitigation

---

## Final Results and Analysis

The final analysis package includes results from both internal and external evaluation.

### Fitzpatrick17k Internal Results

The final internal comparison includes:

- Baseline
- M1
- M2
- M1 + M2

The final internal evaluation examines overall diagnostic performance and skin-tone-specific performance.

The project also evaluates changes in:

- Accuracy gaps
- Macro-F1 gaps
- Skin-tone-specific accuracy
- Skin-tone-specific Macro F1

### DDI External Results

The external evaluation includes:

- Baseline
- M2
- M3
- M2 + M3

The DDI evaluation focuses on external performance, fairness behavior, and representation mitigation.

### Generalization Analysis

Cross-dataset analysis compares performance between:

**Fitzpatrick17k → DDI**

for the model configurations where corresponding internal and external results are available.

The final generalization analysis includes:

- Accuracy
- Balanced Accuracy
- Macro F1
- Weighted F1
- Generalization gaps

The results demonstrate the effect of dataset shift on diagnostic performance.

---

## Final Figures

The repository contains paper-ready figures covering the main experimental findings.

The final figure set includes:

- **Fig. 5** — Fitzpatrick17k Internal Model Comparison
- **Fig. 6** — Fitzpatrick17k Skin-Tone Performance
- **Fig. 7** — Fitzpatrick17k Fairness Comparison
- **Fig. 8** — DDI External Model Comparison
- **Fig. 9** — DDI External Fairness Comparison
- **Fig. 10** — R3 Representation Mitigation
- **Fig. 11** — F1 vs EOD Trade-off
- **Fig. 12** — Fitzpatrick17k vs DDI Performance
- **Fig. 13** — Generalization Gap

These figures summarize the principal findings of the experimental pipeline.

---

## Final Tables

The repository includes final tables covering:

- Overall model performance
- Fairness comparisons
- Representation comparisons
- Fitzpatrick17k vs DDI performance
- Generalization gaps
- Mitigation effectiveness
- Key findings
- Study limitations

These tables are organized as part of the final results package.

---

## Project Workflow

The complete experimental workflow is provided in:

`AI Bias in Skin DIsease Diagnosis.ipynb`

The workflow covers:

1. Environment setup
2. Dataset preparation
3. Data quality analysis
4. Baseline training
5. Baseline bias characterization
6. M1 augmentation
7. M2 reweighting
8. M1 + M2 evaluation
9. External DDI evaluation
10. M3 representation mitigation
11. M2 + M3 combined mitigation
12. Fairness analysis
13. Representation analysis
14. Generalization analysis
15. Final tables and figures

---

## Requirements

The main dependencies include:

- PyTorch
- Torchvision
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Pillow
- PyYAML

Install the dependencies with:

```bash
pip install -r requirements.txt
```

## Reproducibility

The project uses a fixed random seed for the experimental workflow.

The repository includes:

- Configuration files
- Dataset preparation files
- Training configurations
- Evaluation scripts
- Model checkpoints
- Final metrics
- Final tables
- Final figures

These resources are provided to support reproducibility of the reported experiments.

---

## Repository Contents

The repository contains the complete research workflow, including:

- The main experimental notebook
- Source code
- Configuration files
- Evaluation outputs
- Final metrics
- Final tables
- Final figures
- Trained model checkpoints
- Dataset preparation resources

Large datasets and files subject to repository or dataset licensing constraints may not be distributed through the repository.

---

## Limitations

Several limitations should be considered when interpreting the results:

- The external dataset has different characteristics from the development dataset.
- Dataset shift can substantially affect diagnostic performance.
- Skin-tone labels and demographic attributes may contain annotation uncertainty.
- Fairness metrics can behave differently under class imbalance and limited subgroup sample sizes.
- Improvements in one fairness metric may not imply improvements in all fairness metrics.
- Representation-level debiasing may reduce recoverable skin-tone information without guaranteeing improved clinical performance.
- Not every mitigation strategy is evaluated on every dataset.
- M3 and M2 + M3 do not have corresponding Fitzpatrick17k internal evaluation results in the final pipeline.
- Therefore, complete internal-to-external generalization claims cannot be made for every mitigation strategy.
- External performance should be interpreted as evidence of generalization under dataset shift rather than proof of universal fairness.

---

## Research Contribution

This project provides an empirical framework for studying bias in automated skin disease diagnosis by combining:

- Skin-tone-specific performance analysis
- Multiple fairness metrics
- Targeted mitigation strategies
- Data-level augmentation
- Training-level reweighting
- Representation-level bias analysis
- External dataset evaluation
- Cross-dataset generalization analysis

The combination of these analyses provides a more comprehensive view of fairness than evaluating overall classification accuracy alone.

The central analytical perspective of the project is:

**Diagnostic Performance → Skin-Tone Fairness → Representation Bias → External Generalization**

---

## Project Status

**Status: Completed**

The repository contains the experimental workflow, configuration files, trained model checkpoints, evaluation outputs, final tables, and paper-ready figures generated during the completed study.

The final analysis emphasizes the relationship between diagnostic performance, skin-tone fairness, representation bias, and external generalization.

---

## Ethical Considerations

This project is intended for research into algorithmic bias and fairness in medical image analysis.

The reported results should not be interpreted as evidence that the evaluated models are suitable for clinical diagnosis or deployment.

Performance on dermatological image datasets does not establish clinical safety, reliability, or effectiveness in real-world medical settings.

Fairness metrics should also be interpreted in the context of dataset composition, annotation quality, subgroup representation, and clinical relevance.

---

## Data and Model Usage

The repository may contain processed data, configuration files, derived outputs, and trained model checkpoints depending on repository size and dataset licensing restrictions.

Underlying datasets may be subject to their own licensing, access, attribution, and redistribution requirements.

Users should obtain and use the original datasets according to their respective terms and should not assume that repository contents grant unrestricted redistribution rights to third-party datasets.

---

## License

This repository is intended primarily for academic and research purposes.

Please review the licensing and usage restrictions of the underlying datasets before redistributing or using any dataset content.

---

## Acknowledgements

This project builds upon publicly available dermatology datasets and open-source machine learning frameworks.

The authors acknowledge the researchers and institutions responsible for creating and maintaining the datasets and tools used in this study.
