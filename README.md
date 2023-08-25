# Agent-Bonus-Prediction


# INTRODUCTION

Insurance in India and everywhere else is used to cover the financial risk or the loss that the policy holder may have to face if they are involved in an incident that results in property, physical or any other damage. 
A policy holder will typically pay’s insurer a month/annual fee which is also called a insurance premium. The insurance premium paid by the owner is determined by taking several parameters into consideration such as the customers marital status, credit history, whether the customer has an owned or rented accommodation, owners age ,gender and their previous history, the geographic details of the owner etc. Based on these factors an insurance company will increase premium or offer discounts based on the level of risk. 

 # Background 

An insurance broker makes money off commissions from selling insurance to individuals or businesses. Most commissions are between 2% and 8% of premiums, depending on state regulations. Brokers sell all insurance types, including health insurance, homeowner insurance, accident insurance, life insurance, and annuities.

In this project we are working on insurance sales dataset wherein we have several information’s about the customers profile, their income, existing product type, sum assured, no. of policy, channel availed in other words whether the policy taken was through agent or third party and the bonus of the agents etc .

# Objective

The company wants to predict the bonus for its agents given the existing data so that it may design appropriate engagement activity for their high performing agents and upskill programs for low performing agents.

This insight can help the business multiply its profits by generating more sales through incentivizing insurance agents, on the other hand the agents are also motivated to perform and work for the extra bonus which be financially helpful for meeting third day to day needs. The analysis would also focus on the non performing agents who have sold lower policy’s and try to understand the reasons and areas of improvement .


# Data set

The data contains the customer record’s collected overtime as when they were sold the insurance . It consists of 4520 observations and 19 variables/ columns which is a panel data and not a time series data. There are 4520 customers records identified through their unique ID’s. There are details of customers personal and demographic information, along with the types of policy, frequency and sum insured of policy. 

There are 8 object types , 5 integer and 7 float type variables described as below :


After the initial data inspection we saw that there are several missing values present in few variables like Age (269) ,Cust Tenure (226), number of policy (45), monthly income (236), existing policy tenure (185), sum assured (154), CustCareScore (52).

Now we will describe all the numerical variables to understand more about the data:

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

 
The data gives us the following information:

o	There are 3 channels of sales , Agent , Online and Third Party partner
o	The description shows there are 5 unique occupations that the customer in the dataset are doing namely Free lancers, Salaried, Large Business & Small Business, one of category is a spelling error mentioned as ‘laargebusiness’ and needs to corrected.
o	EducationField shows 7 unique categories which includes several erroneously entered values and needs to be corrected.
o	Gender shows 3 unique values again which needs to be corrected.
o	Designation variable shows 6 distinct job roles out of which Manager is the most frequent occurring in the dataset
o	Most of the customer in the dataset are either divorced , single or married . The fourth category say unmarried which can be included under single status .
o	There are 4 zones and most of the customers seem to be from the West
o	Most frequently opted payment method by customers are Half Yearly , with other option being Monthly quarterly and yearly .



The heat map and the pair plot shows the relationship between the different variables. It can be noted that there is significant correlation between several variables as below :
o	Age and Agent Bonus
o	CustTenure and Agent bonus
o	Monthly Income Agent Bonus
o	Sum Assured and Agent Bonus
o	Sum Assured and Cust Tenure
o	Sum Assured and Monthly Income

From the above the most significant corelation noted was that of Sum Assured and Agent Bonus , indicating if the Sum assured increased the agent Bonus also increases .

# DATA CLEANING AND PREPROCESSING

Removal of unwanted variables : 

The variable Age has figures entered erroneously as discussed earlier 75% of the customer in the dataset are shown to be as 20 year old which cannot be the scenario given the variables of education and occupation details where its mentioned that most of the customers are undergraduates or working class executives and managers .

Similarly the Variable Complaint has very 75% customers who have not complained and 25% with complaint registered has I have chosen to remove that variable as it would not be significant in the analysis.

# Missing value treatment :

There are values missing for several variables 

I have imputed the missing observations variables CustTenure, NumberOfPolicy, Monthly Income, ExistingPolicyTenure, Sum Assured  and CustCareScore with the median value.
Please note the column Age is been dropped from further analysis .


# Variables Transformation:

The categorical variables had some observation with spelling mistakes which has been corrected and included in the correct category .
For example the gender value had observations as ‘Fe male’ and ‘Female’ for which I have replaced all the ‘Fe male’ to ‘Female’.
Another being the EducationField wherein Customers were marked as ‘Graduates’ and ‘undergraduates’ category . I have included the Graduates under ‘undergraduates’ and marked them same category .	
Similarly with Marital Status variable, wherein I have included Single and Unmarried category as one .

# SHAPIRO TEST 

I have performed the shapiro test on Agent Bonus variables and was returned a p value of 1.418, which is greater than the confidence level of 0.05 , and hence indicates that the data is normally distributed .

Therefore I can say there is no imbalance in the data .

# MODEL BUILDING

We will be building multiple Linear Regression and Random Forest Models using different methods and ensemble techniques such as ordinary least square method, Gradient Descent Method , Grid Search CV . We will be fine tuning the model to achieve the best fit model.



# MODEL VALIDATION 

The most optimum model that was discovered in the analysis was that of Linear Regression Model 2 where in the regression score in training and test set were 78 and 79 respectively. 

The most important variables which were a good predictor of ‘Agent Bonus’ are as below :

1)Payment Method Monthly & Quaterly  :This means that whenever a customer chooses monthly and quarterly mode of payment the impact on Agent’Bonus is the most and can be analysed further to adapt a bonus plan strategy for Agents.
2)Customer Tenure : this implies whenever customers tenure increase the agent bonus also increases so company should focus on telling agents to source cases where customer should be able to extend the tenure to maximum time , which can yield benefits for the company in terms of premium and bonus to agents
3) Existing Product Type: The product type sold also plays a major impact on deciding Agents Bonus , Company should plan a strategy to  push Agents to sell the popular products and incentivize them for the sale.
4)Existing Policy Tenure: The model says when the unit increase is seen in existing policy tenure the agent bonus also increases.




# INTERPRETATIONS

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

# RECOMMENDATIONS

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

