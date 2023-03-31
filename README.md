# Health-Insurance-Cross-Sell-Prediction
![image](https://user-images.githubusercontent.com/119489207/229149807-f0de5268-5b1f-4d7d-873e-9bc0d2d47768.png)
Business problem: Our client is an Insurance company that has provided Health Insurance to its customers, now they need our help in building a model to predict whether the policyholders (customers) from past year will also be interested in Vehicle Insurance provided by the company. In order to predict whether the customer would be interested in Vehicle insurance, we have information about demographics (gender, age, region code type), Vehicles (Vehicle Age, Damage), Policy (Premium, sourcing channel) etc.

First we import the necessary libraries and look at our data and its characteristics. We have a dataset of 3,81,109 rows and 12 columns with no duplicate/missing data. Next we study the features thoroughly and the data it represents.

In data wrangling, we first create a backup dataset under the name, 'df_copy'. Then We drop the 'id' column as it is not much of use for us. Later, we convert the values in categorical columns 'Driving_License' & 'Previously_Insured' from 1 & 0 to Yes and No for better visualization. We covert 'Region_Code' , 'Annual_Premium' & 'Policy_Sales_Channel' columns from float to int datatype to save space.

Later we visualize our data and perform univariate analysis, bivariate analysis with respect to the dependant variable. The insights found from each chart is described. Finally, we visualize the correlation heatmap and pairplot for better understanding.

Based on our visualizations, we formulate 3 hypothetical statements and perform hypothesis tests. The statements are:

The average annual premium for a vehicle insurance is greater than 20,000. The average age of the customer is greater than 30. The Standard deviation of annual premium is 10,000.

Now was the time for feature engineering. We handled the outliers in 'Annual_Premium' column by using the capping method. In the later boxplot we could visualize all the outliers removed. We wouldn't provide vehicle insurance to someone who didn't have a license to drive. Therefore, we dropped 'driving license' column as they are not providing any valuable information. Furthur, we performed one hot encoding on our categorical features with dropping the first column being true. The data was imbalanced, where the dependant variable, 'Response' had 46,710 label-1 entries and 3,34,399 label-0 enteries. This imbalanced dataset was balanced using SMOTE method. Next we scaled our data using MinMax scaler. Finally we split our data into train and test in 80-20 ratio.

The data was ready to fit into a machine learning model. First, we used Logistic Regression Classifier. We got f1 score as 82%. Second, we used Random Forest Classifier. We got f1 score as 87.32%. We used GridSearchCV for hyperparameter tuning in which we saw a slight improvement. Third, We used XG-Boost with GridSearchCV for hyperparameter tuning. We got a f1 score as 84%.

Out of all above models Random forest Classifier gives the highest F1-score of 87% for test Set. No overfitting is seen.

So finally, the insurance company can deploy a machine learning model that uses Random Forest Classifier to predict the wheather the already existing health insurance customer would be interested in a vehicle insurance product. The company can improve the conversion rate by taking steps to encourage people to buy vehicle insurance by offering some incentives/ease of application & claim settlement process. Cross selling might be an effective way to increase the profits since the customer acquisition cost still remains 0.
