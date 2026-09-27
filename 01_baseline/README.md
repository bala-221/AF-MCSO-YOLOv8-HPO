# Untuned YOLOv8m Baseline

This directory contains the untuned YOLOv8m baseline experiments
used for comparison with the hyperparameter optimization methods
evaluated in this study.

## Notebooks

### `baseline_single_year.ipynb`

Runs the single-year baseline experiment using YOLOv8m without
hyperparameter optimization.

The notebook includes dataset preparation, training, validation,
testing, and reporting of the final detection performance.

### `baseline_cross_year.ipynb`

Runs the cross-year generalization experiments for the untuned
YOLOv8m baseline.

The following evaluation directions are considered:

- Year2021 → Year2022
- Year2022 → Year2021

## How to Run

1. Install the dependencies specified in the root `requirements.txt`.
2. Prepare the Year2021 and Year2022 datasets.
3. Update the dataset paths in the configuration section of the notebook.
4. Run the notebook cells sequentially from top to bottom.

## Evaluation Metrics

The experiments report:

- Precision
- Recall
- mAP@50
- mAP@50:95
- Training time

The baseline results are compared with the hyperparameter-optimized
YOLOv8m models presented in the subsequent directories.
