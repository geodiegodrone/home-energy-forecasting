# Model Card: home-energy-forecasting

## Summary
Household appliance energy regression using sensor and calendar features.

## Intended use
Educational and portfolio demonstration. Outputs may support analysis but are not validated for automated high-impact decisions or production deployment.

## Data
Source: UCI Machine Learning Repository, DOI [https://doi.org/10.24432/C5VC8G](https://doi.org/10.24432/C5VC8G). The dataset is not redistributed here; download occurs at runtime from the UCI archive. UCI dataset license: CC BY 4.0. Cite UCI and review dataset terms before reuse.

## Evaluation
Chronological 80/20 holdout; compare training-mean baseline with HistGradientBoosting. Exclude rv1 and rv2.
See `src/train.py` for implementation. No benchmark results are claimed until the script has been run and independently reviewed.

## Tracking and artifacts
MLflow records run parameters, evaluation metrics, and model artifacts where applicable. Generated data, model files, reports, and local tracking runs are excluded from version control by `.gitignore`.

## Limitations
Historical public benchmark data may not represent current populations or deployment conditions. Validate data quality, temporal stability, subgroup performance, privacy, and operational costs before real-world use.

## Reproducibility
Install pinned dependencies from `requirements.txt` and run `python src/train.py`. The script downloads the dataset and creates local outputs. Set `MLFLOW_TRACKING_URI` to use a configured remote MLflow server.