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
    'reservation
