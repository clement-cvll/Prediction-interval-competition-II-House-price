# Prediction Interval Competition II: House Price

This repository contains my participation in the [Prediction Interval Competition II: House Price](https://www.kaggle.com/competitions/prediction-interval-competition-ii-house-price) on Kaggle.

## Competition Overview

The objective is to build models that predict **intervals** (not just point estimates) for house prices. Each prediction should provide a lower and upper bound (for example, the 5th and 95th percentiles) to capture uncertainty.

## Data

- **Train data:** `data/train.csv`
- **Test data:** `data/test.csv`
- **Sample submission:** `data/sample_submission.csv`

## Submission Format

Your submission should include:
- `pi_lower`: Lower bound of the prediction interval (e.g., 5th percentile)
- `pi_upper`: Upper bound of the prediction interval (e.g., 95th percentile)

## Usage

1. Install requirements from `pyproject.toml`.
2. Run `1-autogluon.ipynb` to train models and generate predictions.
3. The notebook will output a `submission.csv` file in the required format.

## Evaluation

Submissions are evaluated using the **mean Winkler Interval score**. For an individual interval, the Winkler score is:

> Winkler Score = (u - l) <br>
>      + (2 / alpha) * (l - y), if y < l <br>
>      + (2 / alpha) * (y - u), if y > u

where:
- `y` is the true value
- `l` is the lower prediction interval
- `u` is the upper prediction interval
- `alpha = 0.1` (for 90% coverage)

The aim is a **nominal marginal coverage of 90%**, meaning 90% of the prediction intervals should contain the true value.


## References

- [Kaggle Competition Page](https://www.kaggle.com/competitions/prediction-interval-competition-ii-house-price)
- [Autogluon Documentation](https://auto.gluon.ai/stable/index.html)
