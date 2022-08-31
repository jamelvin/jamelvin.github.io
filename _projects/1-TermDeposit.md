---
title: "Logistic Regression Models for Determining who will Purchase a Term Deposit Contract"
excerpt_separator: "<!--more-->"
categories:
  - Project
tags:
  - Logistic Regression
  - Classification
  - Imbalanced Classes
---

Demographics, financials and call center data was collected for customers during a direct marketing campaign selling term deposit contracts to clients at a European bank. Logistic Regression models using various subsets of the data were developed to predict if a customer will purchase the term deposit. As the typical purcase rate is quite low (only 7.2% in the provided dataset), the models prioritized balancing the tradeoff between losing possible subscriptions and producing false leads, by using the **F1 score** as the success metric to assess model performance.

![Matrix of Potential Outcomes from Model Predicitons]({{ site.baseurl }}/images/TermDepositMatrix.png "Model Prediction Potential Outcomes Chart")

<!--more-->

To see additional details and the Python code, see the respository [here](https://github.com/jamelvin/qt28VI6Bkxza3LNd).
