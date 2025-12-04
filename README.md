# OkCupid Matchability Prediction

## Overview

This project explores which OkCupid profile features are associated with higher "matchability" by training 3 tree-based models in R.  
The goal is to compare a simple decision tree with bagging and random forests, and see which user attributes matter most.

All analysis is done in the R Markdown file attached, which loads the data, performs preprocessing, trains the models, and produces the figures.

## Dataset

The project uses an anonymised OkCupid profiles dataset from Kaggle that includes:

- Demographics (age, sex, orientation, height)
- Lifestyle and background (education, religion, alcohol, drugs, etc.)
- Profile structure (which essays are filled in, basic profile fields)

The true number of matches is not available, so a proxy **"matchability" label** is engineered from profile completeness and effort.

> Note: The master dataset in one file wouldn't upload in one go due to its size, so i split it up into 6 different files but the data is all the same.

## Prerequisites

Install the main packages used:

```r
install.packages(c(
  "tidyverse", "tidymodels",
  "rpart", "rpart.plot",
  "ipred", "randomForest",
  "vip", "pdp"
))
```
## Methods

The analysis compares:
1. Decision tree (CART) using rpart
2. Bagging using ipred::bagging
3. Random forest using randomForest

Models are evaluated using a train/test split and metrics such as accuracy and ROC and AUC.

Variable importance and partial dependence plots are used to interpret which features drive the "matchability" label.

For full details, see the slide deck and the knitted report included in this repository.

## License 
This project is released under the MIT License.
