# Neo_Hazard
Near-Earth Objects (NEO) Hazard Prediction Project
Overview
This project aims to analyze and predict whether a Near-Earth Object (NEO) is hazardous or not using various machine learning techniques. The dataset contains information about NEOs such as their estimated diameter, relative velocity, and miss distance. The primary objective is to build and evaluate different models that can accurately classify NEOs as hazardous or non-hazardous.

Data Source
The dataset used in this project is named nearest-earth-objects(1910-2024).csv. It contains various attributes related to NEOs, including:

absolute_magnitude: The absolute magnitude of the NEO.
estimated_diameter_min: The minimum estimated diameter of the NEO.
estimated_diameter_max: The maximum estimated diameter of the NEO.
relative_velocity: The velocity of the NEO relative to Earth.
miss_distance: The closest distance the NEO will come to Earth.
is_hazardous: A binary label indicating whether the NEO is hazardous (1) or not (0).
Steps and Methods
1. Data Preprocessing
Loading Data: The dataset was loaded using pandas.
Initial Exploration: The dataset was explored to understand its structure, missing values, and basic statistics.
Data Cleaning:
Columns neo_id and orbiting_body were dropped as they were not relevant to the prediction task.
Rows with missing values were removed to ensure a clean dataset for model training.
Duplicate rows were checked, but none were found.
Feature Engineering:
Categorical variables were handled, though the only categorical variable (orbiting_body) was dropped.
2. Data Visualization
Boxplots: Visualizations were created to identify outliers in features like absolute_magnitude, estimated_diameter_min, estimated_diameter_max, relative_velocity, and miss_distance.
Pie Chart: The distribution of hazardous vs. non-hazardous NEOs was visualized using a pie chart.
3. Model Training and Evaluation
Baseline Model (Decision Tree):

A Decision Tree Classifier was trained and evaluated on the original dataset.
Accuracy, confusion matrix, and classification report were used to evaluate the model.
The confusion matrix was visualized using a heatmap.
The decision tree was visualized to understand the decision-making process of the model.
Handling Imbalanced Data:

SMOTE (Synthetic Minority Over-sampling Technique):
SMOTE was used to oversample the minority class (hazardous NEOs).
A Decision Tree was trained on the resampled dataset.
The model's performance was evaluated and compared to the baseline model.
Random OverSampling:
Random over-sampling was applied to balance the dataset.
A Decision Tree was trained and evaluated similarly.
Random UnderSampling:
Random under-sampling was used to balance the dataset by reducing the majority class.
The model was trained and evaluated similarly.
Random Forest Model:

A Random Forest Classifier was trained on the original dataset.
Feature importance was assessed using the SelectFromModel method.
The most important features were selected for further analysis.
A single tree from the Random Forest was visualized to understand its decision-making process.
4. Model Comparison and Insights
Decision Tree:

Initially trained on the imbalanced dataset. The model showed decent accuracy, but it struggled with the imbalanced class distribution.
SMOTE and Random OverSampling improved the model's performance, with SMOTE providing the best results among the resampling methods.
Random Forest:

The Random Forest model provided better accuracy than the Decision Tree models and was more robust to the imbalanced class distribution.
Feature selection using the Random Forest model highlighted the most critical features for predicting hazardous NEOs.
5. Conclusion
Best Model: Although the oversampling techniques (especially SMOTE) yielded the highest accuracy, the Random Forest model was selected for future use due to its superior overall performance and robustness.
Future Work: Further tuning of the Random Forest model, exploration of additional features, and the application of more advanced ensemble methods could further enhance prediction accuracy.
6. Dependencies
Python 3.x
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Imbalanced-learn (for SMOTE and resampling techniques)
7. How to Run the Code
Ensure all dependencies are installed.
Load the dataset (nearest-earth-objects(1910-2024).csv).
Run the Jupyter notebook or Python script containing the above code.
Review the outputs, visualizations, and model performance metrics.
8. Insights
Outliers: Identified in features like relative_velocity and miss_distance, which can impact model performance.
Imbalanced Data: The dataset was highly imbalanced, necessitating the use of resampling techniques.
Feature Importance: Certain features, such as relative_velocity and miss_distance, were found to be more important for predicting hazardous NEOs.
9. References
Scikit-learn Documentation: https://scikit-learn.org/stable/
Imbalanced-learn Documentation: https://imbalanced-learn.org/stable/
Matplotlib Documentation: https://matplotlib.org/stable/
