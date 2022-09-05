# Employee Attrition Estimator: Project Overview

Dataset: https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset <br>
Inspiration for Project: https://www.youtube.com/watch?v=LUs4L-r51D8

* Created a tool that estimates/predicts employee attrition to help "IBM" find ways to incentivise and maintain proper staffing year-over-year
* Cleaned and performed Exploratory Data Analysis to determine best variables used in the model building and training.
* Optimized Random Forest Regressors using GridsearchCV to reach the best model.

## Conclusions
* We can predict, with our model, whether an employee will stay with 82% weighted accuracy
* The best predictors of whether someone will stay are broken down into 5 variables in descending order of importance:
    1. Income
    2. Age
    3. Total Working Years
    4. Proximity to Workplace
    5. Amount of Over Time given
    


## Code and Resources Used 
**Python Version:** 3.9.12
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn  



## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. There were a few transformations and recodes that needed to be completed.

* Recoded the following Columns with String variables to integers
    * BusinessTravel
    * Department
    * EducationField
    * StandardHours
    * Gender
    * Marital Status
    * OverTime
    * Job Roles
* Dropped the following columns for lack of useable data:
    * EducationField - may add back in when performing a regression model later
    * StandardHours - only contained one value
    * Over18 - only contained one value
    * EmployeeCount
    * Employee Number
*	Used Lambda function to create YearlySalary column from DailyRate column
    * This was later removed for our final model build
*	Removed NaN values from the dataset


## Model Building 

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 40%.   

I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.   

I attempted one model and evaluated the fit for the data. With an 82% accuracy, we have a pretty decent build. However, I will explore further models builds through Lasso Regression and Multiple Linear Regression

Here is the model I tested
*	**Random Forest** – with the sparsity associated with the data, I thought that this would be a good fit.

## Model performance
The Random Forest model performed well and was able to predict employee attrition with 82% accuracy.
*We performed Hyperparameter tuning to enahnce and build the best possible model. The following parameters gave us the best model.
     * Number of Estimators = 50
     * Minimum Samples Leaf = 1
     * Max Depth = 30
     
     
## Conclusions
* We can predict, with our model, whether an employee will stay with 84% accuracy
* The best predictors of whether someone will stay are:
      * Monthly Income
      * Age
      * Total Working Years
      * Hourly Rate
      * Monthly Rate
      * Distance from Home
      * OverTime


