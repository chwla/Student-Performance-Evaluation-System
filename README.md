# Student-Performance-Evaluation-System

This project is designed to predict student scores in comprehensive exams using machine learning and to provide targeted academic suggestions based on those predictions. The system aims to help identify students who may need additional support and direct them to specific study topics.

Project Goals
Predict comprehensive exam scores using data from prior assessments (tutorials, mid-semester, practical tests).

Automatically suggest study topics for students predicted to underperform, enabling more personalized academic support.

Approach
Data and Feature Engineering
The dataset includes scores from various assessments in the course "Mechanical Oscillations and Waves."

Additional features are engineered, such as:

Average tutorial score

Total pre-comprehensive score

Standard deviation of tutorial scores

Data normalization is applied using StandardScaler to stabilize model training.

Model Development
Two main models were explored:

Deep Neural Network (DNN):

Implemented with dropout, batch normalization, and early stopping.

Despite these measures, the DNN struggled due to high error rates and instability with the given data.

XGBoost Regression:

Provided much lower mean absolute error (MAE ≈ 10.17) and mean squared error (MSE ≈ 168).

Became the primary model for predictions and generating recommendations.

Academic Suggestions
A function automatically identifies students whose predicted scores fall below a certain threshold (e.g., class average).

For each flagged student, the system examines tutorial test scores to find the weakest topic and suggests targeted study material for that area.

How to Use
Install Dependencies

bash
pip install pandas numpy scikit-learn matplotlib xgboost tensorflow
Run the Jupyter Notebook

Open assignment_ai.ipynb in Jupyter Notebook.

Execute the cells in order to:

Load and preprocess the data

Train and evaluate models

Generate predictions and study suggestions

Customize Suggestions

Adjust the performance threshold in the provide_study_suggestions() function to change sensitivity for flagging students.

File Structure
File Name	Description
assignment_ai.ipynb	Main notebook with code and analysis
dataset1.csv / dataset2.csv	Student score datasets (anonymized)
Results
The XGBoost model significantly outperformed the DNN, providing more reliable predictions and actionable academic advice.

The system can be adapted for other courses or datasets with similar structure.
