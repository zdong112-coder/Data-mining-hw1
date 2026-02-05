# Titanic Survival Prediction – Feature Engineering Revision

## Overview
This project revises the feature engineering pipeline of a standard Titanic survival prediction model to study how different feature representations affect model behavior and overfitting.

---

## Feature Engineering Changes

Compared to the original tutorial-style pipeline, the following modifications were made:

- **One-hot encoding** for categorical features (`Embarked`, `Deck`, `TicketPrefix`)  
  → removes artificial ordinal relationships.
- **Continuous representation of `Age`** instead of age band discretization.
- **Explicit missing-value indicators** (`AgeMissing`, `CabinMissing`).
- **Richer feature set**, including `TicketGroupSize` and `Deck`, increasing feature dimensionality.

---

## Model Performance (Training Accuracy)

| Model | Accuracy (%) |
|---|---|
| Random Forest | 97.76 |
| Decision Tree | 97.76 |
| KNN | 88.44 |
| Linear SVC | 83.05 |
| Logistic Regression | 83.05 |

---

## Analysis

- **KNN and SVM-based models improve** under the revised pipeline, indicating that the new feature representation better preserves meaningful geometric relationships.
- **Tree-based models overfit** the training data due to high feature dimensionality and lack of complexity constraints.
- High training accuracy for Decision Tree and Random Forest reflects memorization rather than improved generalization.

---

## Conclusion

The revised feature engineering strategy produces a more principled and expressive feature space.  
While it benefits distance- and margin-based models, it also increases overfitting risk for high-capacity tree models when evaluated on the training set.  
Proper regularization or cross-validation is required for fair generalization assessment.
