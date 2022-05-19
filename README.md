# Credit-Card-Default-Payment-in-Taiwan

# Section 1. Introduction

# 1.1. Background 
 
In 2006, according to Eric Wang (2022), Taiwan's debt from credit and cash cards reached $268 billion, with more than half a million debtors unable to repay their loans. Consequently, the credit card debt and unemployment led to the suicide rate in Taiwan increasing by 22.9% from 2005 to 2006 and created other societal problems such as homeless. I-Cheng Yeh (2009) proclaims that Taiwan's credit and cash debt crisis was caused by banks over-issuing credit and cash cards to unqualified applicants in order to increase their market share. Concurrently, the majority of cardholders overused their credit card for consumption and amassed heavy debts. 

Therefore, it can be argued that the 2006 Taiwan debt crisis origins are akin to the 2008 global financial crisis that saw the United States unemployment rate reaching 10% and about 2.8 million Americans losing their homes to foreclosures (Singh, 2021). David Begg (2014) states that the global financial crisis was caused by risky lending by banks, such as sub-prime mortgages that were given to low-income, high-risk people who later defaulted on their mortgages.

Subsequently, I-Cheng Yeh (2009) asserts that a well-developed financial system utilises risk prediction to reduce the damages and uncertainty that led to Taiwan's debt and the global financial crisis. Risk prediction uses financial information, such as business financial statements, customer transactions and repayment records, to predict business performance or individual customers' credit risk. 

# 1.2. Aims and Objectives 

Consequently, this report aims to analyse the Credit Card Defaulter Prediction dataset (Topre, 2022) and predict the probability of default. Furthermore, this report compares the predictive accuracy of the probability of two data mining methods (decision trees and artificial neural networks) to select the best method to predict and score clients' risk.

# 1.3. Hypothesises 

This report hypothesises that debtors who are university educated, have a low amount of given credit, and can repay their debt duly in September (first payment required) are less likely to default. It can be argued that university-educated students have greater financial knowledge/skills and higher income/savings to repay their debt duly. In theory, having a low amount of given credit should be easier to repay. Moreover, being able to repay debt duly in the first month indicates the debtor's ability to pay and thus stop their debt from spiralling out of control, which would likely lead to defaulting.

# 1.4. Overview  

Firstly, section 2 utilises exploratory data analysis techniques to clean and understand the dataset. Section 2 then describes the data mining methods (decision trees and artificial neural networks) used to analyse the dataset and predict the probability of default. Section 3 illustrates the results from the exploratory data analysis and the data mining methods. Following, section 4 discusses the results and highlights the strengths and weaknesses of the analysis. Ultimately, section 5 summarises the key conclusions from the report.

# Section 2. Methods 

Michael Berry (2000) declares that data mining is the process of exploration and analysis of large quantities of data to discover meaningful patterns and rules. This report employs data mining methods, decision trees (classification tree, random forest and generalised boosted regression trees) and artificial neural networks to analyse the dataset and predict the probability of default. Firstly, the data cleaning and exploratory data analysis conducted in this report is described below, followed by a review of the methods of the data mining techniques employed. 

# 2.1 Exploratory Data Analysis 

The dataset had a total of 30,000 observations and 25 variables. The ID variable was removed as it is unnecessary for analysis and prediction. The binary variable – default payment (Yes = 1, No = 0), is the response variable. The remaining explanatory 23 variables are:   

- LIMIT_BAL: The amount of the given credit (NT dollar): it includes both the individual consumer credit and his/her family (supplementary) credit
- 	SEX (1 = male; 2 = female)
- 	EDUCATION (1 = graduate school; 2 = university; 3= high school; 4 = others)
- MARITAL SATUS (1 = married; 2 = single; 3 = others)
- AGE (year).
- PAY0: Repayment status in September, 2005 (-1=pay duly, 1=payment delay for one month, 2=payment delay for two months,8=payment delay for eight - months, 9=payment delay for nine months and above)
PAY2: Repayment status in August, 2005 (scale same as above)
PAY3: Repayment status in July, 2005 (scale same as above)
PAY4: Repayment status in June, 2005 (scale same as above)
PAY5: Repayment status in May, 2005 (scale same as above)
PAY6: Repayment status in April, 2005 (scale same as above)
- BILLAMT1: Amount of bill statement in September, 2005 (NT dollar)
BILLAMT2: Amount of bill statement in August, 2005 (NT dollar)
BILLAMT3: Amount of bill statement in July, 2005 (NT dollar)
BILLAMT4: Amount of bill statement in June, 2005 (NT dollar)
BILLAMT5: Amount of bill statement in May, 2005 (NT dollar)
BILLAMT6: Amount of bill statement in April, 2005 (NT dollar)
- PAYAMT1: Amount of previous payment in September, 2005 (NT dollar)
PAYAMT2: Amount of previous payment in August, 2005 (NT dollar)
PAYAMT3: Amount of previous payment in July, 2005 (NT dollar)
PAYAMT4: Amount of previous payment in June, 2005 (NT dollar)
PAYAMT5: Amount of previous payment in May, 2005 (NT dollar)
PAYAMT6: Amount of previous payment in April, 2005 (NT dollar)

Firstly, the summary function was used to summarise the 24 variables. The data summary shows each variable's median, mean, minimum and maximum values or outcomes to understand the data better. Consequently, the categorical variables were transformed into factors for the data to be suitable for the data mining techniques below. The dataset was then checked for missing data using a missmap, and for duplicated/wrong inputs, the get dupes and unique functions were used. Hence, observations that inputted '0' or are unknown for marriage and education were removed. 

Subsequently, a graphical matrix was utilised that produces scatter plots, histograms and Pearson correlation. The scatter plots illustrate the correlation, and the histograms highlight the explanatory variables' distributions to comprehend the data better and check for potential outliers. Whereas the Pearson correlation checks for collinearity/multicollinearity of the explanatory variables. Additionally, bar graphs, box plots, and pie charts are also employed to check for outliers to understand the data better.   

# 2.2. Decision Trees

Data flair states that 'decision trees are a data mining technique that uses a tree-like structure to deliver consequences based on input decisions' (Data Flair, 2022). Moreover, decision trees are supervised learning algorithms that can perform regression and classification problems. This report employs three types of decision trees: classification tree, random forest and generalised boosted regression tree.

# 2.2.1. Classification Tree

Classification trees predict a qualitative response by using a binary decision (yes or no) to grow a classification tree. The classification tree aims to predict the number of defaults based on the other variables. In order to find rules that are generalisable and stop the model from overfitting, the classification tree model was created with a minim split of two and the complexity parameter of zero to create the most complex possible tree.

# 2.2.2. Random Forest 

Victor Ivamoto (2020) proclaims that the name random forest derives from the random process of splitting the data and creating many trees, or a forest. Additionally, Ivamoto states that random forests are better at prediction over classification trees by averaging multiple decision trees. Random forests create several random subsets of the data and calculates the classification trees; thus, the result is the average of all trees.

# 2.2.3. Generalised Boosted Regression Tree

Generalised Boosting Models (GBMs) repeatedly fit many decision trees to improve the accuracy of the model. While random forests build deep independent trees, GBMs build shallow successive trees with each tree learning and improving form the previous tree. Appendix 6.1 illustrates how the optimal GBM model was created. 

# 2.3. Neural Network

Avinash Navlani asserts that a: 

‘Neural network is a set of connected input/output units in which each connection has a weight associated with it. In the learning phase, the network learns by adjusting the weights to predict the correct class label of the given inputs’ (Navlani, 2019).

Appendix 6.2 shows the method how the best fitting model was created and selected. 

# 2.4. Model Evaluation 

Before the models are created, the data is split into train and test sets (70/30 split) for model validation and prediction tests. To evaluate the models, a confusion matrix is used to highlight a model’s accuracy, sensitivity and specificity. Additionally, a ROC curve showing the models AUC is employed to evaluate a models predictive power. 

# Section 3. Results 

This section displays the model results and discusses their performances. The models are applied to predicting default, allowing the comparison of different models by utilising confusion matrixes, ROC curves and variable importance graphs. However, the results of the exploratory data analysis are presented first below. 

# 3.1 Exploratory Data Analysis 

Figure 1. Data Summary 

<img width="365" alt="image" src="https://user-images.githubusercontent.com/97530878/169292596-f128bc54-6ec5-4e41-9e4e-e0052ba6950a.png">

Figure 1 illustrates the 24 variables as discussed above. The data summary shows each variable's median, mean, minimum and maximum values or outcomes to understand the data better. Consequently, the categorical variables were transformed into factors for the data to be suitable for the data mining techniques below. Additionally, the summary highlights that for variables education and marriage, there were observations that were '0' or unknown, and thus these observations were removed.

Figure 2. Missingness Map 

<img width="423" alt="image" src="https://user-images.githubusercontent.com/97530878/169292651-ceb644d3-304e-42c0-b0f2-5875259b5231.png">

Peng (2013) asserts that missing data can decrease statistical power, increase standard errors, and weaken generalisability. Therefore, a missing plot (figure 2) was employed to check for missing data. The x-axis shows the variables, and the y-axis displays the observations. If there were missing data, the block would be red. Nonetheless, all the blocks are blue, highlighting no missing data to be cleaned.

Figure 3. Scatter Plot Matrix 

<img width="459" alt="image" src="https://user-images.githubusercontent.com/97530878/169292673-0f3e9a99-a132-484f-bd3b-1e07abc21e68.png">

Figure 3 above checks for collinearity and multicollinearity of the non-categorical explanatory variables. Figure 3 displays that some of the absolute values of the correlation are greater than 0.9 between variables. For instance, variables BILL_AMT4 and BILL_AMT5 have the strongest correlation of 0.94Therefore, these variables are highly correlated or have a strong linear relationship, indicating collinearity issues. Nevertheless, the majority of variables have low correlations with each other. Additionally, figure 3 highlights the distribution of each variable, showing that the overwhelming majority of the variables are skewed and do not follow the assumptions of normal distribution.

Figure 4. Variable Analysis 

<img width="406" alt="image" src="https://user-images.githubusercontent.com/97530878/169292724-8993b48b-f31a-4040-928a-ff40c9be035a.png">

Figure 4 highlights that most individuals are university educated, single and female. Figure.4d illustrates that the age of individuals ranges from 21 to 79 and that the median age (middle value) is around 35. The dots above the maximum line are suggested to be outliers. However, these values seem reasonable as they are the typical and appropriate age for someone to have a credit card (age would be an outlier if under 18 and potential over 100 years old).

Figure 5. Number of defaults 

<img width="255" alt="image" src="https://user-images.githubusercontent.com/97530878/169292767-183305ba-a2cd-4d7a-8c4f-9e3c4b1a2238.png">

Figure 5 shows that majority of observations did not default. 77.7% (22,996) of individuals did not default compared to just 22.3% (6,605) who defaulted.  

Figure 6. Variables and Default 

<img width="410" alt="image" src="https://user-images.githubusercontent.com/97530878/169292800-22c6da22-1235-4650-bfbf-0f2c619d852e.png">

Figure 6 exhibits the default level between different sexes, education levels, marital statuses and ages. At first glance, it can be argued that a young female who is university educated is more likely to default. Consequently, this assumption goes against this repots hypothesis. Nevertheless, as illustrated in figure 4, most observations are female and university-educated, thus skewing the results. The number of defaults for all variable groups is very similar, suggesting that sex, education level, marital status, and age have little impact or importance in predicting individuals who are more likely to default.

# 3.2. Decision Trees

# 3.2.1. Classification Tree

Figure 7. Classification Tree Confusion Matrix 

<img width="205" alt="image" src="https://user-images.githubusercontent.com/97530878/169292861-c490e996-1c46-450d-a1fd-56d6b141cdfe.png">

Figure 7 shows the predictions of the classification tree using the test set. The classification tree model correctly predicted 99% of defaulters and indicating that the model has great prediction accuracy. 

Figure 8.  Classification Tree ROC Curve 

<img width="448" alt="image" src="https://user-images.githubusercontent.com/97530878/169292886-ae235b92-a5b1-43fd-b9c1-01ccefc75474.png">

Figure 8 shows a ROC curve that evaluates the prediction accuracy of the model. The ROC curve portrays the trade-off between the sensitivity (true positive rate) and specificity (false positive rate), as shown in the confusion matrix. The AUC evaluates the model performance. The AUC value ranges between 0 and 1, with the higher AUC showing a better performance of a model differentiating between the positive and negative classes. Consequently, the classification tree has an AUC score of 0.99 and thus can differentiate between the positive and negative classes. Therefore, the model fits the data well and has a very good predication accuracy. 

Figure 9. Decision Tree Variable Importance 

<img width="457" alt="image" src="https://user-images.githubusercontent.com/97530878/169292941-e0836ad0-20bd-4b9c-aa54-cd67785079b6.png">

Figure 9. displays the importance of each variable that has an influence on defaulting. However, figure 9 shows that marital status and sex have little importance on predicting defaulting as illustrated by figure 6. 

# 3.2.2. Random Forest 

Figure 10. Random Forest Confusion Matrix 

<img width="185" alt="image" src="https://user-images.githubusercontent.com/97530878/169293017-5d4c9836-0dcd-4d53-addd-be6228560f2a.png">

Figure 10 shows the predictions of the classification tree using the test set. The random forest model correctly predicted 82% of defaulters and indicating that the model has great prediction accuracy. 

Figure 11. Random Forest ROC Curve 

<img width="454" alt="image" src="https://user-images.githubusercontent.com/97530878/169293083-f3b36644-b8b2-49c9-86b6-e86468089723.png">

Figure 11 shows that the random forest has an AUC score of 0.76 and thus can differentiate between the positive and negative classes. Therefore, the model fits the data well and has a decent predication accuracy. 

Figure 12. Random Forest Variable Importance 

<img width="443" alt="image" src="https://user-images.githubusercontent.com/97530878/169293128-dfc54f5c-0e5f-4952-a72f-1cd8ca861508.png">

Figure 12 shows that marital status, education level and sex have little importance on predicting defaulting akin to the classification trees findings.

# 3.2.3. Generalised Boosted Regression Tree

Figure 13. Generalised Boosted Regression Tree Confusion Matrix 

<img width="194" alt="image" src="https://user-images.githubusercontent.com/97530878/169293162-d97fbd1e-b36b-4a45-8c5b-2b356f3ae84b.png">

Figure 13 shows the predictions of the classification tree using the test set. The GBM model correctly predicted 77% of defaulters and indicating that the model has great prediction accuracy. 

Figure 14. Generalised Boosted Regression Tree ROC Curve 

<img width="393" alt="image" src="https://user-images.githubusercontent.com/97530878/169293229-913da466-0417-4ebf-ae86-39ef8794522f.png">

Figure 14 displays that the GBM model has an AUC score of 0.78 and thus can differentiate between the positive and negative classes. Therefore, the model fits the data well and has a decent predication accuracy. 

Figure 15. Generalised Boosted Regression Tree Variable Importance  

<img width="396" alt="image" src="https://user-images.githubusercontent.com/97530878/169293602-3bf6bec8-2229-487e-a091-aeba86934bdd.png">

The GBM unlike the other decision trees indicates that the variables have less significance in being able to predict defaulting. However, the order of importance is akin to the random forest model. 

# 3.3 Neural Network

Figure 16. Best Fitting Model 

<img width="399" alt="image" src="https://user-images.githubusercontent.com/97530878/169293662-3695c5dd-327c-43a0-8461-ccbe7497ada6.png">

Figure 17. Neural Network Confusion Matrix

<img width="175" alt="image" src="https://user-images.githubusercontent.com/97530878/169293696-69ff9bb3-aaf2-4c9d-9d31-4c1b426df83a.png">

Figure 17 shows the predictions of the classification tree using the test set. The neural network model correctly predicted 80% of defaulters and indicating that the model has great prediction accuracy. 

Figure 18. Neural Network ROC Curve 

<img width="425" alt="image" src="https://user-images.githubusercontent.com/97530878/169293735-3ad66dec-c065-4b26-a6f6-d2e4c17221e5.png">

Figure 18 highlights that the neural network has an AUC score of 0.72 and thus can differentiate between the positive and negative classes. Therefore, the model fits the data well and has a decent predication accuracy.

Figure 19. Neural Network Variable Importance 

<img width="436" alt="image" src="https://user-images.githubusercontent.com/97530878/169293790-10879384-fa3a-4709-8533-e68a49b6d4af.png">

# Section 4.0 Discussion 

Best Model/ important variables (hypothesis test)

<img width="448" alt="Screenshot 2022-05-19 at 13 32 26" src="https://user-images.githubusercontent.com/97530878/169293882-4bd07842-2261-4656-8c2f-f43b96617f36.png">

Table1 exhibits that the classification tree is the best model for predict and score clients' risk. The classification tree had the best accuracy, sensitivity, specificity and AUC score.  

This report hypothesises that debtors who are university educated, have a low amount of given credit, and can repay their debt duly in September (first payment required) are less likely to default is partial correct. The variable of importance for each model suggests that education and low amount of given credit are do not impact the risk of defaulting. However, for all models the debtors ability to pay duly in in September (first payment required) is significant in predicting the risk of an individual defaulting. 


# Appendix 

# Method:  Generalised Boosted Regression Tree

Figure 20. Training and cross-validated MSE as n trees are added to the GBM algorithm

<img width="443" alt="image" src="https://user-images.githubusercontent.com/97530878/169294125-37b7cf50-b842-4590-ace2-b3b604d95264.png">

get MSE and compute RMSE
0.3662737
plot error curve
189

Figure 21. Optimal Learning Rate

<img width="239" alt="image" src="https://user-images.githubusercontent.com/97530878/169294182-305ce186-e4ad-40d6-a21e-d3e0d7143e41.png">

Figure 22. Best Hyperparameter Settings

<img width="275" alt="image" src="https://user-images.githubusercontent.com/97530878/169294219-94fda505-3d80-4791-a988-aef070b223b2.png">

# Method: Neural Network

Methods to Assess Models Performance 

<img width="196" alt="image" src="https://user-images.githubusercontent.com/97530878/169294299-fac895f0-6cad-4772-8432-29d58c62fc74.png">

Figure 23. Neural Network Models 

<img width="582" alt="image" src="https://user-images.githubusercontent.com/97530878/169294325-c9b0ec01-86d5-421d-9b3e-a6dbbcf0d33e.png">

Figure 24. Neural Network Model Quality of Fit 

<img width="397" alt="image" src="https://user-images.githubusercontent.com/97530878/169294355-b0420165-c575-4221-8f61-2fad19031eb4.png">

# BIBLIOGRAPHY

Data Flair , 2022. R Decision Trees – The Best Tutorial on Tree Based Modeling in R!. [Online] 
Available at: https://data-flair.training/blogs/r-decision-trees/
[Accessed 28 March 2022].
David Begg, G. V. S. F. R. D., 2014. economics. 11 ed. New York : McGraw-Hill Education .
I-Cheng Yeh, C.-h. L., 2009. The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients. Expert Systems with Applications, Volume 36, pp. 2473-2480.
Ivamoto, V., 2020. Wine Type and Quality Prediction With Machine Learning. [Online] 
Available at: https://rstudio-pubs-static.s3.amazonaws.com/565136_b4395e2500ec4c129ab776b9e8dd24de.html#246_classification_and_regression_trees
[Accessed 28 March 2022].
Le, J., 2018. R Decision Trees Tutorial. [Online] 
Available at: https://www.datacamp.com/community/tutorials/decision-trees-R
[Accessed 28 March 2022].
Linoff, M. A. B. a. G., 2000. Mastering Data Mining: The Art and Science of Customer Relationship Management. New York : John Wiley & Sons, Inc.
Singh, M., 2021. The 2007–2008 Financial Crisis in Review. [Online] 
Available at: https://www.investopedia.com/articles/economics/09/financial-crisis-review.asp#citation-20
[Accessed 28 March 2022].
Topre, G., 2022. Credit Card Defaulter Prediction. [Online] 
Available at: https://www.kaggle.com/datasets/gauravtopre/credit-card-defaulter-prediction
[Accessed 28 March 2022].
Wang, E., 2022. Taiwan’s Credit Card Crisis, Kansas City : Seven Pillars Institute.





























