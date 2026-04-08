
# Understanding Decision Tree Regression

## Overview
[cite_start]A **Decision Tree Regressor** is a machine learning model that predicts continuous numerical values, such as prices, temperatures, or salaries[cite: 2]. [cite_start]It works by learning simple decision rules from data features to build a flowchart-like tree structure[cite: 2, 3]. 

[cite_start]Think of it as a series of "yes-or-no" questions for your data[cite: 4]. [cite_start]Each answer narrows down the possibilities—much like the game "20 Questions"—until a final numeric prediction is reached[cite: 5, 6].

## Tree Anatomy
[cite_start]Every decision tree consists of four essential components[cite: 7]:

* [cite_start]**Root Node**: The very first decision point at the top which asks the most critical question to split the data[cite: 8].
* [cite_start]**Decision Nodes**: Internal nodes that appear after the root and further split data based on other features[cite: 9, 10].
* [cite_start]**Branches**: The paths connecting nodes, representing the "True/False" or "Yes/No" answers[cite: 11].
* [cite_start]**Leaves (Terminal Nodes)**: The final nodes at the bottom that contain the actual predicted value[cite: 12, 13]. [cite_start]For regression, this is the average of training examples in that leaf[cite: 14].

---

## Practical Application: House Price Prediction

![House Price Decision Tree](assets/images/Gemini_Generated_Image_ex7lbcex7lbcex7l.png)

[cite_start]Based on the visualization above, here is how the regressor determines a house price[cite: 16, 20, 29]:

| Features | Logic Path | Predicted Price |
| :--- | :--- | :--- |
| **Bedrooms $\le 2$** | Lot Size $\le 790$ $m^2$ | [cite_start]**₺6,300,000** [cite: 23] |
| **Bedrooms $\le 2$** | Lot Size $> 790$ $m^2$ | [cite_start]**₺8,100,000** [cite: 28] |
| **Bedrooms $> 2$** | Lot Size $\le 1070$ $m^2$ | [cite_start]**₺7,300,000** [cite: 31] |
| **Bedrooms $> 2$** | Lot Size $> 1070$ $m^2$ | [cite_start]**₺10,200,000** [cite: 33] |

---

## Hyperparameter Tuning & Optimization
[cite_start]To prevent **underfitting** (tree is too shallow) or **overfitting** (tree is too deep), we use hyperparameters to control growth[cite: 45, 49]:

* [cite_start]**Maximum Depth**: Limits how many levels the tree can grow[cite: 47].
* [cite_start]**Minimum Samples Split**: The smallest number of samples a node must have before the algorithm considers splitting it further[cite: 51].
* [cite_start]**Minimum Samples Leaf**: The smallest number of samples allowed in any leaf node[cite: 54].
* [cite_start]**Max Features**: Limits the number of features considered when searching for the best split at each node[cite: 56].
* [cite_start]**Criterion**: The mathematical formula (e.g., `squared_error`) used to evaluate how "good" a potential split is[cite: 58, 65].

## Implementation (Python/Scikit-Learn)
```python
from sklearn.tree import DecisionTreeRegressor

# Initializing the model with specific constraints
regressor = DecisionTreeRegressor(
    max_depth=5,              # [cite: 61]
    min_samples_split=10,     # [cite: 62]
    min_samples_leaf=5,       # [cite: 63]
    max_features=None,        # [cite: 64]
    criterion='squared_error',# [cite: 65]
    random_state=42           # [cite: 66]
)
