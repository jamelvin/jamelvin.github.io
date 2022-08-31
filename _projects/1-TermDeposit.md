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

Demographics, financials and call center data was collected for customers during a direct marketing campaign selling term deposit contracts to clients at a European bank. Logistic Regression models using various subsets of the data were developed to predict if a customer will purchase the term deposit. As the typical purcase rate is quite low (only 7.2% in the provided dataset), the models prioritized balancing the tradeoff between losing possible subscriptions and producing false leads, with a bias towards capturing all possible subscribers.  This was done by using the **F1 score** as a key success metric to assess model performance.

![Matrix of Potential Outcomes from Model Predicitons]({{ site.baseurl }}/images/TermDepositMatrix.png "Model Prediction Potential Outcomes Chart")

<!--more-->

Three Logistic Regression models were built, each representing a different stage in the development of a sales campaign.  The first, which was aimed at determining who to target, used only demographic and financial data available.  The second, with the goal of helping to develop a sales campaign strategy added contact information.  Finally the third model added information about interactions with customers and could be used to help set strategies and targets for sales staff.

| Model                                            | F1 Score    | Accuracy | Pct of False to All Leads | Pct of All Sales Captured |    
| ------------------------------------------------ | ----------- | -------- | ------------------------- | ------------------------- |
| Demographics and Financials                      | 17.4%       | 64.0%    | 89.5%                     | 51.5%                    |
| Demographics, Financials and Contact             | 19.1%       | 67.5%    | 88.3%                     | 52.9%                    |
| Demographics, Financials, Contact and Campaign   | 43.4%       | 87.2%    | 67.9%                     | 66.8%                    |

The Demographics and Financials model, if used as an initial test for a customer dataset, immediately eliminates around 2/3rds of the dataset, while only losing about 50\% of the potential leads.  In the remaining dataset, approximately 1 in 10 are successfully converted to sales, compared to around 1 in 14 in the original data.

The model can also be used to aid in identifying the types of customers to target.  Younger (< 30) and Older (> 60) age groups, unmarried customers, those outside of the services/housemaid industries, no housing or personal loans and having more than $1000 in their account are all determined by the model to be more likely to sign up for term deposits.  To further drill down into the ideal demographics, combinations of these groups can be examined.  For instance, young single customers have higher purchase rates in the full dataset than their comparison groups.  However, care has to be taken as combinations of groups quickly leads to very low sample sizes, such as a very low frequency of single customers over the age of 60.

| Age Group | Marital Status || Pct of Successful Sales | Group Sample Size |
| --------- | -------------- || ----------------------- | ----------------- |
| < 30 | Single || 12.7% | 2873 |
| | Married || 6.9% | 1305 |
| | Divorced || 11.5% | 96 |
| 30-60 | Single || 8.3% | 8005 |
| | Married || 5.8% | 22895 |
| | Divorced || 7.8% | 4592 |
| 61+ | Single || 9.0% | 11 |
| | Married || 37.6% | 186 |
| | Divorced || 54.1% | 37 | 

![Conversion success rates of term deposit sales by age for both Single and Married customers]({{ site.baseurl }}/images/TermDepositAgeMarital.png "Term Deposit Sales by Age for Single and Married Customers")


To see additional details and the Python code, see the respository [here](https://github.com/jamelvin/qt28VI6Bkxza3LNd).
