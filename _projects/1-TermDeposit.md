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

Three Logistic Regression models were built, each representing a different stage in the development of a sales campaign.  The first, which was aimed at determining who to target, used only demographic and financial data available.  The second, with the goal of helping to develop a sales campaign strategy added contact information.  Finally the third model added information about interactions with customers and could be used to help set strategies and targets for sales staff.

| Model                                            | F1 Score    | Accuracy | Pct of False to All Leads | Pct of All Sales Captured |    
| ------------------------------------------------ | ----------- | -------- | ------------------------- | ------------------------- |
| Demographics and Financials                      | 17.7%       | 66.0%    | 89.3%                     | 49.5%                    |
| Demographics, Financials and Contact             | 19.1%       | 67.5%    | 88.3%                     | 52.9%                    |
| Demographics, Financials, Contact and Campagin   | 43.4%       | 87.2%    | 67.9%                     | 66.8%                    |


To see additional details and the Python code, see the respository [here](https://github.com/jamelvin/qt28VI6Bkxza3LNd).
