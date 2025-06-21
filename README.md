# Statistical Learning on Gapminder Dataset

## Overview
This project applies a range of statistical learning techniques to the Gapminder dataset to study and predict life expectancy trends across countries. The dataset includes GDP per capita, population, and life expectancy data from 1952 to 2007 for 142 countries. The goal is to analyze relationships between these variables and evaluate the performance of various models in predicting life expectancy.

## Features
- Exploratory Data Analysis using ggplot2, correlation plots, and histograms.
- Simple linear regression to model GDP vs. life expectancy globally.
- Country-specific prediction (India) using:
  - Linear Regression
	- Decision Trees
	- Ridge Regression
	- Lasso Regression
- Feature selection via correlation matrix.
- Model performance evaluated using:
  - R-squared
	- RMSE
  - MAE
	- MAPE
- Cross-validation for generalized model accuracy.

## Installation
To run the Gapminder project, R and the following libraries must be installed:
```
install.packages(c("gapminder", "dplyr", "ggplot2", "rpart", "glmnet"))
```
For RStudio users, clone or download the .Rmd or .R files and open the script.

## Usage
This project is structured to perform both global and country-level prediction tasks.

### Data Preparation
The dataset is loaded using the gapminder package. It includes 1,704 observations and 6 variables:
- **country**: Country name
- **continent**: Continent the country belongs to
- **year**: Time period (1952–2007)
- **lifeExp**: Life expectancy
- **pop**: Population
- **gdpPercap**: GDP per capita

```
library(gapminder)
data(gapminder)
str(gapminder)
```
## Running the Code
You can run each model independently by section:
1. Linear regression using lm() to predict life expectancy globally.
2. Subsetting India data, calculating average life expectancy.
3. Feature engineering for avg_lifeExp and model input setup.
4. Implementing:
   - Linear Regression
	 - Decision Tree (rpart)
	 - Ridge and Lasso Regression (glmnet)
5. 5-Fold cross-validation using manual fold splitting.
6. Plotting predicted vs. actual life expectancy.

## Models
**Approach 1**: Global Linear Regression
Predicts life expectancy using GDP per capita:
```
model <- lm(lifeExp ~ gdpPercap, data = train)
```
	- Accuracy: ~85.99%
	- R²: 0.34

**Approach 2**: Country-Specific Predictions (India)
Predicts life expectancy using features:
	- year, pop, gdpPercap, avg_lifeExp

Models used:
	- Linear Regression
	- Decision Tree
	- Ridge Regression
	- Lasso Regression

Cross-Validation
	- 5-fold CV implemented for both models
	- Evaluated on RMSE and R²

 ## Evaluation Metrics 
 
| Model             | R² (Mean) | RMSE (Average) |
|------------------|-----------|----------------|
| Linear Regression | 0.2986    | ~10.7          |
| Decision Tree     | 0.2986    | ~7.9           |

 ## Visualizations
The following plots help interpret model results:
- **Life Expectancy Distribution**: Histogram and boxplots by continent
- **GDP vs. Life Expectancy**: Global scatterplot
- **Trend Over Time**: Life expectancy vs. year colored by continent
- **Predicted vs. Actual**: For both Linear and Tree models

## Custom Functions
The analysis makes use of utility code snippets for:
- Manual 5-fold cross-validation
- Feature filtering by correlation
- Model evaluation metrics
- Plotting helper functions

## Key Learnings
- GDP per capita has a strong linear relationship with life expectancy.
- Simple linear models can give high interpretability but limited prediction accuracy.
- Cross-validation provides better generalization insights than a single test/train split.
- Decision trees performed better in terms of RMSE compared to linear regression.
- Ridge and Lasso helped in regularizing and selecting important predictors.

## Contributing
Feel free to fork the repository and contribute enhancements.
1. Fork the repo
2. Create your feature branch (git checkout -b feature/fooBar)
3. Commit your changes (git commit -am 'Add new feature')
4. Push to the branch (git push origin feature/fooBar)
5. Create a new Pull Request

## Contact
**Project Owner**: Priyanka Vyas
**Email**: vpriyanka.sv@gmail.com

## Acknowledgments
This project was developed as part of the Statistical Learning course. Special thanks to:
- Gapminder Foundation
- R packages: ggplot2, dplyr, rpart, glmnet, and gapminder
