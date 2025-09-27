# IMT-574-Final-Project

# Introduction to the Dataset

We chose a dataset from the University of California Irvine Machine Learning Repository that collected information from direct telemarketing campaigns of a Portuguese banking institution from May 2008 to November 2010 (Moro et al).

[Bank Marketing - UCI Machine Learning Repository
](https://archive.ics.uci.edu/dataset/222/bank+marketing)

The general predictor variable within this dataset is written as a binary outcome: yes or no, whether the client would subscribe to a bank term deposit. Investopedia, a website focused on providing general information and definitions about the specifics of financial services and institutions describes a term deposit as when a customer, “will deposit or invest in one of these accounts, agreeing not to withdraw their funds for a fixed period in return for a higher rate of interest paid on the account" (Investopedia).

There are 16 features within this dataset, including the following categories (Moro et al):

**Demographic information of customers:**
- Age
- Occupation
- Marital status
- Highest attained education level

**Information related to customers' current accounts:**
- Whether the client has credit in default
- Average yearly balance
- Whether the client has a housing loan
- Whether the client has a personal loan

**Additional information regarding the call itself:**
- Contact communication type (cellular vs a landline telephone)
- The day of the week that the client was contacted
- Duration of the phone call
- Number of times this client was contacted for this campaign
- Number of days that passed by after the client was last contacted from a previous campaign
- Number of contacts performed before this campaign and for this client
- The outcome of the previous campaign

**Response variable we are interested in investigating:**
- Has the client subscribed to a term deposit?

# Research Question
**What factors determine whether bank customers will subscribe to a term deposit in response to a telemarketing campaign?**

The marketing campaigns were based on phone calls. Often, more than one contact with the same client was required to ensure that said client would agree to subscribe to a term deposit. We are interested in developing a model that can take these different features into account in order to best optimize future telemarketing campaigns.

**In other words, the classification goal is to predict if the client will subscribe (yes/no) to a term deposit (variable y).**

# Choice of Algorithm

We needed to use models that would estimate binary outcomes for classification, so around 5 general categories of models were used in order to answer the research question.

In the context of a marketing campaign, recall was determined to be the most relevant performance metric for each model. Since our goal is to increase subscriptions to term deposits, discovering the number of true positives is more significant than the number of true negatives via precision (although we also looked at the precision scores).

Initially, we attempted to answer this research question with various algorithms that ultimately were not the most effective:

* **Logistic Regression:** Multiple attempts were made with logistic regression, none of them had a recall that was higher than 38%. Our assumption was that this particular data set didn’t have a linear distribution.
* **K-nearest neighbors:** We simply did not find any truly significant results with K-nn. It’s likely that the dataset used is rather noisy. Especially as there was a huge class imbalance between the number of positive observations in the data set (approx. 4000) and the number of negative observations (approx. 30,000).
* **Gradient Boosted Decision Trees:** Similarly, it’s likely that this class imbalance impacted our attempt at gradient boosting since the majority class of negative observations (or people who did not subscribe to the term deposit) seemed to be favored.

However, with certain alterations, we found that both decision trees and a random forest could be used as effective models for this data set:

* **Decision Tree:** (Decision Tree with Lower Decision Threshold, Undersampling & Synthetic Sampling): Seen in Appendix B
* **Random Forest:** Finally, random forest produced the highest recall for this dataset since we used a grid search. We assume that it is also a result of the ensemble method better handling the class imbalance compared to the individual decision trees.

# Additional Data Analysis: 

Included within the rest of this repository under IMT 574 Final Project_Ivanov_Stelter_Zhu.pdf
