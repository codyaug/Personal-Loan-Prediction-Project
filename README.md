# Personal Loan Prediction Project

## Data Preprocessing

### Handling Duplicates
The dataset was checked for duplicates, and none were found, indicating clean data.

### Data Transformation
- The 'CCAvg' column was transformed to a float type by replacing '/' with '.'.
- 'Income' was divided by 12 to represent monthly income.
- 'Experience' was made non-negative.

### Feature Removal
The 'ID' column, being an identifier, was removed.

## Exploratory Data Analysis (EDA)
EDA was performed using pandas profiling, Plotly, and Seaborn to understand data distributions and correlations. Visualizations included histograms, box plots, and scatter plots.

## Feature Selection
- **Continuous Features:** 'Age', 'Income', 'Experience', 'CCAvg', and 'Mortgage' were selected for analysis due to their potential impact on loan acceptance.
- **Discrete Features:** 'Family', 'Education', 'Securities Account', 'CD Account', 'Online', and 'CreditCard' were selected for analysis as discrete categorical variables.

## Model Selection and Evaluation

### Logistic Regression
- **Normalization:** Features were normalized using StandardScaler.
- **Hyperparameter Tuning:** GridSearchCV was utilized to find optimal hyperparameters (C, penalty, solver).
- **Evaluation Metrics:** Accuracy score and F1 score were chosen as evaluation metrics.
- **Performance:** After GridSearchCV, the model achieved an accuracy score of 96% and an F1 score of 79.6%.

### Addressing Class Imbalance

#### SMOTE (Synthetic Minority Over-sampling Technique)
- To address class imbalance, SMOTE was applied, generating synthetic samples for the minority class.
- **Performance Improvement:** After addressing class imbalance, the final model achieved an accuracy score of 91.3% and an F1 score of 91.6%.

### Naive Bayes
- **Model:** Gaussian Naive Bayes classifier was implemented.
- **Performance:** The Naive Bayes model achieved an accuracy score of 85% and an F1 score of 85%.

### K-Nearest Neighbors (KNN)
- **Model:** KNN Classifier was utilized with GridSearchCV to find optimal hyperparameters (n_neighbors, weights, p).
- **Performance:** The KNN model achieved an accuracy score of 98.1% and an F1 score of 98.2%.

## Model Comparison and Visualization
- A bar plot was created to visually compare the accuracy scores of Logistic Regression, KNN, and Naive Bayes models.
- **Comparison:** The KNN model outperformed others in both accuracy and F1 score, making it the best choice for predicting personal loan acceptance in this dataset.

## Future Steps
- **Further Tuning:** Continuous improvement can be pursued by tuning hyperparameters further or exploring different algorithms.
- **Additional Features:** Exploring additional features or engineered features might enhance model performance.
- **Deployment:** Once satisfied with the model, it can be deployed for real-time predictions, possibly integrated into a web application or used via API endpoints.
- **Monitoring and Maintenance:** Continuous monitoring of the model's performance and periodic retraining will ensure it remains relevant and accurate over time.
