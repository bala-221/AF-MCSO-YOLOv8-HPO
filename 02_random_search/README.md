# Random Search

This directory contains the Random Search hyperparameter optimization
experiments for YOLOv8m used in this study.

## Notebooks

### `random_search_single_year.ipynb`

Performs Random Search under the single-year experimental setting.

The notebook defines the hyperparameter search space, evaluates
candidate configurations, ranks them using the study's fitness
criterion, selects the best configuration, and performs final
training and evaluation.

### `random_search_cross_year.ipynb`

Performs the cross-year Random Search experiments used to evaluate
the generalization of optimized YOLOv8m configurations across
different data collection years.

The following directions are evaluated:

- Year2021 → Year2022
- Year2022 → Year2021

## How to Run

1. Install the dependencies specified in the root `requirements.txt`.
2. Prepare the Year2021 and Year2022 datasets according to the main
   repository instructions.
3. Update the dataset paths in the configuration section of the notebook.
4. Verify the experimental settings, random seeds, and search-space
   configuration.
5. Run the notebook cells sequentially from top to bottom.

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
