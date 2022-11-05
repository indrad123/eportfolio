---
description: >-
  By Indra Dewaji, part of Assignment on Applied AI at University of York by
  Indra Dewaji, March 2022
---

# Customer Churn Analysis  in the Telco Company

## Executive Summary

Predicting customer churn can help the telecom company to analyze and improve their service or retain their customer. There are many factors in customer churn that can be analyzed employed using the Artificial Intelligence approach. Customer churn is the behavior of the customer to move a service from one provider to another provider. In the telco company, customer churn may be caused by many factors, such as price, quality of service, promotion, etc. Other factors such as age, marital status, occupation, also might impact the customer churn. To come to the conclusion, some methods in Artificial Intelligence will be employed to get the full insight, into what happened to the customer and what factors impacted the customer's decision to choose the service.

The prediction of customer churn can help the company to retain the customer. Random forest and Naïve Bayes is used as classification analysis process. Random forest is a classification method using a decision tree, used on a large dataset where the classification decision until the maximum level of the tree. Random Forest classification is performed better compared to linear regression, because random forest may adapt easily to the independent data \[4]. Naïve Bayes classification is also used as the comparison in this customer churn analysis. Naïve Bayes classification may use in the uncertain dataset classification. Naïve Bayes classification is based on the probability theory, where the assumption of prediction, taken from the past attributes relates to the past identified result \[5].

Steps on the customer churn analysis in this report are data pre-processing, data analysis, and churn prediction. The dataset used in the report contains six thousand rows of sample data and also contains fifty-six attributes that need to analyze. Weka is used as the main tool for data analysis and predict customer churn. The result of the report is to provide which factors impacted the customer churn based on the dataset, so the company can predict and take action based on the result.

## Introduction

The competition in the telecom industry has impacted the customer churn rate. Some companies are looking for a strategy to retain the customer in many ways. The analysis in the telecom industries includes the segmentation and customer analysis. In the segmentation, telecom industries analyze based on the value and behavior of the customers. The segmentation predicts which segment of the user will value the provider and how the telecom industry can improve their service in this segment. Churn analysis is a remedial process from a range of period to analyze and predict the factor of why the customer migrate from one provider to another provider \[1]. This report will cover customer churn prediction and identifying which factors causing customer churn.

Studies indicate that customer churn is costly to the company compared to customer retention. The competition among the telecom providers can easily make the customer move from one provider to another provider \[2]\[10]. The company provides the below data to analyze the churn of customers.

&#x20;

\#   Column                     &#x20;

\---  ------                     &#x20;

&#x20;0   MonthlyRevenue            &#x20;

&#x20;1   MonthlyMinutes            &#x20;

&#x20;2   TotalRecurringCharge      &#x20;

&#x20;3   DirectorAssistedCalls     &#x20;

&#x20;4   OverageMinutes            &#x20;

&#x20;5   RoamingCalls              &#x20;

&#x20;6   PercChangeMinutes         &#x20;

&#x20;7   PercChangeRevenues        &#x20;

&#x20;8   DroppedCalls             &#x20;

&#x20;9   BlockedCalls             &#x20;

&#x20;10  UnsweredCalls            &#x20;

&#x20;11  CustomerCareCalls        &#x20;

&#x20;12  ThreewayCalls             &#x20;

&#x20;13  ReceivedCalls            &#x20;

&#x20;14  OutboundCalls            &#x20;

&#x20;15  InboundCalls             &#x20;

&#x20;16  PeakCallsInOut           &#x20;

&#x20;17  OffPeakCallsInOut        &#x20;

&#x20;18  DroppedBlockedCalls      &#x20;

&#x20;19  CallForwardingCalls      &#x20;

&#x20;20  CallWaitingCalls         &#x20;

&#x20;21  MonthsInService            &#x20;

&#x20;22  UniqueSubs                 &#x20;

&#x20;23  ActiveSubs                 &#x20;

&#x20;24  ServiceArea               &#x20;

&#x20;25  Handsets                   &#x20;

&#x20;26  HandsetModels              &#x20;

&#x20;27  CurrentEquipmentDays       &#x20;

&#x20;28  AgeHH1                    &#x20;

&#x20;29  AgeHH2                    &#x20;

&#x20;30  ChildrenInHH              &#x20;

&#x20;31  HandsetRefurbished        &#x20;

&#x20;32  HandsetWebCapable         &#x20;

&#x20;33  TruckOwner                &#x20;

&#x20;34  RVOwner                    &#x20;

&#x20;35  Homeownership             &#x20;

&#x20;36  BuysViaMailOrder          &#x20;

&#x20;37  RespondsToMailOffers      &#x20;

&#x20;38  OptOutMailings           &#x20;

&#x20;39  NonUSTravel               &#x20;

&#x20;40  OwnsComputer              &#x20;

&#x20;41  HasCreditCard             &#x20;

&#x20;42  RetentionCalls             &#x20;

&#x20;43  RetentionOffersAccepted    &#x20;

&#x20;44  NewCellphoneUser          &#x20;

&#x20;45  NotNewCellphoneUser       &#x20;

&#x20;46  ReferralsMadeBySubscriber  &#x20;

&#x20;47  IncomeGroup                &#x20;

&#x20;48  OwnsMotorcycle            &#x20;

&#x20;49  AdjustmentsToCreditRating  &#x20;

&#x20;50  HandsetPrice              &#x20;

&#x20;51  MadeCallToRetentionTeam   &#x20;

&#x20;52  CreditRating              &#x20;

&#x20;53  PrizmCode                 &#x20;

&#x20;54  Occupation                &#x20;

&#x20;55  MaritalStatus             &#x20;

&#x20;56  Churn                     &#x20;

Table 1. Attribute List

&#x20;

From the above data, not all information really needed. In pre-processing, we need to identify, which data really important and related to the customer churn. Of course, it is difficult to understand this massive data by seeing it manually one by one, it needs a method to automate the prediction instead do it manually.

Artificial Intelligence specific to machine learning can be employed to analyze customer churn.  According to P. Lalwani, et.al, there are two ways to handle customer churn management, they are reactive and proactive approaches. In the reactive approach, customer churn is handled after the customer cancelled or migrates into another service provider. The proactive approach predicts the customer churn based on the service and the characteristic of the customer, so the customer churn can be avoided in the early stage \[3].&#x20;

Machine learning proved in many businesses cases, effectively predicts based on past data \[3]. Pre-processing is the important initial stage to reduce complexity or overfitting to create the prediction model. The next stage is classification to classify each characteristic of data. There is two machine learning technique used in this analysis, they are Random Forest and Naïve Bayes technique. The reason to choose these two methods is that they are among the popular machine learning classification methods.

Naïve Bayes classification used the prediction based on probability generate from the past data.  At customer churn analysis, the independent data probability which causes customer churn can be written below equation:

|   | ![](<.gitbook/assets/image (5).png>) | (1) |
| - | ------------------------------------ | --- |

Where A and B are independent events. We can take as an example if A is monthly revenue and B is a total recurring charge, these two variables independently create the probability of customer churn by multiplying the probability of monthly revenue times the probability of total recurring charge \[6, p.46]. In the probability theory, there is a conditional probability where condition A given the occurrence of condition B.

|   | ![](<.gitbook/assets/image (25).png>) | (2) |
| - | ------------------------------------- | --- |

This conditional probability is explaining where the probability of A given that B is true, then it is the division between probability A and B divided by the probability of B \[6, p.46]. Equation (2) fulfill the commutative law the probability B given that A is true is equal to probability A and B divided by probability A.

|   | ![](<.gitbook/assets/image (9).png>) | (3) |
| - | ------------------------------------ | --- |

If we see on equation (1), so equation (2) and (3) can be simplified as      &#x20;

|   | ![](<.gitbook/assets/image (32).png>) | (4) |
| - | ------------------------------------- | --- |
|   | ![](<.gitbook/assets/image (23).png>) | (5) |
|   | ![](<.gitbook/assets/image (2).png>)  | (6) |

Further of manipulating this equation, for two different events A and B, the probability written on below equation and known as Bayes’ rule.

|   | ![](<.gitbook/assets/image (34).png>) | (7) |
| - | ------------------------------------- | --- |

&#x20;

&#x20;

Equation (7) in a word can be called posterior probability \[6, p.47].

|   | ![](<.gitbook/assets/image (15).png>) | (8) |
| - | ------------------------------------- | --- |

This is the basic of Naïve Bayes classification where this classification will involve prior probability and evidence.

Random Forest classification has the popularity of high accuracy. Random Forest method built based on trees decision collection. The first stage is to select the random dataset to build the tree. The unselected data called will be kept to estimate the good fit in the next stage.  The local training data split and linked with the other random subset with the best fit. All the nodes grow to the most extent possible \[7].

## Literature Review

The solution in this report is aligned with the proposed solution from researchers \[1]\[3]\[8]\[9]. S. Wu et.al \[1] propose the solution with the approach of using Random Forest. In his research, Random Forest was used to predicting customer churn. And for a deep understanding of the churn customer factor, his research used Attribute Selected Classifiers. Attribute Selected Classifiers make selective attributes only for the related factor to the customer churn prediction. In his research, the customer profiling where the customer indicated churn, was used to identify another customer with the same profile. The retention strategy will be decided based on this information \[1].

S. Wu et.al \[1] identified the potential of imbalance on the dataset. Most of the customer does not change the provider in a very short period. Their research aim is to fill the gap where other researchers only focus on one aspect of analysis, either on churn prediction or only customer segmentation. Their research combines both aspects to get more accurate information and characteristics for the telecom company to take action to retain the customer.

P. Lalwani et al. \[3] provide a comparative analysis on machine learning techniques such as Logistic Regression, Naïve Bayes, Support Vector Machine, Decision Trees, Random Forest Classifier, Extra Tree Classifier. In addition, the research also employed boosting algorithms such as Ada Boost, XGBoost, and CatBoost. Their research concluded that Ada Boost and XGBoost have performed better compares to other algorithms.

I. Ullah et al. \[8] employed Random Forest, J48, and other techniques in the research. The methods in the research are divided into two main parts, data pre-processing and customer classification and prediction. The data pre-processing is divided into two steps, noise removal, and features selection. The conclusion of the research shows that Random Forest and J48 performed better with 88% accuracy.

A. Idris et al. \[9] compares the machine learning technique Random Forest and K Nearest Neighbour (KKN). The research also points out the importance of data pre-processing to get a better and more accurate result. Random Under Sampling (RUS) was used in the research to normalize the distribution between churners and non-churner.

Y. Yulianti and A. Saifudin \[10] employed Naïve Bayes in their customer churn classification technique. They are pointing out that customer churn would very costly to the companies. It is important to have a technique to get high accuracy to detect the customer churn. The research has shown the positive result to identify the customer churn where it can be used as the reference to the company to take action.

## Research Design

The proposed customer churn prediction design will use two main steps, data pre-processing and customer classification for churner and non-churner.

![](<.gitbook/assets/image (45).png>)

Figure 1. Steps Analysis

The research is using a dataset of small version of the telecom dataset compared to the original data in Kaggle (https://www.kaggle.com/jpacse/datasets-for-churn-telecom), which contains 6,380 records. The dataset also contains 56 attributes. The data cleansing process is replacing the empty value with a mean value from the dataset.

Feature selection is used to select only relevant data for the prediction. This can improve training time in a model and may increase accuracy. In the WEKA tool, the evaluator used is CfsSubsetVal, where it evaluates the attributes if it is redundant and has the individual predictive capability. To optimize the training, the genetic algorithm will be used. Genetic algorithms are algorithms mimicking the evolutional processes. It is an iterative process until reaches its fittest condition \[11].

The prediction employs two methods, Random Forest and Naïve Bayes. Both techniques are compared to find which one has a better performance. The comparison of the performance considers based on accuracy, precision, recall, and f-measure. Accuracy calculated based on the below equation:

|   | ![](<.gitbook/assets/image (21).png>) | (9) |
| - | ------------------------------------- | --- |

where TP stands for true positive, TN stands for true negative, FP stands for false positive, and FN stands for false-negative \[8]. True positive means when the probability says it is true, the actual value is also true. Similarly, if true negative, if the probability says it is true but the actual result is negative. The true positive rate should be as high as possible and on the other side, the false positive rate should be as low as possible.

|   | ![](<.gitbook/assets/image (31).png>) | (10) |
| - | ------------------------------------- | ---- |
|   | ![](<.gitbook/assets/image (47).png>) | (11) |

To get the precision, it is calculated with the equation below:

|   | ![](<.gitbook/assets/image (43).png>) | (12) |
| - | ------------------------------------- | ---- |

If the model is correctly true positive, the measure for this is called recall. The calculation of recall is:

|   | ![](<.gitbook/assets/image (24).png>) | (13) |
| - | ------------------------------------- | ---- |

&#x20;Another measure is called f-measure, calculated as the mean between precision and recall.

|   | ![](<.gitbook/assets/image (11).png>) | (14) |
| - | ------------------------------------- | ---- |

The f-measure is useful to compare two techniques, where the value should be closest to 1.0 \[8].&#x20;

&#x20;

## Experimental Results and Analysis

Weka version 3.8.6 windows version is used for analyzing and predicting the data on an Intel® Core™ i7-10510U CPU @ 1.80 GHz 2.30 GHz, RAM 24 GB, 1 TB SDD and 1 TB HDD drive. The dataset for this experimental activity is using one small dataset containing 6380 records of data with 57 attributes. The attributes of the data including the data type are shown in table 2 below.

&#x20;

\#   Column                     Non-Null Count  Dtype&#x20;

\---  ------                     --------------  -----&#x20;

&#x20;0   MonthlyRevenue             6380 non-null   object

&#x20;1   MonthlyMinutes             6380 non-null   object

&#x20;2   TotalRecurringCharge       6380 non-null   object

&#x20;3   DirectorAssistedCalls      6380 non-null   object

&#x20;4   OverageMinutes             6380 non-null   object

&#x20;5   RoamingCalls               6380 non-null   object

&#x20;6   PercChangeMinutes          6380 non-null   object

&#x20;7   PercChangeRevenues         6380 non-null   object

&#x20;8   DroppedCalls               6380 non-null   float64

&#x20;9   BlockedCalls               6380 non-null   float64

&#x20;10  UnsweredCalls              6380 non-null   float64

&#x20;11  CustomerCareCalls          6380 non-null   float64

&#x20;12  ThreewayCalls              6380 non-null   float64

&#x20;13  ReceivedCalls              6380 non-null   float64

&#x20;14  OutboundCalls              6380 non-null   float64

&#x20;15  InboundCalls               6380 non-null   float64

&#x20;16  PeakCallsInOut             6380 non-null   float64

&#x20;17  OffPeakCallsInOut          6380 non-null   float64

&#x20;18  DroppedBlockedCalls        6380 non-null   float64

&#x20;19  CallForwardingCalls        6380 non-null   float64

&#x20;20  CallWaitingCalls           6380 non-null   float64

&#x20;21  MonthsInService            6380 non-null   int64&#x20;

&#x20;22  UniqueSubs                 6380 non-null   int64&#x20;

&#x20;23  ActiveSubs                 6380 non-null   int64&#x20;

&#x20;24  ServiceArea                6380 non-null   object

&#x20;25  Handsets                   6380 non-null   int64&#x20;

&#x20;26  HandsetModels              6380 non-null   int64&#x20;

&#x20;27  CurrentEquipmentDays       6380 non-null   int64&#x20;

&#x20;28  AgeHH1                     6380 non-null   object

&#x20;29  AgeHH2                     6380 non-null   object

&#x20;30  ChildrenInHH               6380 non-null   object

&#x20;31  HandsetRefurbished         6380 non-null   object

&#x20;32  HandsetWebCapable          6380 non-null   object

&#x20;33  TruckOwner                 6380 non-null   object

&#x20;34  RVOwner                    6380 non-null   object

&#x20;35  Homeownership              6380 non-null   object

&#x20;36  BuysViaMailOrder           6380 non-null   object

&#x20;37  RespondsToMailOffers       6380 non-null   object

&#x20;38  OptOutMailings             6380 non-null   object

&#x20;39  NonUSTravel                6380 non-null   object

&#x20;40  OwnsComputer               6380 non-null   object

&#x20;41  HasCreditCard              6380 non-null   object

&#x20;42  RetentionCalls             6380 non-null   int64&#x20;

&#x20;43  RetentionOffersAccepted    6380 non-null   int64&#x20;

&#x20;44  NewCellphoneUser           6380 non-null   object

&#x20;45  NotNewCellphoneUser        6380 non-null   object

&#x20;46  ReferralsMadeBySubscriber  6380 non-null   int64&#x20;

&#x20;47  IncomeGroup                6380 non-null   int64&#x20;

&#x20;48  OwnsMotorcycle             6380 non-null   object

&#x20;49  AdjustmentsToCreditRating  6380 non-null   int64&#x20;

&#x20;50  HandsetPrice               6380 non-null   object

&#x20;51  MadeCallToRetentionTeam    6380 non-null   object

&#x20;52  CreditRating               6380 non-null   object

&#x20;53  PrizmCode                  6380 non-null   object

&#x20;54  Occupation                 6380 non-null   object

&#x20;55  MaritalStatus              6380 non-null   object

&#x20;56  Churn                      6380 non-null   object

Table 2. Attribute List with the Data Type

From 6380 records of data, the churn distribution is as shown below.

![](<.gitbook/assets/image (8).png>)

Figure 2. Churn Distribution

0 = Not Churn (1811)

1 = Churn (4569)       &#x20;

&#x20;

At the data preparation stage, the CSV file is converted into .arff file format as the native file type for Weka. To clean the data, Weka has the functionality in the pre-processing stage. The identified unknown data will be marked as “?” sign, and it replaced with “0” using “ReplaceMissingWithUserConstant”. This functionality will replace all missing values with the supply constant that is set in the properties. The filter is categorized as an unsupervised filter \[12].

The next step is to select the supervised filter “AttributeSelection”.

&#x20;

![](<.gitbook/assets/image (46).png>)

Figure 3. “AttributeSelection” using “GeneticSearch”

&#x20;

The “AttributeSelection” filter function used to select search optimisation algorithm. The genetic search has been selected for the search function. A genetic algorithm is an algorithm mimicking evolution theory by Charles Darwin. It is searching after many iterations to find the best fit on the population. There are five phases on genetic algorithm, they are initial population initialization, fitness function, selection, cross over, and mutation \[13].

The genetic algorithm will help on the optimisation during customer churn analysis. The selected attributes will help the company to narrow down the analysis instead of checking all bunches of data. The company can focus only for these attributes for action and improvement.

The result after filtering using a genetic algorithm, the attributes selected are as below.

![](<.gitbook/assets/image (22).png>)

Figure 4. Result of Filter using Genetic Algorithm

The company now can only focus on attributes _Months in Service_, _Service Area_, _Current Equipment Days_, _and Made Calls to Retention Team_.

The classification process employed Naïve Bayes and Random Forest algorithm. Naïve Bayes algorithm, as discussed in equation (7) in the introduction section, is the division between probability B in the event A multiplied by probability A, divided by probability B.

|   | ![](<.gitbook/assets/image (26).png>) | (7) |
| - | ------------------------------------- | --- |

The idea of the Naïve Bayes algorithm is to use the probability of a feature, where it is most likely correct. This probability will relate to another feature where the other probability is also counted. In the real world, let’s assume that black color will relate to a blackboard. But black color also might relate to a black cat. The probability of the black color is a blackboard is depend on the shape, if it is square, most likely it is a blackboard, but if the shape is not square, we can assume it is a cat. Of course, this sample is not as simple as that, but we can see the idea behind this Naïve Bayes algorithm, that the probability of an event will depend on another event \[13].

Random Forest algorithm, consisting of many decision trees, uses the randomness method to split the data and make the decision. A tree decision we can call a class. Each class is randomly selected to “vote” the decision. Each class has a low correlation with the other \[14].

Below is the result after running Naïve Bayes and Random Forest algorithm. Both of the algorithms are using 10 folds cross-validation.  Cross-validation is used to shuffle the data randomly by splitting the sample data to check the “skill” of unseen data \[16].

&#x20;

| <p> </p><p> <strong></strong> </p><p> </p> | <p> </p><p><strong>TP Rate</strong></p><p> </p> | <p> </p><p><strong>FP Rate</strong></p><p> </p> | <p> </p><p><strong>Precision</strong></p><p> </p> | <p> </p><p><strong>Recall</strong></p><p> </p> | <p> </p><p><strong>F-Measure</strong></p><p> </p> | <p> </p><p><strong>MCC</strong></p><p> </p> | <p> </p><p><strong>ROC Area</strong></p><p> </p> | <p> </p><p><strong>PRC Area</strong></p><p> </p> | <p> </p><p><strong>Class</strong></p><p> </p> |
| ------------------------------------------ | ----------------------------------------------- | ----------------------------------------------- | ------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------- | ------------------------------------------- | ------------------------------------------------ | ------------------------------------------------ | --------------------------------------------- |
|                                            | <p> </p><p>0.063</p><p> </p>                    | <p> </p><p>0.047</p><p> </p>                    | <p> </p><p>0.349</p><p> </p>                      | <p> </p><p>0.063</p><p> </p>                   | <p> </p><p>0.107</p><p> </p>                      | <p> </p><p>0.033</p><p> </p>                | <p> </p><p>0.559</p><p> </p>                     | <p> </p><p>0.323</p><p> </p>                     | <p> </p><p>Yes</p><p> </p>                    |
|                                            | <p> </p><p>0.953</p><p> </p>                    | <p> </p><p>0.937</p><p> </p>                    | <p> </p><p>0.72</p><p> </p>                       | <p> </p><p>0.953</p><p> </p>                   | <p> </p><p>0.82</p><p> </p>                       | <p> </p><p>0.033</p><p> </p>                | <p> </p><p>0.559</p><p> </p>                     | <p> </p><p>0.754</p><p> </p>                     | <p> </p><p>No</p><p> </p>                     |
| <p> </p><p>Weighted Avg.</p><p> </p>       | <p> </p><p>0.701</p><p> </p>                    | <p> </p><p>0.684</p><p> </p>                    | <p> </p><p>0.614</p><p> </p>                      | <p> </p><p>0.701</p><p> </p>                   | <p> </p><p>0.618</p><p> </p>                      | <p> </p><p>0.033</p><p> </p>                | <p> </p><p>0.559</p><p> </p>                     | <p> </p><p>0.632</p><p> </p>                     |                                               |

Table 3. Naïve Bayes Classification Result

&#x20;

| <p> </p><p> <strong></strong> </p><p> </p> | <p> </p><p><strong>TP Rate</strong></p><p> </p> | <p> </p><p><strong>FP Rate</strong></p><p> </p> | <p> </p><p><strong>Precision</strong></p><p> </p> | <p> </p><p><strong>Recall</strong></p><p> </p> | <p> </p><p><strong>F-Measure</strong></p><p> </p> | <p> </p><p><strong>MCC</strong></p><p> </p> | <p> </p><p><strong>ROC Area</strong></p><p> </p> | <p> </p><p><strong>PRC Area</strong></p><p> </p> | <p> </p><p><strong>Class</strong></p><p> </p> |
| ------------------------------------------ | ----------------------------------------------- | ----------------------------------------------- | ------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------- | ------------------------------------------- | ------------------------------------------------ | ------------------------------------------------ | --------------------------------------------- |
|                                            | <p> </p><p>0.285</p><p> </p>                    | <p> </p><p>0.219</p><p> </p>                    | <p> </p><p>0.34</p><p> </p>                       | <p> </p><p>0.285</p><p> </p>                   | <p> </p><p>0.31</p><p> </p>                       | <p> </p><p>0.069</p><p> </p>                | <p> </p><p>0.555</p><p> </p>                     | <p> </p><p>0.323</p><p> </p>                     | <p> </p><p>Yes</p><p> </p>                    |
|                                            | <p> </p><p>0.781</p><p> </p>                    | <p> </p><p>0.715</p><p> </p>                    | <p> </p><p>0.734</p><p> </p>                      | <p> </p><p>0.781</p><p> </p>                   | <p> </p><p>0.756</p><p> </p>                      | <p> </p><p>0.069</p><p> </p>                | <p> </p><p>0.555</p><p> </p>                     | <p> </p><p>0.751</p><p> </p>                     | <p> </p><p>No</p><p> </p>                     |
| <p> </p><p>Weighted Avg.</p><p> </p>       | <p> </p><p>0.64</p><p> </p>                     | <p> </p><p>0.574</p><p> </p>                    | <p> </p><p>0.622</p><p> </p>                      | <p> </p><p>0.64</p><p> </p>                    | <p> </p><p>0.63</p><p> </p>                       | <p> </p><p>0.069</p><p> </p>                | <p> </p><p>0.555</p><p> </p>                     | <p> </p><p>0.63</p><p> </p>                      |                                               |

Table 4. Random Forest Classification Result

&#x20;

![](<.gitbook/assets/image (35).png>)

Figure 5. ROC Plot Area for Naïve Bayes

&#x20;![](<.gitbook/assets/image (44).png>)

Figure 6. ROC Plot Area for Random Forest

&#x20;

![](<.gitbook/assets/image (33).png>)

Figure 7. Naïve Bayes Model Execution

![](<.gitbook/assets/image (3).png>)

Figure 8. Random Forest Model Execution

&#x20;

From Tables 3 and 4, we can see that Naïve Bayes is better in terms of precision, and the true positive rate also higher compare to the Random Forest. But for the f-measure score, Random Forest is better which means, the precision compares against the recall, Random Forest gets a better score. For the ROC score in Figures 5 and 6, Naïve Bayes get a better score. The ROC score is closer to 1, which is better \[17].

Figures 7 and 8 show the Naïve Bayes also better on the execution time. Naïve Bayes only need 0.02 seconds compared to 3.03 seconds for Random Forest. Naïve Bayes also score better on correctly classified instances.

## Conclusion

The competition in the telecom industry is really high. The retention strategy employing the Artificial Intelligence technique is beneficial to the company. The use of the Artificial Intelligence technique proved to be effective to predict and create the strategy for customer retention.

From the comparison in the previous section, Naïve Bayes is performed better in more aspects. The attributes of the month in service, service area, current equipment days, and made calls to the retention team, may use for further analysis and action.

Naïve Bayes has scored higher on precision, TP rate, and Precision. But Naïve Bayes also score high for the FP rate and Recall. The F-measure for Random Forest is better than the Naïve Bayes. On the other hand, Naïve Bayes has a better score for the ROC.

The use of optimization methods for genetic algorithms has narrowed the attributes that need to analyze. But this optimization method, still need to improve and compares with other methods in the future.

Overall, Naïve Bayes and Random Forest can be used to predict customer churn. The result is aligned with the literature review from some research. Future research may focus on how to optimize the dataset with other algorithms. It is needed to find a method where the user can easily identify which attributes directly impacted the customer churn, and Artificial Intelligence can suggest a solution to drive the customer churn factor. Besides, need further research to normalize the imbalance dataset since the behavior and the customer churn in the telecom industry will take time until it becomes a churner.

## References

\[1]   S. Wu, W. -C. Yau, T. -S. Ong and S. -C. Chong, "Integrated Churn Prediction and Customer Segmentation Framework for Telco Business," in IEEE Access, vol. 9, pp. 62118-62136, 2021, doi: 10.1109/ACCESS.2021.3073776.

\[2]   M. Óskarsdóttir, C. Bravo, W. Verbeke, C. Sarraute, B. Baesens, and J. Vanthienen, “Social network analytics for churn prediction in telco: Model building, evaluation and network architecture”, _Expert Systems with Applications_, vol. 85, pp. 204–220, 2017.

\[3]   P. Lalwani, M. K. Mishra, J. S. Chadha, and P. Sethi, “Customer churn prediction system: a machine learning approach”, Computing, vol. 104, no. 2, pp. 271–294, 2022.

\[4]   M. Schonlau and R. Y. Zou, “The random forest algorithm for statistical learning”, The Stata Journal: Promoting communications on statistics and Stata, vol. 20, no. 1, pp. 3–29, 2020.

\[5]   J. Ren, S. D. Lee, X. Chen, B. Kao, R. Cheng, and D. Cheung, “Naive Bayes Classification of Uncertain Data”, 2009.

\[6]   G. Dougherty, Pattern Recognition and Classification, New York: Springer, 2013.

\[7]   A. Palczewska, J. Palczewski, R. Marchese Robinson, and D. Neagu, “Interpreting Random Forest Classification Models Using a Feature Contribution Method”, in Advances in Intelligent Systems and Computing, Advances in Intelligent Systems and Computing, 2014, pp. 193–218.

\[8]   I. Ullah, B. Raza, A. K. Malik, M. Imran, S. U. Islam, and S. W. Kim, “A Churn Prediction Model Using Random Forest: Analysis of Machine Learning Techniques for Churn Prediction and Factor Identification in Telecom Sector”, IEEE Access, vol. 7, pp. 60134–60149, 2019.

\[9]   A. Idris, M. Rizwan, A. Khan, “Churn prediction in telecom using Random Forest and PSO based data balancing in combination with various feature selection strategies”, Computers & Electrical Engineering, vol. 38, pp. 1808-1819, 2012.

\[10]        Y. Yulianti and A. Saifudin, “Sequential Feature Selection in Customer Churn Prediction Based on Naive Bayes”, IOP Conference Series: Materials Science and Engineering, vol. 879 Issue 1 012090, 2020.

\[11]        M. Fridrich, “Experimental Parameter Tuning of Artificial Neural Network in Customer Churn Prediction”, Trends Economics and Management, vol. 11, no. 28, p. 9, 2017.

\[12]           T. U. o. Waikato, "Weka Documentation," \[Online]. Available: https://weka.sourceforge.io/doc.dev/overview-summary.html. \[Accessed 6 March 2022].

\[13]           V. Mallawaarachchi, “Introduction to Genetic Algorithms,” 8 July 2017. \[Online]. Available: https://towardsdatascience.com/introduction-to-genetic-algorithms-including-example-code-e396e98d8bf3. \[Accessed 6 March 2022].

\[14]           G. Chauhan, “All About Naïve Bayes,” 8 October 2018. \[Online]. Available: https://towardsdatascience.com/all-about-naive-bayes-8e13cef044cf#:\~:text=Real%20time%20Prediction%3A%20Naive%20Bayes,multiple%20classes%20of%20target%20variable.. \[Accessed 6 March 2022].

\[15]           T. Yiu, “Understanding Random Forest,” 12 June 2019. \[Online]. Available: https://towardsdatascience.com/understanding-random-forest-58381e0602d2#:\~:text=The%20fundamental%20concept%20behind%20random,of%20the%20individual%20constituent%20models.. \[Accessed 6 March 2022].

\[16]           J. Brownlee, “A Gentle Introduction to k-fold Cross-Validation,” 3 August 2018. \[Online]. Available: https://machinelearningmastery.com/k-fold-cross-validation/. \[Accessed 6 March 2022].

\[17]           Anon, “Comparing Two ROC Curves – Paired Design,” \[Online]. Available: https://ncss-wpengine.netdna-ssl.com/wp-content/themes/ncss/pdf/Procedures/NCSS/Comparing\_Two\_ROC\_Curves-Paired\_Design.pdf. \[Accessed 6 March 2022].
