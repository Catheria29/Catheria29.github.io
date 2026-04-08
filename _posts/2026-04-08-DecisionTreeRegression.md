# Understanding Decision Tree Regression

## Overview
A **Decision Tree Regressor** is a machine learning model that predicts continuous numerical values, such as prices, temperatures, or salaries. It works by learning simple decision rules from data features to build a flowchart-like tree structure[cite: 2, 3].

Think of it as a series of "yes-or-no" questions for your data[cite: 4]. [cite_start]Each answer narrows down the possibilities—much like the game "20 Questions"—until a final numeric prediction is reached[cite: 5, 6].

## Tree Anatomy
Every decision tree consists of four essential components:

* **Root Node**: The very first decision point at the top which asks the most critical question to split the data[cite: 8].
* **Decision Nodes**: Internal nodes that appear after the root and further split data based on other features[cite: 9, 10].
* **Branches**: The paths connecting nodes, representing the "True/False" or "Yes/No" answers[cite: 11].
* **Leaves (Terminal Nodes)**: The final nodes at the bottom that contain the actual predicted value[cite: 12, 13]. [cite_start]For regression, this is the average of training examples in that leaf[cite: 14].

---

## Practical Application: House Price Prediction

![House Price Decision Tree](assets/DecisionTreeRegressor.png)

[cite_start]Based on the visualization above, here is how the regressor determines a house price[cite: 16, 20, 29]:

| Bedrooms | Lot Size | Predicted Price |
| :--- | :--- | :--- |
| $\le 2$ | $\le 790$ $m^2$ | [cite_start]**₺6,300,000**  |
| $\le 2$ | $> 790$ $m^2$ | [cite_start]**₺8,100,000**  |
| $> 2$ | $\le 1070$ $m^2$ | [cite_start]**₺7,300,000**  |
| $> 2$ | $> 1070$ $m^2$ | [cite_start]**₺10,200,000**  |

---

## Hyperparameter Tuning & Optimization
To prevent **underfitting** or **overfitting**, we use hyperparameters to control growth:

* **Maximum Depth**: Limits how many levels the tree can grow[cite: 47].
* **Minimum Samples Split**: The smallest number of samples a node must have before the algorithm considers splitting it.
* **Minimum Samples Leaf**: The smallest number of samples allowed in any leaf node.
* **Max Features**: Limits the number of features considered when searching for the best split at each node.
* **Criterion**: The mathematical formula (e.g., `squared_error`) used to evaluate the quality of a split.

## Implementation
```python
from sklearn.tree import DecisionTreeRegressor

# Initializing the model with specific constraints 
regressor = DecisionTreeRegressor(
    max_depth=5,
    min_samples_split=10,
    min_samples_leaf=5,
    max_features=None,
    criterion='squared_error',
    random_state=42
)
