# Overview

We are a data science consulting company named M&Y Consulting Services, LLC looking to provide predictive and actionable insights regarding likely churn candidates at the telecommunications company SyriaTel. We hope to create a complex model that can predict likely churn candidates as well as the features that impact churn the most. 

Our presentation, where we analyze out dataset can be found at: ["A Study on Churn and Retention Rates"](Phase_3_Presentation.pdf)

# Business Problem 

Telecommunication services have increased dramatically due to the growing demand among consumers as many businesses require telecommunication services in order to help their business expand. This has led to communications becoming one of the most competitive and fastest-growing industries in the globe. Despite that there are some policies to reduce the rivalry among big corporations, the competition among companies in the telecom industry has been intensified in recent years. In the US, the telecom market continues to witness intense pricing competition. As one of the many telecom companies, SyriaTel is competing with other world top telecom companies such as AT&T, Verizon, Comcast, etc. and they are currently looking for a solution to retain as many customers as they can as churn rates have been rising steadily-likely due to inflation. As a solution, we are going to make several predictive models using a Classification to help SyriaTel identify the potential churn customers using the recall score. We're focusing on the recall score because we're looking to minimize the false negatives while also identifying churn candidates.

# Data Understanding

We are sourcing the data for this project from the SyriaTel dataset, which can be found at ["SyriaTel Dataset"](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset)

In total, we reviewed 3,333 data points from this SyriaTel data set. Our visualizations can also be found seperately in the images folder located in this repository. We will analyze a list of variables from the SyriaTel data such as whether or not the customer has an international plan or voice mail plan, number of voicemail messages, total calling minutes, the state the customer lives in, and charge rates for each time of the day. Limitations of the data include possible overfitting, dealing with an outdated and a narrow data set, data imbalance, and possible outliers.

# Classification Modeling Results 

In our best model we are looking for the model that produces the highest recall score. We are focused on the recall score of our model since we are aiming to identify all likely churn candidates. We are placing less importance on finding the true negatives because we are primarily interested in spotting the real churners (true positives) as often as possible. After we find our model model, we then will look to find the highest impact features in relation to our target variable, churn. 

![Recall Scores of Our Best Model](images/recall_score.png)

As you can see in the graph above, our best model has cross-validated recall score of .80. When we ran our best model using unseen testing data, it provided a recall score of .75. This means that our model accurately predicted 75% of all true positives and false negatives from the unseen data.

![High Impact Features](images/feature_import.png)

In the graph above we highlight the top three impact features than affect churn rate. These features are whether or not the customer has an International plan, the number of customer service calls, and the total call minutes per customer. We can interpret these log odd coefficients by using Euler's Number 'e'. For example, a customer who has a international plan has 8.8 times the odds of churning versus a customer who does not have an international plan. A customer who has two or more customer service calls has 2.24 times the odds of churning than a customer who has zero or one customer service call. Also, for every one standard deviation increase in total calling minutes, we'd expect churn to increase 1.51 times the average churn rate.

# Conclusion & Recommendations
Our best model had a cross-validated recall score of .80, and a recall score of .75 when the model was run against our unseen test data. We found the top three features that influence the customer churn most are: International Plan Rate, Number of Service Calls, and Total Minutes. We are focused on finding churn candidates, and will use our impact features to find likely customers who fulfill this threshold. Once we identify these customers, we believe its best to offer promotions, discounts, and surveys to help retain and attract new customers. Lastly, given the outsized churn rate within those with an international plan we believe its best to lower the plan rate for international plans. 

# Repository Contents
- Working_Notebook
- data
- images
- .gitignore
- CONTRIBUTING.md
- Data_Notebook.ipynb
- LICENSE.md
- Model_Notebook.ipynb
- Phase_3_Presentation.pdf
- README.md
