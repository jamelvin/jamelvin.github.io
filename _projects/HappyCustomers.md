---
title: "Using Random Forest to Predict what Makes Happy Customers for a Delivery Service"
excerpt_separator: "<!--more-->"
categories:
  - Project
tags:
  - Random Forest
  - Classification
---

Likert scale survey data was collected from a customer cohort and responses were used to develop a Random Forest classification model to predict what aspects of the ordering and delivery process were most likely to lead to customer happiness.

![Bar Chart of Important Characteristics for Customer Happiness]({{ site.baseurl }}/images/HappyCustImportances.png "Most important characteristics leading to customer happiness")

<!--more-->

The model suggests the most important characteristics leading to customer happiness were `Able to Find Everything` (30.3%) and `Delivery was On Time` (27.3%).

The clearest story in the sample data was for `Delivery was On Time`, where 65% of Happy respondents gave a 5/5 rating compared to only 35% of Unhappy respondents. For `Able to Find Everything`, 48% of Happy respondents rated it 4/5 or above, compared to 30% of Unhappy respondents.

![Histograms of Delivery was On Time and Able to Find Everything against Customer Happiness]({{ site.baseurl }}/images/HappyCustHistograms.png "Distribution of Ratings for Delivery was On Time and Able to Find Everything")

This suggests that to improve customer satisfaction, business development and investment should be focused on improving On Time Delivery and expanding inventory/partnerships to increase the likelihood a customer is able to find the products they are looking for.

The model, which uses survey responses on Delivery was On Time, Customer was Able to Find Everything, Prices were Good and the App was Easy to Use, provides about 70% accuracy in predicting the happiness of the customer. A small survey sample size (N=126) may be limiting the potential accuracy of the model, as well as the types of analysis available and thus for future surveys, depending on costs, larger samples would ideally be prioritized.

The analysis excluded two survey responses after initial data exploration, Customer Found their Order was as Expected and Delivery Satisfaction. Customer Found their Order was as Expected showed the weakest relationship with customer happiness and the exclusion of Delivery Satisfaction was determined to lead to the best performance in model accuracy when excluded along with Customer Found their Order was as Expected.

![Histogram of Customer Found their Order was as Expected against Customer Happiness]({{ site.baseurl }}/images/HappyCustHistogramExpected.png "Distribution of Ratings for Customer Found their Order was as Expected")

A potentially concerning insight from the sample data was that Customer Found their Order was as Expected had the lowest average rating at only 2.53/5. While the relationship of this survey response was weak with customer happiness in the sample data, one hypothesis, if the raw data is correct, is that if customers are not typically receiving what they expect, this characteristic isn't informative of their happiness. However, intuition would suggest that receiving what you would expect to receive should be important. Future surveys may want to investigate this further, through additional questions, to better understand why customers are providing low ratings for Customer Found their Order was as Expected.

To see additional details and the Python code, see the respository [here](https://github.com/jamelvin/K85eN3vyoFJwCQ3W).
