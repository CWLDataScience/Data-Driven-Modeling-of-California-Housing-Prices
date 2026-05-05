# Data-Driven-Modeling-of-California-Housing-Prices
Got it — here’s a cleaner, more natural version without emojis or “trying too hard” tone. This reads like a real person wrote it, not a template.

---

# California Housing Price Prediction

## Overview

This project analyzes the main factors that influence housing prices in California and builds a machine learning model to predict `median_house_value` using geographic and demographic data.

The objective is to provide a more data-driven way to understand housing prices rather than relying purely on intuition.

---

## Objectives

* Build a regression model to predict housing prices
* Identify the key drivers behind property value
* Translate model results into practical insights

---

## Business Context

**Real Estate Investors**
The model can be used as a baseline to compare predicted prices with actual values. Properties where the actual price is higher than the predicted value may indicate undervaluation, which could represent investment opportunities.

**Urban Planners**
The analysis helps explain how income distribution, population density, and location affect housing prices, which can support planning and development decisions.

**Mortgage Lenders**
The model provides an additional reference point for estimating property value and assessing lending risk across different regions.

---

## Key Findings

Median income is the strongest predictor of housing prices, indicating that purchasing power plays a central role in determining property value. Location-related features, such as latitude, longitude, and proximity to the ocean, also contribute significantly, showing that geography has a strong influence on price patterns. In contrast, structural housing characteristics such as the number of rooms or house age have a relatively smaller impact.

The model performs reasonably well overall, but prediction errors tend to be larger for mid-range priced houses, suggesting uneven performance across price segments. There is no clear geographic pattern in the residuals, which indicates that location-based effects are largely captured by the model.

---

## Methodology

### Data Preparation

* Removed capped house values to reduce distortion
* Renamed columns to reflect that the data is aggregated at the block level
* Performed a stratified train-test split based on income distribution

### Feature Engineering

* Created ratio-based features (e.g., rooms per household, people per household)
* Applied log transformations to handle skewed distributions
* Used clustering on geographic coordinates to capture location similarity
* Encoded categorical variables using one-hot encoding

### Models Evaluated

* Linear Regression
* Ridge Regression
* Decision Tree
* Random Forest
* Gradient Boosting

Random Forest produced the best performance among the tested models.

---

## Model Performance

The final model achieved a test RMSE of approximately 40,500, indicating a reasonable level of prediction accuracy given the limitations of the dataset.

---

## Feature Importance

Permutation importance shows that income-related features dominate the model’s predictions, followed by geographic variables. Population and household-related features have moderate influence, while housing structure variables contribute less.

It is important to note that these results reflect how the model uses features, not direct causal relationships.

---

## Additional Analysis

Residual analysis shows that errors are generally centered around zero, meaning the model is not heavily biased. However, the error spread is larger in mid-priced properties, indicating less stability in that range.

Mapping prediction errors geographically does not reveal a strong spatial pattern, suggesting that most location-based effects have already been captured by the model.

---

## Limitations

* The dataset includes capped values, which affect high-end predictions
* Important external factors such as economic conditions and local amenities are not included
* Feature importance does not imply causation
* Model performance varies across price ranges
* Hyperparameter tuning was not fully explored due to time constraints
* There may be minor analysis imperfections

---

## Tech Stack

* Python (NumPy, Pandas)
* Matplotlib, Seaborn, GeoPandas, GeoPlot
* Scikit-learn

---

## Notes

The dataset represents aggregated data at the block level rather than individual houses. Column names were adjusted to better reflect this after initial exploration.

---

* tighten it further to one-page (for recruiters who skim)
* or help you write the Kaggle version (slightly different tone)
