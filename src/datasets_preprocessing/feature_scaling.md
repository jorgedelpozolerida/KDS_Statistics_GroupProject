# 1.Extract Independent variables(X) and dependent variable(y)

# 2.Identifying and handling the missing values:

* Deleting a particular row – In this method, you remove a specific row that has a null value for a feature or a particular column where more than 75% of the values are missing. However, this method is not 100% efficient, and it is recommended that you use it only when the dataset has adequate samples. You must ensure that after deleting the data, there remains no addition of bias. 

* Calculating the mean – This method is useful for features having numeric data like age, salary, year, etc. Here, you can calculate the mean, median, or mode of a particular feature or column or row that contains a missing value and replace the result for the missing value. This method can add variance to the dataset, and any loss of data can be efficiently negated. Hence, it yields better results compared to the first method (omission of rows/columns). Another way of approximation is through the deviation of neighbouring values. However, this works best for linear data.


# 3.Encoding the categorical data:
* one hot encoding
* label encoding

# 4. Delete  unnecessary features e.g. the date

# 5. Splitting the dataset into train, test, validation

# 6. Feature scaling - WE NEED SCALING  https://www.kaggle.com/code/aimack/complete-guide-to-feature-scaling  The Big Question – Normalize or Standardize?
	
  Normalization vs. standardization is an eternal question among machine learning newcomers. Let me elaborate on the answer in this section.
* Normalization is good to use when you know that the distribution of your data does not follow a Gaussian distribution. This can be useful in algorithms that do not assume any distribution of the data like K-Nearest Neighbors and Neural Networks.
* Standardization, on the other hand, can be helpful in cases where the data follows a Gaussian distribution. However, this does not have to be necessarily true. Also, unlike normalization, standardization does not have a bounding range. So, even if you have outliers in your data, they will not be affected by standardization.
	
	However, at the end of the day, the choice of using normalization or standardization will depend on your problem and the machine learning algorithm you are using. There is no hard and fast rule to tell you when to normalize or standardize your data. You can always start by fitting your model to raw, normalized and standardized data and compare the performance for best results.
	It is a good practice to fit the scaler on the training data and then use it to transform the testing data. This would avoid any data leakage during the model testing process. Also, the scaling of target values is generally not required, but scaling of target values can help to determine how well are the metrics for MSE, RMSE
