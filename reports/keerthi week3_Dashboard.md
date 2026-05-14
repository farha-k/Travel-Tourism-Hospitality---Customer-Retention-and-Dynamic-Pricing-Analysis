# Week 3: Baseline Predictive Modeling (Churn Prediction)

## Objective
The objective of this phase is to build a baseline machine learning model to predict whether a hotel booking is likely to be canceled.

This predictive analysis helps hotel management:
- Identify high-risk bookings
- Improve customer retention strategies
- Reduce revenue loss caused by cancellations
- Support future dynamic pricing systems

The target variable used in this analysis is:

```python
is_canceled
```

- 0 = Booking Not Canceled
- 1 = Booking Canceled

---

# Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

Machine Learning Libraries:
- Scikit-Learn
- Logistic Regression
- Decision Tree Classifier

---

# Data Preprocessing

## Handling Missing Values
Missing values were removed using:

```python
df = df.dropna()
```

## Feature Selection

Input features were selected by removing:
- is_canceled
- reservation_status
- reservation_status_date

```python
X = df.drop(columns=[
    'is_canceled',
    'reservation_status',
    'reservation_status_date'
])
```

Target Variable:

```python
y = df['is_canceled']
```

---

# Encoding Categorical Variables

Categorical columns were converted into numerical values using Label Encoding.

```python
from sklearn.preprocessing import LabelEncoder
```

Purpose:
- Machine learning models require numerical input
- Encoding converts text data into numeric format

---

# Splitting Dataset

The dataset was divided into:
- 80% Training Data
- 20% Testing Data

```python
from sklearn.model_selection import train_test_split
```

Purpose:
- Training data is used to train the model
- Testing data is used to evaluate model performance

---

# Logistic Regression Model

## Objective
Logistic Regression was implemented as a baseline classification model for predicting booking cancellations.

```python
from sklearn.linear_model import LogisticRegression
```

## Model Training

```python
lr_model = LogisticRegression(max_iter=5000)

lr_model.fit(X_train, y_train)
```

---

# Predictions

```python
y_pred = lr_model.predict(X_test)

y_prob = lr_model.predict_proba(X_test)[:,1]
```

---

# Evaluation Metrics

## Accuracy
Accuracy measures the percentage of correctly predicted observations.

## Precision
Precision measures how many predicted cancellations were actually canceled bookings.

## Recall
Recall measures how effectively the model identifies actual canceled bookings.

## ROC-AUC Score
ROC-AUC evaluates the model’s ability to distinguish between canceled and non-canceled bookings.

---

# Confusion Matrix

The confusion matrix visualizes:
- True Positives
- True Negatives
- False Positives
- False Negatives

A heatmap visualization was created using Seaborn.

---

# ROC Curve

The ROC Curve visualizes:
- True Positive Rate
- False Positive Rate

The closer the curve is to the top-left corner, the better the model performance.

---

# Decision Tree Model

## Objective
A Decision Tree Classifier was implemented to compare performance with Logistic Regression.

```python
from sklearn.tree import DecisionTreeClassifier
```

## Model Training

```python
dt_model = DecisionTreeClassifier(
    max_depth=5,
    random_state=42
)

dt_model.fit(X_train, y_train)
```

---

# Decision Tree Evaluation

The following metrics were evaluated:
- Accuracy
- Precision
- Recall
- Classification Report
- Confusion Matrix
- ROC Curve

---

# Key Insights

- Machine learning models successfully predicted booking cancellations
- Logistic Regression provided stable baseline performance
- Decision Tree provided better interpretability
- Lead time and booking details strongly influence cancellation probability
- Predictive modeling can help hotels reduce cancellations and improve customer retention

---

# Outcome

Successfully developed baseline machine learning models for hotel booking cancellation prediction using:
- Logistic Regression
- Decision Tree Classifier

The models were evaluated using multiple performance metrics and visualization techniques.

---

# Conclusion

This phase demonstrated how predictive analytics can be used in the hospitality industry to forecast booking cancellations. The developed machine learning models can support hotels in improving customer retention strategies, reducing revenue loss, and making better business decisions.
