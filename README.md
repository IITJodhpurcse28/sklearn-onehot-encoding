# Categorical Encoding with scikit-learn

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange.svg)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-F37626.svg)](https://jupyter.org/)

A hands-on notebook on encoding categorical features for machine learning, using a used-car listings dataset as the running example. Built while learning how `pandas` and `scikit-learn` approach the same problem differently, and why that difference matters once you bring a train/test split into the picture.

## Table of contents

- [What's covered](#whats-covered)
- [Dataset](#dataset)
- [Project structure](#project-structure)
- [Requirements](#requirements)
- [Usage](#usage)
- [Key takeaways](#key-takeaways)
- [Notes](#notes)

## What's covered

| Topic | Why it matters |
|---|---|
| One-hot encoding with `pandas.get_dummies` | Fast for exploration, but no `fit`/`transform` split |
| k-1 encoding (`drop_first=True`) | Avoids multicollinearity between dummy columns for linear models |
| `sklearn.preprocessing.OneHotEncoder` | Learns categories from training data only, then applies the same encoding to test data — no data leakage |
| Grouping rare categories | Prevents high-cardinality columns (like `brand`) from exploding into hundreds of sparse columns |
| `sklearn.compose.ColumnTransformer` | Applies different transformations to different columns in a single, pipeline-ready step |

## Dataset

This notebook expects a `cars.csv` file in the same directory, containing used car listings with columns including `brand`, `km_driven`, `fuel`, `owner`, and a target column such as `selling_price`.

Add your own copy of the dataset before running, or update the loading cell to point to your data source. If you sourced this dataset from Kaggle or elsewhere, consider linking the original source here instead of redistributing the file, depending on its license.

## Project structure

```
.
├── onehot-encoding-and-columntransformer.ipynb   # main notebook
├── cars.csv                                      # dataset (add your own)
└── README.md
```

## Requirements

```
pandas
numpy
scikit-learn
jupyter
```

Install with:

```bash
pip install pandas numpy scikit-learn jupyter
```

## Usage

```bash
jupyter notebook onehot-encoding-and-columntransformer.ipynb
```

Run the cells top to bottom. Each section is preceded by a short explanation of what's being done and why.

## Key takeaways

- `pd.get_dummies` is quick for exploration but can't guarantee train and test sets get encoded consistently.
- `OneHotEncoder` fixes that: fit on train, transform on train and test.
- Use `drop='first'` (k-1 encoding) to avoid multicollinearity for linear models.
- For high-cardinality columns, group rare categories together before encoding.
- `ColumnTransformer` bundles multiple column-specific transformations into one pipeline-friendly object instead of manual array stitching.

## Notes

This started as a personal learning exercise, so feedback, corrections, and suggestions are very welcome — feel free to open an issue or a pull request.
