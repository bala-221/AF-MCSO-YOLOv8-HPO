# DEHB

This directory contains the Differential Evolution Hyperband (DEHB)
hyperparameter optimization experiments for YOLOv8m used in this study.

## Notebooks

### `dehb_single_year.ipynb`

Performs DEHB under the single-year experimental setting.

The notebook defines the common hyperparameter search space,
generates candidate configurations using differential evolution,
evaluates candidates under multiple training budgets, selects the
best configuration, and performs final training and evaluation.

### `dehb_cross_year.ipynb`

Performs the cross-year DEHB experiments used to evaluate the
generalization of optimized YOLOv8m configurations across different
data collection years.

The following directions are evaluated:

- Year2021 → Year2022
- Year2022 → Year2021

## How to Run

1. Install the dependencies specified in the root `requirements.txt`.
2. Prepare the Year2021 and Year2022 datasets according to the main
   repository instructions.
3. Update the dataset paths in the notebook configuration section.
4. Verify the search space, DEHB settings, training budgets, and
   experimental configuration.
5. Run the notebook cells sequentially from top to bottom.

## Optimization Strategy

DEHB combines differential evolution with Hyperband-style
multi-fidelity resource allocation. Candidate configurations are
generated through evolutionary search and evaluated using different
training budgets to balance exploration and computational efficiency.

## Optimization Criterion

Candidate configurations are ranked using a composite fitness
criterion based on:

- mAP@50:95
- Recall
- Mean mAP@50:95 of the three least-performing classes

## Outputs

The notebooks report:

- Selected hyperparameter configuration
- Precision
- Recall
- mAP@50
- mAP@50:95
- Computational time

The resulting performance is compared with the untuned baseline,
Random Search, Hyperband, and the proposed AF-MCSO method.
