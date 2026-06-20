# One-Hot Encoding & ColumnTransformer in scikit-learn

A hands-on notebook covering categorical feature encoding for machine learning, using a used-car listings dataset as the running example.

## What's covered

- One-hot encoding with `pandas.get_dummies`
- The k-1 dummy variable trick (`drop_first=True`) and why it avoids multicollinearity
- One-hot encoding with scikit-learn's `OneHotEncoder`, including the correct `fit` (train) / `transform` (test) split to avoid data leakage
- Handling high-cardinality categorical columns by grouping rare categories into an "uncommon" bucket
- Combining everything into a single, pipeline-friendly step with `ColumnTransformer`

## Dataset

This notebook expects a `cars.csv` file in the same directory, containing used car listings with columns including `brand`, `km_driven`, `fuel`, `owner`, and a target column such as `selling_price`. Add your own copy of the dataset before running, or update the loading cell to point to your data source. (If you found this dataset on Kaggle or elsewhere, consider linking the original source here instead of redistributing the file, depending on its license.)

## Requirements

```
pandas
numpy
scikit-learn
```

Install with:

```
pip install pandas numpy scikit-learn
```

## Usage

Open `onehot-encoding-and-columntransformer.ipynb` in Jupyter or VS Code and run the cells top to bottom.

## Notes

This was a learning exercise — feedback and suggestions are welcome.
