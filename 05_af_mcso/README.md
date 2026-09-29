# AF-MCSO

This directory contains the proposed AF-MCSO hyperparameter optimization
experiments for YOLOv8m used in this study.

## Notebooks

### `af_mcso_single_year.ipynb`

Implements the proposed AF-MCSO method under the single-year experimental
setting and performs hyperparameter optimization, candidate selection,
final training, and evaluation.

### `af_mcso_cross_year.ipynb`

Implements the proposed AF-MCSO method under the cross-year experimental
setting.

The following directions are evaluated:

- Year2021 → Year2022
- Year2022 → Year2021

## How to Run

1. Install the dependencies specified in the root `requirements.txt`.
2. Prepare the Year2021 and Year2022 datasets.
3. Update the dataset paths in the notebook configuration section.
4. Verify the search-space and experimental settings.
5. Run the notebook cells sequentially from top to bottom.

## Method

AF-MCSO is the proposed multi-fidelity hyperparameter optimization
method evaluated in this study. It combines adaptive candidate
generation with low- and high-fidelity model evaluations to search
for effective YOLOv8m hyperparameter configurations under a controlled
computational budget.

## Outputs

The notebooks report:

- Selected hyperparameter configuration
- Validation fitness
- Precision
- Recall
- mAP@50
- mAP@50:95
- Computational time

The resulting performance is compared with the untuned YOLOv8m baseline,
Random Search, Hyperband, and DEHB.
