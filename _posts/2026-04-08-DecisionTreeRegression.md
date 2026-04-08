# Understanding Decision Tree Regression

## Overview
A **Decision Tree Regressor** is a machine learning model that predicts continuous numerical values, such as prices, temperatures, or salaries. It works by learning simple decision rules from data features to build a flowchart-like tree structure.

Think of it as a series of "yes-or-no" questions for your data.Each answer narrows down the possibilities much like the game "20 Questions"until a final numeric prediction is reached.

## Tree Anatomy
Every decision tree consists of four essential components:

* **Root Node**: The very first decision point at the top which asks the most critical question to split the data.
* **Decision Nodes**: Internal nodes that appear after the root and further split data based on other features.
* **Branches**: The paths connecting nodes, representing the "True/False" or "Yes/No" answers.
* **Leaves (Terminal Nodes)**: The final nodes at the bottom that contain the actual predicted value. For regression, this is the average of training examples in that leaf.

---

## Practical Application: House Price Prediction

![House Price Decision Tree](/assets/images/Gemini_Generated_Image_ex7lbcex7lbcex7l.png)

Based on the provided model, here is how a prediction is made:

    Root Question: Does the house have more than 2 bedrooms? 

    The "No" Path: If it has 2 or fewer bedrooms, the model asks: "Is the lot size larger than 790 m2?".

        No: Predicted Price = ₺6,300,000.

        Yes: Predicted Price = ₺8,100,000.

    The "Yes" Path: If it has more than 2 bedrooms, the model asks: "Is the lot size larger than 1070 m2?".

        No: Predicted Price = ₺7,300,000.

        Yes: Predicted Price = ₺10,200,000.
---

## Hyperparameter Tuning & Optimization
To prevent **underfitting** or **overfitting**, we use hyperparameters to control growth:

* **Maximum Depth**: Limits how many levels the tree can grow.
* **Minimum Samples Split**: The smallest number of samples a node must have before the algorithm considers splitting it.
* **Minimum Samples Leaf**: The smallest number of samples allowed in any leaf node.
* **Max Features**: Limits the number of features considered when searching for the best split at each node.
* **Criterion**: The mathematical formula (e.g., `squared_error`) used to evaluate the quality of a split.

## Implementation
![Creating a Decision Tree Model](/assets/images/decisiontreeModel.png)
