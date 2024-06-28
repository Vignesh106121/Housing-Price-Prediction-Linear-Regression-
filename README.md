HOUSING PRICE PREDICTION USING LINEAR REGRESSION

Linear Regression:

Linear regression is a statistical method used to model the relationship between a dependent variable (target variable) and one or more independent variables (predictor variables). It assumes a linear relationship between the variables, meaning the change in the dependent variable is directly proportional to changes in the independent variables.

Here’s a step-by-step explanation of what I've done in this analysis and modeling process for housing price prediction:

Importing Libraries:

Imported necessary libraries such as numpy, pandas for data manipulation, and matplotlib and seaborn for visualization.

Loading the Dataset:

Loaded the housing dataset from a URL into a DataFrame named housing.

Initial Data Exploration:

Displayed the first few rows of the dataset using head().
Checked the shape of the dataset using shape.
Used info() to understand the data types and non-null counts.
Generated descriptive statistics using describe().

Checking for Missing Values:

Calculated the percentage of missing values for each column using isnull().sum().

Outlier Analysis:

Created boxplots for various columns to identify outliers.
Applied outlier treatment to the price and area columns by calculating the interquartile range (IQR) and removing data points outside the range of [Q1 - 1.5 * IQR, Q3 + 1.5 * IQR].

Visualization:

Re-plotted the boxplots for various columns to ensure outliers were treated.
Used pairplot to visualize relationships between different features.
Created boxplots to examine the impact of categorical features (mainroad, guestroom, basement, hotwaterheating, airconditioning, furnishingstatus) on price.

Encoding Categorical Variables:

Converted binary categorical variables (mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea) into numerical format using a mapping function.
Created dummy variables for furnishingstatus and added them to the DataFrame, dropping the original furnishingstatus column.

Splitting Data into Training and Test Sets:

Split the dataset into training (70%) and testing (30%) sets using train_test_split.

Scaling Numerical Features:

Applied MinMax scaling to numerical features in the training set.

Correlation Analysis:

Plotted a heatmap to visualize the correlation between features in the training set.

Feature Selection using RFE:

Applied Recursive Feature Elimination (RFE) with Linear Regression to select the top 6 features.
Extracted the selected features and created a new training set (X_train_rfe).

Building the Model:

Built an Ordinary Least Squares (OLS) regression model using statsmodels.
Evaluated the model using the summary statistics provided by statsmodels.

Variance Inflation Factor (VIF) Calculation:

Calculated VIF to check for multicollinearity among the selected features.

Model Diagnostics:

Plotted the distribution of residuals (errors) to check for normality.
Created a scatter plot of residuals to check for any patterns.

Preparing Test Data:

Scaled the numerical features in the test set.
Predicted the prices for the test set using the trained model.
Calculated the R-squared value for the test set predictions.

Evaluation:

Plotted a scatter plot comparing actual prices (y_test) and predicted prices (y_pred) to visually assess the model's performance.
