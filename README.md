# Agent-Bonus-Prediction


INTRODUCTION

Insurance in India and everywhere else is used to cover the financial risk or the loss that the policy holder may have to face if they are involved in an incident that results in property, physical or any other damage. 
A policy holder will typically pay’s insurer a month/annual fee which is also called a insurance premium. The insurance premium paid by the owner is determined by taking several parameters into consideration such as the customers marital status, credit history, whether the customer has an owned or rented accommodation, owners age ,gender and their previous history, the geographic details of the owner etc. Based on these factors an insurance company will increase premium or offer discounts based on the level of risk. 

Background 

An insurance broker makes money off commissions from selling insurance to individuals or businesses. Most commissions are between 2% and 8% of premiums, depending on state regulations. Brokers sell all insurance types, including health insurance, homeowner insurance, accident insurance, life insurance, and annuities.

In this project we are working on insurance sales dataset wherein we have several information’s about the customers profile, their income, existing product type, sum assured, no. of policy, channel availed in other words whether the policy taken was through agent or third party and the bonus of the agents etc .

Objective

The company wants to predict the bonus for its agents given the existing data so that it may design appropriate engagement activity for their high performing agents and upskill programs for low performing agents.

This insight can help the business multiply its profits by generating more sales through incentivizing insurance agents, on the other hand the agents are also motivated to perform and work for the extra bonus which be financially helpful for meeting third day to day needs. The analysis would also focus on the non performing agents who have sold lower policy’s and try to understand the reasons and areas of improvement .


Data set

The data contains the customer record’s collected overtime as when they were sold the insurance . It consists of 4520 observations and 19 variables/ columns which is a panel data and not a time series data. There are 4520 customers records identified through their unique ID’s. There are details of customers personal and demographic information, along with the types of policy, frequency and sum insured of policy. 

There are 8 object types , 5 integer and 7 float type variables described as below :


 
Table 1:Data Dictionary

After the initial data inspection we saw that there are several missing values present in few variables like Age (269) ,Cust Tenure (226), number of policy (45), monthly income (236), existing policy tenure (185), sum assured (154), CustCareScore (52).

Let’s go ahead and describe all the numerical variables to understand more about the data:

 
Table 2:Numerical Data Description

From the above table we can see that : 
o	there are 4520 Customer ID’s which are unique and not duplicated.
o	Agents maximum bonus received is 9608 and minimum being 1605 indicating there are outliers and that some agents are performing lot better than others 
o	The oldest customer in the dataset is 58 year old and minimum age shown is 2 which can be a error .
o	The tenure customer opted for are maximum 57 and minimum 2 , with 50% of the customer opting for 13
o	The maximum types of products is 6 and minimum 1 , 50% customers have at least 4 types of insurance and the same stands for the number of policy taken by customers.
o	Monthly income of the customers in the data set is 22890 on an average, but there are several outliers which can be seen as the median is at 21606
o	We can see that the customers have had much of complaints registered.
o	There are max 25 yearlong tenures for existing policy , 50% of them have at least 3 years long tenure from the existing policy
o	The max sum assured is 18,38,496 is all existing policies of customers , 50% of them have a sum assured of 578976.5
o	Maximum call to customer for cross sell has been 18 and 5 on an average .

Let’s describe the categorical variables and understand the data further :

 
Table 3:Data Description of categorical variables
The data above gives us the following information:
o	There are 3 channels of sales , Agent , Online and Third Party partner
o	The description shows there are 5 unique occupations that the customer in the dataset are doing namely Free lancers, Salaried, Large Business & Small Business, one of category is a spelling error mentioned as ‘laargebusiness’ and needs to corrected.
o	EducationField shows 7 unique categories which includes several erroneously entered values and needs to be corrected.
o	Gender shows 3 unique values again which needs to be corrected.
o	Designation variable shows 6 distinct job roles out of which Manager is the most frequent occurring in the dataset
o	Most of the customer in the dataset are either divorced , single or married . The fourth category say unmarried which can be included under single status .
o	There are 4 zones and most of the customers seem to be from the West
o	Most frequently opted payment method by customers are Half Yearly , with other option being Monthly quarterly and yearly .


Exploratory Data Analysis

Univariate analysis of the numerical variables :

Description of AgentBonus
-----------------------------------------------------------------------
count    4520.000000
mean     4077.838274
std      1403.321711
min      1605.000000
25%      3027.750000
50%      3911.500000
75%      4867.250000
max      9608.000000
Distribution of AgentBonus            Box Plot of Agent Bonus
-----------------------------------------------------------------------
   
Figure 1:Distribution and Bos Plot of Agent Bonus

The distribution shows that there is a slight skewness with the presence of outlier in the data, but the mean and median are nearly close to each other. Minimum bonus received by an agent is 1605, and maximum is 9608.




















Description of Age
----------------------------------------------------------------------------
count    4251.000000
mean       14.494707
std         9.037629
min         2.000000
25%         7.000000
50%        13.000000
75%        20.000000
max        58.000000
      Distribution of Age                      Box Plot of Age
-----------------------------------------------------------------------
  
Figure 2:Distribution and Box Plot Age

We can that the age variable is skewed to the right with the presence of outlier. The minimum age shown here is 2 and it also says that the 50% of the customers in the dataset are aged 13 and 75% 20 , which seems very strange and needs to be treated with alternate information available or dropped before the analysis .

























Description of CustTenure
-----------------------------------------------------------------------
count    4520.000000
mean       14.395575
std         8.742521
min         2.000000
25%         8.000000
50%        13.000000
75%        19.000000
max        57.000000 
Distribution of CustTenure                Box Plot of CustTenure
-----------------------------------------------------------------------
   
Figure 3:Distribution and Box Plot Customer Tenure

The distribution shows that there are outliers in the data with right skewness. Highest Tenure being 57 and lowest 2 .

Description of ExistingProdType
-----------------------------------------------------------------------
count    4520.000000
mean        3.688938
std         1.015769
min         1.000000
25%         3.000000
50%         4.000000
75%         4.000000
max         6.000000
Distribution of ExistingProdType        Box Plot of ExistingProdType
-----------------------------------------------------------------------
   
Figure 4:Distribution and Box Plot Existing Product Type
The plots above in figure 4 tell us that there are 6 product types , and most of the customer in the dataset have 4 types of product.

Description of NumberOfPolicy
-----------------------------------------------------------------------
count    4520.000000
mean        3.569690
std         1.449302
min         1.000000
25%         2.000000
50%         4.000000
75%         5.000000
max         6.000000
Distribution of Number Of Policy.   Box Plot of Number Of Policy
-----------------------------------------------------------------------
   
Figure 5:Distribution and Box Plot of Number of Policy
The above figure 5 shows us how many policy customers have at a time. While there are customers with 6 policies , most of them in the dataset have 4 .
Description of MonthlyIncome
-----------------------------------------------------------------------
count     4520.000000
mean     22823.253097
std       4764.892420
min      16009.000000
25%      19858.000000
50%      21606.000000
75%      24531.750000
max      38456.000000
Distribution of Monthly Income          Box Plot Of Monthly Income
-----------------------------------------------------------------------
   
Figure 6:Distribution and Box plot of Monthly Income

The plots above on monthly income tell us about the income distribution of customers in the dataset which are right skewed indicating there are outliers in the data .The minimum salary earned in this data is 16009 and the maximum is 38,456 .

Description of Complaint
-----------------------------------------------------------------------
count    4520.000000
mean        0.287168
std         0.452491
min         0.000000
25%         0.000000
50%         0.000000
75%         1.000000
max         1.000000
Distribution of Complaint             Box Plot of Complaint
-----------------------------------------------------------------------
  
Figure 7:Distribution and Box Plot Complaint

This plot gives us a picture of the complaints that has been received and we cansee that there are not much as 50% of the customers have 0 complaints registered. We can think of dropping this variable for future analysis .

Description of ExistingPolicyTenure
-----------------------------------------------------------------------
count    4520.000000
mean        4.084071
std         3.285152
min         1.000000
25%         2.000000
50%         3.000000
75%         5.000000
max        25.000000
Distribution of ExistingPolicyTenure   Box Plot of ExistingPolicyTenure
-----------------------------------------------------------------------
   
Figure 8:Distribution and Box Plot of Existing Policy Tenure
The existing policy tenure is 25 at maximum and 1 being the lowest, clearly indicating the skewness.

Description of SumAssured
----------------------------------------------------------------------
count    4.520000e+03
mean     6.186020e+05
std      2.421172e+05
min      1.685360e+05
25%      4.444762e+05
50%      5.789765e+05
75%      7.500105e+05
max      1.838496e+06
Distribution of SumAssured              Box Plot of Sum Assured
-----------------------------------------------------------------------
   
Figure 9:Distribution and Box Plot of Sum Assured
The graph shows the distribution of the sum assured  which is right skewed, indicating outliers as we can see in the box plot. This means that there are customers with  very high amount of sum assured and low
Description of LastMonthCalls
-----------------------------------------------------------------------
count    4520.000000
mean        4.626991
std         3.620132
min         0.000000
25%         2.000000
50%         3.000000
75%         8.000000
max        18.000000
Distribution of Last Month Calls           Box Plot of Last Month Calls
-----------------------------------------------------------------------
  
Figure 10:Distribution and Box Plot of Last Month Calls

The above figure 10 shows the call made to customers in the last month for cross sell. The max call being 18 times and there are some customers to whom the calls were not made at all.

Description of CustCareScore
----------------------------------------------------------------------
count    4520.000000
mean        3.066814
std         1.375007
min         1.000000
25%         2.000000
50%         3.000000
75%         4.000000
max         5.000000
Distribution of Cust Care Score    Box Plot of CustCareScore
-----------------------------------------------------------------------
   
Figure 11:Distribution and Box Plot of Customer Care Score
The graph shows us the customer care score which ranges from 1 to 5 .
Analysis the categorical variable  :

 	 
Figure 12 :Count Plot of 'Channel' and 'Education'
The count plot above for channel indicates that customers buy insurance products through agents more than third party partner and online services .
The education field graph shows that there are more than 300 under graduates customers in the dataset.


   
Figure 13 : Count Plot of Designation and Marital Status
The figure above shows that most customers in the dataset are working as Executive , followed by Managers. 
Marital Status plot tells us that most customers are married .

   
Figure 14:Count Plot of Zone and Occupation
From the above plot it can be inferred that most customers in the dataset are from West and North .Also, most of the customers in the data are salaried individuals .
   
Figure 15: Count Plot of Payment Method and Gender

Figure 15 tells us that the preferred payment method of customers are Half yearly followed by yearly . The second figure shows that data is dominated by makes customers .


Bivariate analysis:



 
Figure 16:Heat Map


 
Figure 17:Pair Plot of variables

The heat map in figure 16 and the pair plot in figure 17 shows the relationship between the different variables. It can be noted that there is significant correlation between several variables as below :
o	Age and Agent Bonus
o	CustTenure and Agent bonus
o	Monthly Income Agent Bonus
o	Sum Assured and Agent Bonus
o	Sum Assured and Cust Tenure
o	Sum Assured and Monthly Income

From the above the most significant corelation noted was that of Sum Assured and Agent Bonus , indicating if the Sum assured increased the agent Bonus also increases .
DATA CLEANING AND PREPROCESSING

Removal of unwanted variables : 

The variable Age has figures entered erroneously as discussed earlier 75% of the customer in the dataset are shown to be as 20 year old which cannot be the scenario given the variables of education and occupation details where its mentioned that most of the customers are undergraduates or working class executives and managers .

Similarly the Variable Complaint has very 75% customers who have not complained and 25% with complaint registered has I have chosen to remove that variable as it would not be significant in the analysis .

Missing value treatment : 

There are values missing for several variables as below :

CustID	0
AgentBonus	0
Age	269
CustTenure	226
Channel	0
Occupation	0
EducationField	0
Gender	0
ExistingProdType	0
Designation	0
NumberOfPolicy	45
MaritalStatus	0
MonthlyIncome	236
Complaint	0
ExistingPolicyTenure	184
SumAssured	154
Zone	0
PaymentMethod	0
LastMonthCalls	0
CustCareScore	52

I have imputed the missing observations variables CustTenure, NumberOfPolicy, Monthly Income, ExistingPolicyTenure, Sum Assured  and CustCareScore with the median value.
Please note the column Age is been dropped from further analysis .


Variables Transformation:

The categorical variables had some observation with spelling mistakes which has been corrected and included in the correct category .
For example the gender value had observations as ‘Fe male’ and ‘Female’ for which I have replaced all the ‘Fe male’ to ‘Female’.
Another being the EducationField wherein Customers were marked as ‘Graduates’ and ‘undergraduates’ category . I have included the Graduates under ‘undergraduates’ and marked them same category .	
Similarly with Marital Status variable, wherein I have included Single and Unmarried category as one .

SHAPIRO TEST 

I have performed the shapiro test on Agent Bonus variables and was returned a p value of 1.418, which is greater than the confidence level of 0.05 , and hence indicates that the data is normally distributed .

Therefore I can say there is no imbalance in the data .
MODEL BUILDING

We will be building multiple Linear Regression and Random Forest Models using different methods and ensemble techniques such as ordinary least square method, Gradient Descent Method , Grid Search CV . We will be fine tuning the model to achieve the best fit model.

MODEL 1

LINEAR REGRESSION

OUTLIERS AND TREATMENT
As we saw in the Exploratory Data analysis that we have many outliers in the data set  which might be misleading as the data tends to become bias depending on the mean, we will be performing the outlier treatment using Inter quartile range calculation.
ENCODING:
Once we have performed the outlier treatment, we will move ahead with one hot encoding because of data bias within the variables . Since Linear Regression model might understand the data in the variables as ordinal values.
For Model 1,  we performed One Hot Encoding using ‘get dummies’ function and only removed the ‘CusID’ column from the data as it has no value addition to the analysis , now the shape of the dataset is 4520 observations and 32 columns .
TEST AND TRAINING SET
We now divide these into training and test set in the split of 70:30 . keeping the Random state figure as ‘123’ . The X-train set has 3164 observation and test set has 1356 observation . X has all the independent variables and Y has the dependent variables ‘Agent Bonus’ .
SCALING
We have scaled the dataset using Standard Scaler function after splitting the data into train and set.
GRADIENT DESCENT METHOD

COEFFICIENTS
After applying the regression model using scikit learn we go ahead and find the coefficients of each independent variable as below :

The coefficient for CustTenure is 27.44889970400817
The coefficient for ExistingProdType is 71.15795255318704
The coefficient for NumberOfPolicy is -2.601341486453725
The coefficient for MonthlyIncome is 0.031038896075320954
The coefficient for ExistingPolicyTenure is 40.17156149919149
The coefficient for SumAssured is 0.003829568938272132
The coefficient for LastMonthCalls is -2.5706596292396346
The coefficient for CustCareScore is 11.301506937205206
The coefficient for Channel_Online is -8.921734888676353
The coefficient for Channel_Third Party Partner is 7.977472852479893
The coefficient for Occupation_Large Business is -557.6310192368464
The coefficient for Occupation_Salaried is -576.3021171792329
The coefficient for Occupation_Small Business is -570.673647224353
The coefficient for EducationField_Engineer is -15.49508462823721
The coefficient for EducationField_MBA is -168.3819417533866
The coefficient for EducationField_Post Graduate is 2.3517333354416556
The coefficient for EducationField_Under Graduate is 15.699510836057396
The coefficient for Gender_Male is -4.93443388608597
The coefficient for Designation_Executive is -540.1612141416732
The coefficient for Designation_Manager is -489.4938709397874
The coefficient for Designation_Senior Manager is -273.50944317251714
The coefficient for Designation_VP is 35.571056843262305
The coefficient for MaritalStatus_Married is -54.91568027011717
The coefficient for MaritalStatus_Single is 2.3509077325318346
The coefficient for Zone_North is -121.82715470544562
The coefficient for Zone_South is -76.8247794179503
The coefficient for Zone_West is -98.51043707786657
The coefficient for PaymentMethod_Monthly is 273.7555344615456
The coefficient for PaymentMethod_Quarterly is 165.65791302387157
The coefficient for PaymentMethod_Yearly is -80.47115110513526

INTERCEPT
The Intercept of our model is 1296.01, which means when X for example is any of the attributes such as CustTenure, Existing Product Type, Number of Poilicy, Monthly Incomes, etc including all the features is 0 then the agent bonus will be 1296 which can be possible absurd sometimes. 

R SQAURE
 
The Linear Regression model score or the R square for the training set 0.78 and for the test set is 0.79 indicting the model to be on the right fit zone.

The RMSE score on the training set is 635 , and test set is 614. 

R^2 is not a reliable metric as it always increases with addition of more attributes even if the attributes have no influence on the predicted variable. Instead we use adjusted R^2 which removes the statistical chance that improves R^2 . Scikit does not provide a facility for adjusted R^2 so we use statsmodel, a library that gives results similar to what you obtain in R language. This library expects the X and Y to be given in one single dataframe, hence we concat the X&Y data .

ORDINARY LEAST SQAURE METHOD

Using OLS method we will try to build the model and pull out the intercepts and coefficients to compare the regression models.

As we can see in the inferential statistics for Model 1 in the table below, the intercepts and coefficients are similar to what we had seen in the Gradient Descent Model.

We can see that we have derived almost the same observation for r squared as 0.784 and the ajusted R squared which removes the statistical fluke from R squared to give us more reliability about the performance of the model is 0.782, which seems to be a good indication of the performance of the model as the closer the adjuted R sqaure is to 1 the better the model. This simply means that the model is able to explain 78% of the dataset.
In the above model the null hypothesis claims that the relationship between the dependent variable y and the independent variable X does not exist. Since the P(F-statistic) the p value is less that 0.05 hence at 95% confidence level we say that there is some relationship between the dependent and independent variable.
The P value zero in all individual variables suggests that all of those variables are good for our prediction and have some influence on the Agent Bonus in the real world .
However, the variable with higher-P value indicate that they are not the strong predictors of  the dependent variables and therefore we will try and exclude such variables and build another model to achieve a better score and check how the model performance changes.

 

Table 2:Linear Regression model 1 using statistical method








MODEL 2


OUTLIERS AND TREATMENT
As discussed earlier in the Exploratory Data analysis and model 1  that we have many outliers in the data set  which might be misleading as the data tends to become bias depending on the mean, hence will be performing the outlier treatment using Inter quartile range calculation.
ENCODING:
For Model 2 we are performing the encoding using ‘get dummies’ function which is One Hot Encoding and removing various variables which were not of much significance when observed under MODEL 1. Now the new variables dropped for building model 2  are ‘Number Of Policy’ , ‘Last Month Calls’, ‘Channel Online’, ‘Channel online’, ’Channel Third Party’, Education Field Engineer’, ‘Education Field Under graduate’, Education Field Post Graduate’, ‘Designation VP’, ‘marital Status Single’, ‘Gender Male’ columns from the data as it has no value addition to the analysis , now the shape of the dataset is 4520 observations and 21 columns .
TEST AND TRAINING SET
We now divide these into training and test set in the split of 70:30 . keeping the Random state figure as ‘123’ . The X-train set has 3164 observation and test set has 1356 observation . X has all the independent variables and Y has the dependent variables ‘Agent Bonus’ .
SCALING
We have scaled the dataset using Standard Scaler function after splitting the data into train and set.
GRADIENT DESCENT METHOD

COEFFICIENTS
After applying the regression model using scikit learn we go ahead and find the coefficients of each independent variable as below :
The coefficient for CustTenure is 27.441744297349324
The coefficient for ExistingProdType is 65.34780877705002
The coefficient for MonthlyIncome is 0.031753131381774935
The coefficient for ExistingPolicyTenure is 39.94007265248912
The coefficient for SumAssured is 0.0038324602190584756
The coefficient for CustCareScore is 11.309135041168425
The coefficient for Occupation_Large Business is -580.2851307034616
The coefficient for Occupation_Salaried is -568.7729753485979
The coefficient for Occupation_Small Business is -565.4853088890602
The coefficient for EducationField_MBA is -180.48914638890437
The coefficient for Designation_Executive is -536.0001992774328
The coefficient for Designation_Manager is -494.1003976741626
The coefficient for Designation_Senior Manager is -284.0062170630165
The coefficient for MaritalStatus_Married is -56.78029022779614
The coefficient for Zone_North is -125.84132637836309
The coefficient for Zone_South is -82.90139646066227
The coefficient for Zone_West is -101.15089769837851
The coefficient for PaymentMethod_Monthly is 262.3581702943045
The coefficient for PaymentMethod_Quarterly is 156.0341658540828
The coefficient for PaymentMethod_Yearly is -74.4069204808571


INTERCEPT
The Intercept of our model is 1290.97, which means when X for example is any of the attributes such as CustTenure, Existing Product Type, Number of Poilicy, Monthly Incomes, etc including all the features is 0 then the agent bonus will be 1290.

R SQAURE
 
The Linear Regression model score or the R square for the training set  0.78 and for the test set is 0.79 indicting the model to be on the right fit zone. These score are the same as the scores in model 1 indicating no change in model performance

The RMSE score on the training set is 635 , and test set is 614. 

R^2 is not a reliable metric as it always increases with addition of more attributes even if the attributes have no influence on the predicted variable. Instead we use adjusted R^2 which removes the statistical chance that improves R^2 . Scikit does not provide a facility for adjusted R^2 so we use statsmodel, a library that gives results similar to what you obtain in R language. 
This library expects the X and Y to be given in one single dataframe, hence we concat the X&Y data .

ORDINARY LEAST SQAURE METHOD

Using OLS method we will try to build the model and pull out the intercepts and coefficients to compare the regression models.

As we can see in the inferential statistics for Model 2 in the table below, the intercepts and coefficients are similar to what we saw in the Gradient Descent Model.

We can see that we have derived almost the same observation for r squared as 0.784 and the ajusted R is 0.782 .

 
Figure 18:Scatter plot of Best Fit Line
 
Table 3: Inferential statistics of Model 2

The Linear Regression equation of the second model is 
(1290.97) * Intercept + (27.44) * CustTenure + (65.35) * ExistingProdType + (0.03) * MonthlyIncome + (39.94) * ExistingPolicyTenure + (0.0) * SumAssured + (11.31) * CustCareScore + (-580.29) * Occupation_Large_Business + (-568.77) * Occupation_Salaried + (-565.49) * Occupation_Small_Business + (-180.49) * EducationField_MBA + (-536.0) * Designation_Executive + (-494.1) * Designation_Manager + (-284.01) * Designation_Senior_Manager + (-56.78) * MaritalStatus_Married + (-125.84) * Zone_North + (-82.9) * Zone_South + (-101.15) * Zone_West + (262.36) * PaymentMethod_Monthly + (156.03) * PaymentMethod_Quarterly + (-74.41) * PaymentMethod_Yearly + 


MODEL INTERPRETATION
Thus the model explains that when Customer Tenure increases by 1 unit, Agent Bonus increases by 27.44 units, keeping all other predictors constant.
Similarly, when Payment Method Montly increases by 1 unit, Agent Bonus increases by 262.36 units, keeping all other predictors constant.
There are also some negative co-efficient values, for instance, ‘Designation Manager has its corresponding co-efficient as -284.01. This implies, when the customer is manger, the agent bonus decreases by 248.01 units, keeping all other predictors constant.
As per the above model building analysis we can say that the variables Customer Tenure , Existing Product Type, Monthly Income of customer, payment method monthly , payment method quarterly are the various  factors which can positively influence the bonus of the agents .


MODEL 3

DECISION TREE RANDOM FOREST, ARTIFICIAL NEURAL NETWORK,  

OUTLIERS AND TREATMENT
As discussed earlier, that we have many outliers in the data set  which might be misleading as the data tends to become bias depending on the mean, hence will be performing the outlier treatment using Inter quartile range calculation.
ENCODING:
For Model 3 we are performing the Label Encoding technique which is can be optimal under this modem building analysis since we would like to get rid of the multicollinearity in the dataset and removing various variables which were not adding value to the dataset . Now the new variables dropped for building model 3 are ‘Age’,’Complaint’.’CustID columns from the data as it has no value addition to the analysis .


TEST AND TRAINING SET
We now divide these into training and test set in the split of 70:30 . keeping the Random state figure as ‘123’ . The X-train set has 3164 observation and test set has 1356 observation . X has all the independent variables and Y has the dependent variables ‘Agent Bonus’ .
SCALING
We have scaled the dataset using Standard Scaler function after splitting the data into train and set.
MODEL BUILDING 
We go ahead with building Decision Tree ,Random Forest and Artificial Neural Network classifer  model,wherein we are using the random state classfier as 123 , hiddel layer sizes as 500 and max iteration at 10000.

The model scores we achieved are as below :
 
Table 4: Model Scores for RF, DT & ANN model's
INTERPRETATION
As we can see under this model the scores seem to be OVER FITTING  for Decision Tree , Random Forest, and Artificial Neural Network model , which means the model is performing well but it is poor in production. Hence cannot be chosen as the optimum model for Agent Bonus Prediction . 
However we see that the Linear Regression model is performing equally well in train and test set. Therefore the Linear regression model can be the optimum model to choose from while building a strategy to plan Agent Bonus .

MODEL VALIDATION 

The most optimum model that was discovered in the above analysis was that of Linear Regression Model 2 where in the regression score in training and test set were 78 and 79 respectively. 

The most important variables which were a good predictor of ‘Agent Bonus’ are as below :

1)Payment Method Monthly & Quaterly  :This means that whenever a customer chooses monthly and quarterly mode of payment the impact on Agent’Bonus is the most and can be analysed further to adapt a bonus plan strategy for Agents.
2)Customer Tenure : this implies whenever customers tenure increase the agent bonus also increases so company should focus on telling agents to source cases where customer should be able to extend the tenure to maximum time , which can yield benefits for the company in terms of premium and bonus to agents
3) Existing Product Type: The product type sold also plays a major impact on deciding Agents Bonus , Company should plan a strategy to  push Agents to sell the popular products and incentivize them for the sale.
4)Existing Policy Tenure: The model says when the unit increase is seen in existing policy tenure the agent bonus also increases.








INTERPRETATIONS

1.	There are 2688 male customers in the dataset of 4520
2.	The customer are mostly undergraduates and working as Executives and Managers.
3.	75% of the Agent receive 4867 as bonus, and maximum anyone has received is 9608
4.	Significant correlation between sum assured and bonus was indentified, indicating if one increases the other also increases.
5.	The customers mostly prefer buying insurance through agents rather than buying it online or any other channel .
6.	50% of the customers have given customer satisfaction score as 3, there is a scope for improvement .
7.	The market base is higher in the West with 2566 customers.
8.	The payment method most customers opt for is half yearly and the least preferred is monthly .
9.	It is observed that 50% of the customer have atleast 4 policy .
10.	There is no complaint registered by atleast 75% of the customers in the dataset .

RECOMMENDATIONS

•	Incentive Structure to be implemented as per below:
              -targets on total sum assured should be allocated to achieve higher payout
              -targets should be set on selling at least 4 types of insurance and policies

•	Upskill programme to be organized for agents who earning below 3000 by:
              - selling more to high income customers.
              - training on products and policies of insurance
              - guidance to retain customers

•	Reduce cost incurred to company by
              -not incentivizing sales made through online channels

•	Rewards and recognition 
             -for employees earning more than 5000 

![image](https://github.com/cijithjose/Agent-Bonus-Prediction/assets/98333115/070b162e-807f-4d8a-bf6b-5319e51d1590)
