# AF-MCSO-YOLOv8 Hyperparameter Optimization

Implementation and experimental code associated with our study on hyperparameter optimization of YOLOv8m for weed detection.

This repository contains the experiments conducted using the untuned YOLOv8m baseline, Random Search, Hyperband, Differential Evolution Hyperband (DEHB), and the proposed AF-MCSO method.

The experiments include both single-year evaluation and cross-year generalization using the Year2021 and Year2022 subsets of the 2SeasonWeedDet8 dataset.

## Methods

The following methods are included:

1. Untuned YOLOv8m baseline
2. Random Search
3. Hyperband
4. Differential Evolution Hyperband (DEHB)
5. Proposed AF-MCSO

All hyperparameter optimization methods are evaluated using a common search space and controlled computational budgets to support a fair comparison.

## Repository Structure

```text
AF-MCSO-YOLOv8-HPO/
│
├── 01_baseline/
│   ├── README.md
│   ├── baseline_single_year.ipynb
│   └── baseline_cross_year.ipynb
│
├── 02_random_search/
│   ├── README.md
│   ├── random_search_single_year.ipynb
│   └── random_search_cross_year.ipynb
│
├── 03_hyperband/
│   ├── README.md
│   ├── hyperband_single_year.ipynb
│   └── hyperband_cross_year.ipynb
│
├── 04_dehb/
│   ├── README.md
│   ├── dehb_single_year.ipynb
│   └── dehb_cross_year.ipynb
│
├── 05_af_mcso/
│   ├── README.md
│   ├── af_mcso_single_year.ipynb
│   └── af_mcso_cross_year.ipynb
│
├── requirements.txt
├── CITATION.cff
└── README.md
```

Each experiment directory contains a separate README with instructions for running the corresponding notebooks.

## Experimental Settings

Two evaluation settings are considered.

### Single-Year Evaluation

Models are optimized, trained, and evaluated using data from the same collection year.

Experiments are conducted independently for:

- Year2021
- Year2022

### Cross-Year Evaluation

Cross-year experiments evaluate model generalization between different data collection years.

The following directions are considered:

- Year2021 → Year2022
- Year2022 → Year2021

## Dataset

The experiments use the **2SeasonWeedDet8** weed detection dataset.

The dataset is available from Zenodo:

https://doi.org/10.5281/zenodo.10762138

The dataset is not included directly in this repository because of its size.

Users should download the dataset separately and update the dataset paths in the corresponding notebooks.

## Installation

Clone this repository:

```bash
git clone https://github.com/bala-221/AF-MCSO-YOLOv8-HPO.git
cd AF-MCSO-YOLOv8-HPO
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Running the Experiments

Each method contains two Jupyter notebooks:

- `*_single_year.ipynb` for single-year experiments
- `*_cross_year.ipynb` for cross-year experiments

To reproduce an experiment:

1. Download and prepare the dataset.
2. Install the required dependencies.
3. Open the corresponding Jupyter notebook.
4. Update the dataset path in the configuration section.
5. Run the notebook cells sequentially from top to bottom.

Method-specific information is provided in the README inside each experiment directory.

## Evaluation Metrics

Model performance is evaluated using:

- Precision
- Recall
- mAP@50
- mAP@50:95

Computational time and the selected hyperparameter configurations are also reported for the HPO experiments.

## Hyperparameter Optimization

Random Search, Hyperband, DEHB, and AF-MCSO are evaluated using the same YOLOv8m hyperparameter search space.

Candidate configurations are ranked using a composite fitness criterion based on:

- mAP@50:95
- Recall
- Mean mAP@50:95 of the three least-performing classes

Multi-fidelity evaluations use different training budgets to reduce the computational cost of hyperparameter optimization.

## Reproducibility

The notebooks provided in this repository correspond to the experimental procedures used in the associated study.

Experimental settings, random seeds, dataset splits, search spaces, training budgets, and evaluation procedures are provided in the notebooks to support reproducibility.

## Citation

If you use this repository or its implementation in your research, please cite the associated paper.

The complete citation will be added following publication.

## Authors

... et al.

## Acknowledgements

The authors gratefully recognize the institutional support provided by Abu Dhabi University and Monash University Malaysia.

## License

Please refer to the repository license for terms of use.
