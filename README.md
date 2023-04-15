# IABAC-INX-Future-Inc-employee-performance-analysis

# Project Summary

# 1)Business Case:

INX Future Inc ,(referred as INX ) , is one of the leading data analytics and automation solutions provider with over 15 years of global business presence. In recent years, the employee performance indexes are not healthy and this is becoming a growing concerns among the top management. There has been increased escalations on service delivery and client satisfaction levels came down by 8 percentage points.The CEO of company decided to analyse the current employee data and find the core underlying causes of this performance issues of the employees.  Company also expects a clear indicators of non performing employees, so that any penalization of non-performing employee, if required, may not significantly affect other employee morals.
  
The following insights are expected from this project.

1. Department wise performances

2. Top 3 Important Factors effecting employee performance

3. A trained model which can predict the employee performance based on factors as inputs. This will be used to hire employees
   
4. Recommendations to improve the employee performance based on insights from analysis

# 2)Requirement

Data from third party sources.
The employee performance data of INX Future Inc. can be downloads from below link.
http://data.iabac.org/exam/p2/data/INX_Future_Inc_Employee_Performance_CDS_Project2_Data_V1.8.xls

## 3)Analysis

The data is supervised and categorical as well as numerical, we have 19 Numerical features and 9 categorical features. The predictor variables are nominal and ordinal. The target variable 'PerformanceRating' is ordinal.

### Exploratory data analysis

**UNIVARIANT ANALYSIS**

* Average age of employee in the INX Future Inc is 36 whereas the maximum employee lies in the age group of 25 to 45.

* Many employees resides near the office.

* Many employees has given rating as 3.0 for employee job environment.

* Many employees has worked for 0-1 company.

* most of the employee got salary hike of 0-12%.

* most of the employee has given performance rating as 3.

**BIVARIANT ANALYSIS**

* We can conclude that from EmpDepartement Development department is showing high performance rate as compared to other departement.

* After development department Research & Development department performed well.Sales,Human resources, data science and finance also performed well.

* employee which are business analyst, technical lead, data scientist, developer,have performed well performance rating of employee does not vary with Marital status employee who do overtime have rated as more as compared to those who doesn't do overtime.

* Employee with gender as male are rated more as compare to female employee, the reason may be there are more number of male employees than female employees in the company.

* Employees with education background of Life science and medical are rated more

* Employee who travel rarely are rated more as compared to those who travel frequently or who are non traveler

* Performance rating of employee depends on Years with current manager.when manager is same for long duration of time the employee performace drops. So, for improving performance of employee the manager needs to shuffle atleast after every 2-3 years.

* performance rating depends on years since last promotion. when employee are not promoted since 2 to 3 years, the perfromance of employee drops. Hence to imporve performace of employee the employee should be promoted after every 1 year or at least 2 years.

* Performace of employee also depends on employee work life balance. when employee work life balance is good and are rated as 3 the performance rating of employee is also more.

* when employee relationship satisfaction is more the performance of employee is also more

* When total work experience of employee is above 10 year the performace of employee drops

* when the employee got salary hike of more than 19%, the performce of employee increased. thus, employee performace depends on the salary hike given by the company. employee with higher salary hike percentage has performed well.

* employee who are satisfied by environment have performed well.

* We can see that 11% and 16.3% of employees having low job satisfaction and job involvement have low performance ratings

## Data preprocessing

* **Checking Null values:-** There are no null values

* **Categorical to Numerical data conversion:-** Handle categorical data to Numerical using Label encoding.

* **Outlier Handling:-** Some features contains outliers so we are imputing these outliers with the help of IQR and 3 sigma rule. If the features are normally distributed we will use 3 sigma rule. If the features are not normally distributed we will use IQR.

* **Feature Transformation:-** In YearsSinceLastPromotion some skewed & kurtosis is present, so we used Square Root Transformation techinque.

* **Scaling the data:-** Scaling the data with the help of Standard scalar.

  Standard Scaling: Standardization is the process of scaling the feature, it assumes the feature follow normal distribution and scale the feature between mean and standard deviation, here mean is 0 and standard deviation is always 1.

## Feature Selection

- There are lot of features in our dataset, to extract important features which really contribute to target feature we need to find corelation coefficient. Corelation coefficient is used to find out the important features in dataset and these features are then used to train the model.

- From there, we also get the top factors which affect performance. We can see that the most important features selected were Department, Job Role, Environment Satisfaction, Last Salary Hike Percent, Work Life Balance, Experience Years At This Company, Experience Years In Current Role, Years Since Last Promotion, Years With Current Manager. These were selected because their correlation coeffecient with Performance Rating was more than 0.1.

- Standarization and Label Encoding was also used for feature transformation.

- We can conclude that top 3 Important Factors affecting employee performance are-

1)Employee EnvironmentSatisfaction,

2)Employee Last Salary Hike Percent and 

3)EmpWorkLifeBalance

1. Drop unique and constant feature: Dropping employee number because this is a constant column as well as drop Years Since Last Promotion because we create a new feaure using square root transformation

2. Checking Correlation: Checking correlation with the help of heat map, and get the their is no highly correlated feature is present.
   Heatmap: A heatmap is a graphical representation of data that uses a system of color-coding to represent different values.
   
3. Check Duplicates: In this data Their is no dupicates is present.

## Machine learning Model Creation & Evaluation

1. Define Dependant and Independant Features:

2. Balancing the data: The data is imbalance, so we need to balance the data with the help of SMOTE 
SMOTE: SMOTE (synthetic minority oversampling technique) is one of the most commonly used oversampling methods to solve the imbalance problem. It aims to balance class distribution by randomly increasing minority class examples by replicating them. SMOTE synthesises new minority instances between existing minority instances.

3. Splitting Training And Testing Data: 75% data use for training & 25% data used for testing

## Algorithm:

AIM: Create a sweet spot model (Low bias, Low variance)

HERE WE WILL BE EXPERIMENTING WITH THREE ALGORITHM

1. Logistic Regression 

2. Support Vector Machine

3. Random Forest 

4. Decission Tree 

4. Artificial Neural Network MLP classifier

* Support vector machine well perform on training data with accuracy 90% but the test score is 87%.

- Random forest very well perform in training data with 100% accuracy but in testing 97.61% after doing hyperparameter tunning testing score is decreases.

- Artifical neural network[Multilayer percepton] perform very well on training data with 99% accuracy and testing score is 91.80%.

- So we are selecting Random forest model.

## Recommendations to improve the employee performance

* The overall employee performance can be achieved by employee environment satisfaction. The company needs to focus more on the employee environment satisfaction.

* shuffling the manager after every 2-3 years will result in good performance of employee.

* The salary hike will give the boost to the employees to perform well.

* Promote the employee every 6th month

* Improve Employee's work-life balance this affects the performance rating.

* While recruiting for HR, consider the female candidates where they perform well compared to male.

* The development and sales department is having an overall higher performance comparing to rest of the departments. While some of the employees who gives feedback like Low & Medium from Job Satisfaction & Relationship Satisfaction feature, such employees gives Excellent performance more in number. So company should focus on them.
