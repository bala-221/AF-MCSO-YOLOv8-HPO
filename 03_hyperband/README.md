# Hyperband

This directory contains the Hyperband hyperparameter optimization
experiments for YOLOv8m used in this study.

## Notebooks

### `hyperband_single_year.ipynb`

Performs Hyperband under the single-year experimental setting.

The notebook defines the common hyperparameter search space,
evaluates candidate configurations using multiple training budgets,
promotes stronger configurations, selects the best configuration,
and performs final training and evaluation.

### `hyperband_cross_year.ipynb`

Performs the cross-year Hyperband experiments used to evaluate
the generalization of optimized YOLOv8m configurations across
different data collection years.

The following directions are evaluated:

- Year2021 → Year2022
- Year2022 → Year2021

## How to Run

1. Install the dependencies specified in the root `requirements.txt`.
2. Prepare the Year2021 and Year2022 datasets according to the
   main repository instructions.
3. Update the dataset paths in the notebook configuration section.
4. Verify the search space, training budgets, and experimental settings.
5. Run the notebook cells sequentially from top to bottom.

## Multi-Fidelity Optimization

Hyperband evaluates candidate configurations using different
training budgets. Lower-fidelity evaluations are used to identify
promising configurations, which are then promoted for higher-fidelity
evaluation.

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

The resulting performance is compared with the untuned baseline
and the other hyperparameter optimization methods included in
this repository.
