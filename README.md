# COVID-19 Dataset Classification Using Machine Learning Algorithms

This project focuses on analyzing a dataset of COVID-19 cases across 51 US states for January 2021 and applying various machine learning classification algorithms to predict daily increases in confirmed cases, deaths, and recoveries.

### Table of Contents

Project Overview
Dataset Description
Installation and Setup
Data Preprocessing
Dimensionality Reduction
Classification Models
Results and Analysis
Project Structure
Conclusion
References

### Project Overview

The goal of this project is to analyze the DKMA-COVID19-Jan-States dataset, clean and preprocess the data, and apply various machine learning algorithms to predict daily increases in COVID-19 statistics (confirmed cases, deaths, and recoveries). The classifiers used include Naive Bayes, Decision Tree, Random Forest, and Gradient Boosting, along with feature reduction techniques such as Principal Component Analysis (PCA) and Linear Discriminant Analysis (LDA).

### Dataset Description

The dataset contains statistics related to COVID-19 cases across US states for each day in January 2021, sourced from:

[John Hopkins University CSSE COVID-19](https://github.com/CSSEGISandData/COVID-19)
[US 2020 Census](https://www.census.gov)

The dataset features include:

- Day: Date (ranging from Jan 2 to Jan 31, 2021)
- State ID: Arbitrary state identifier
- State: Name of the US state
- Active Cases: Number of active COVID-19 cases on the specified date
- Incident Rate, Total Test Results, Case Fatality Ratio, Testing Rate: Additional statistics from the original dataset
- Resident Population, Population Density, Density Rank, Sex Ratio: Census data on state populations
- Three binary labels indicating increases in Confirmed Cases, Deaths, and Recoveries on each day.

### Main Libraries Used
- Pandas: For data manipulation and preprocessing
- Scikit-learn: For machine learning algorithms
- Matplotlib/Seaborn: For visualization
- Numpy: For numerical operations

### Data Preprocessing

Steps Taken:
<br>
1. Data Cleaning: Handled inconsistent number formats and normalized certain features like Incident Rate, Testing Rate, and Population Density.
2. Handling Outliers: Considered potential outliers due to variations in COVID-19 case numbers across states.
3. Feature Engineering: Categorical features such as State, Day, and State ID were excluded from model training, focusing only on numerical attributes.

### Dimensionality Reduction

PCA and LDA were applied for feature reduction:

- PCA: A scree-plot was used to analyze the cumulative variance, and optimal features were selected based on the analysis.
- LDA: Used the labels (Confirmed Cases, Deaths, Recoveries) to perform linear discriminant analysis, visualizing the results on a 2D plane.

### Classification Models

The following models were applied to the dataset, with hyperparameter tuning using k-fold cross-validation:

1. Decision Trees:
- Tuned parameters: Maximum depth, splitting criteria
- Evaluated mean accuracy for different depth levels
2. Random Forests:
- Tuned parameters: Number of trees, maximum depth
- Visualized results with a heatmap of accuracy vs. parameter combinations
3. Gradient Boosting:
- Tuned parameters: Number of estimators (trees)
- Plotted mean accuracy vs. number of estimators
4. Naive Bayes:
- Tuned the variance smoothing parameter and compared results with tree-based models

### Performance Metrics:
- Accuracy
- F1-score
- Precision and Recall

### Results and Analysis

- Decision Tree Classifier: Optimal depth produced meaningful splitting rules, highlighting significant features for predicting daily increases.
- Random Forest: Achieved high accuracy with moderate tree depth and number of trees, with PCA and LDA features improving overall model performance.
- Gradient Boosting: Produced the highest accuracy when the number of estimators was tuned.
- Naive Bayes: Effective for binary classification, but slightly underperformed compared to tree-based methods.

### Conclusion

This project demonstrates the application of various machine learning classifiers to a real-world dataset, highlighting the importance of data preprocessing and model tuning. It also emphasizes how dimensionality reduction techniques like PCA and LDA can enhance model performance.
  
