---
title: "MaRAI: Engineering AI for Maternal Health Impact"
excerpt: "How I achieved 99.6% accuracy in predicting pregnancy complications using Random Forest."
categories:
  - Machine Learning
tags:
  - Healthcare AI
  - Python
  - Scikit-Learn
---

### The Problem: Why Maternal Health?
Maternal mortality remains a critical global health challenge. As a Computer Engineering student and a mother, I saw an opportunity to apply predictive modeling to identify high-risk pregnancies before they become emergencies.

### The Technical Approach
For the **MaRAI** project, I chose the **Random Forest Classifier**. While simpler models were considered, the Random Forest's ability to handle non-linear relationships in medical data (like systolic vs. diastolic blood pressure) provided superior results.

* **Dataset:** 1,500 clinical entries.
* **Accuracy:** 99.6%
* **Key Features:** Age, SystolicBP, DiastolicBP, BS (Blood Sugar), BodyTemp, and HeartRate.

* ![MaRAI Confusion Matrix](/assets/images/marai_confusion_matrix.png)

### Deployment with Streamlit
Model accuracy is useless if clinicians cannot access it. I utilized **Streamlit** to build a lightweight, real-time interface where health workers can input patient vitals and receive an instant risk assessment.

[View the Code on GitHub](https://github.com/Catheria29/MaRAI)
