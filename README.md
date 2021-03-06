# Google Stock Market Predictor
Utilizes Yahoo finance as an API & retrieves data for use. Implements machine learning with the use of a Recurrent Neural Network in order to provide a prediction of Google stocks. Incorporates visulaization in the form of a table and graph in order to display predicted stock values with actual stock values.

*NOTE: This was an attempt to get as close to the actual values as I possibly could, there is no solid way to predict the stock market with 100% accuracy.*


**STEP 1)**
The first step is importing the necessary libraries in which we will be using for this project. Feel free to implement a diffent plot style if you would like!

![Imports](https://user-images.githubusercontent.com/60532479/82355320-0b4c0480-99d0-11ea-93b3-eff985861a27.png)

**STEP 2)**
Implement the use of pandas' Datareader by grabbing the necessary information we need. In this case, I am grabbing Google's stocks from Yahoo Finance for the dates of Jan 1, 2015 to April 10, 2020. You can also choose to view the data you are working with by calling back the function afterwards.

![Google df](https://user-images.githubusercontent.com/60532479/82355643-7d244e00-99d0-11ea-829f-e530a1773538.png)

**STEP 3)**
View the size of your data as a whole

![Google df shape](https://user-images.githubusercontent.com/60532479/82357027-78f93000-99d2-11ea-9646-bc35a28ee326.png)


**STEP 4) (Optional)**
Visualization of prior closing prices for Google within the stock market.

![PrevPricesGoogle](https://user-images.githubusercontent.com/60532479/82357375-050b5780-99d3-11ea-97df-44023f487741.png)


**STEP 5)** 
Create a new data frame with only closing price values. Then, convert the data into a numpy array for usability. Lastly, train 80% of the the closing prices. You can then view the size of your training data and confirm that it is in fact 80% of the data which was obtained in Step 3.

![GoogleLen](https://user-images.githubusercontent.com/60532479/82358318-59fb9d80-99d4-11ea-91b1-93be549d5949.png)

**STEP 6)**
Implement the use of the minMaxScaler and scale the data. Call back the function to confirm the scaling.

![GoogleScale](https://user-images.githubusercontent.com/60532479/82358803-0a69a180-99d5-11ea-8983-18362d9217f8.png)


**STEP 7)**
Create both a scaled and training dataset. Use the previous 60 closing price values and append them to the x_train dataset. Use the 61st value and append it to the y_train dataset. It is not manadatory, but you can also test what you have so far with the commented code and see what you are working with.

![CreationTrainingSet](https://user-images.githubusercontent.com/60532479/82360556-91b81480-99d7-11ea-8dee-71cbbf392323.png)

**STEP 8)** 
Convert the new x and y train datasets to numpy arrays for uability. We also need a 3-Dimensional array for usability as well, so we must reshape the data upon converting it into a numpy array. Call back the function to confirm that the array is in fact 3-Dimensional.

![ConversionGoogle](https://user-images.githubusercontent.com/60532479/82360989-30447580-99d8-11ea-93cf-6baaed5d6ace.png)

**STEP 9)**
Use a modified version of a Recurrent Neural Network otherwise known as "Long Short Term Memory". Long Short Term Memory makes it easier on us when it comes to remembering past data in memory. 

![GoogleLSTM](https://user-images.githubusercontent.com/60532479/82361843-6cc4a100-99d9-11ea-912a-48585c870396.png)

**STEP 10)**
Utilize the optimizer "Adam" and "Mean Squared Error" to compile the model. Then train the model to obtain an understanding of how much loss has taken place throughout the epoch. 

![GoogleCompilation:Trianing](https://user-images.githubusercontent.com/60532479/82369410-f9c12780-99e4-11ea-8e47-62c8fd5c1130.png)

**STEP 11)**
Create a new training dataset containing only the scaled values. Then create an x & y test set, with the x test set containing the previous 60 closing prices.

![New Training set](https://user-images.githubusercontent.com/60532479/82370154-14e06700-99e6-11ea-97ee-281e7ef3951f.png)


**STEP 12)**
Convert the x_test set into a numpy array for usability and reshape the data as well.

![x_test conversion](https://user-images.githubusercontent.com/60532479/82370481-9fc16180-99e6-11ea-964b-7432d6e07382.png)


**STEP 13)**
Predict the price values for x_test. Once complete, then scale and transform the x_test set. Then, also obtain your Root Mean Squared Error value. The Root Mean Squared Error will measure how much error there is between our datasets. Since we are predicting stocks and the variancy can be quite large, this is a decent RMSE.

![PredValue:RMSE](https://user-images.githubusercontent.com/60532479/82372115-62aa9e80-99e9-11ea-84fe-4acd6aae9d84.png)


**STEP 14)**
Create a function that can be used to call back later on to display and compare our raw predicted values agianst the actual values. Also, create a plot to visualize the differences between our training data, actual values, and predicted data for the previous 60 days from i (April 10, 2020). Based upon our graph, we can see that our predictions weren't incredibly too far off.

![Plot1Google](https://user-images.githubusercontent.com/60532479/82373248-4f98ce00-99eb-11ea-9f27-f18d86711617.png)
![PlotGoogle2](https://user-images.githubusercontent.com/60532479/82373822-20cf2780-99ec-11ea-8744-456ec6eab28e.png)


**STEP 15)**
Call back the function from Step 14 to display raw values and obtain a full understanding of how far off our predictions were from the actual closing prices for the prior 60 days to i (April 10, 2020). 

![ActualvsPred](https://user-images.githubusercontent.com/60532479/82374550-3264ff00-99ed-11ea-8a2b-ca99d33535ce.png)


**STEP 16)**
Create one more dataframe to once again contain the previous 60 days then scale it again as well. Append the previous 60 values into the x_test set then convert it into an array and reshape it. Once you have modified your x_test set, predict the closing stock value for the next day and obtain the actual closing stcok value in order to compare the two. As you can see, I came up about 59 points shy from the actual stock value. 

![Final Plot](https://user-images.githubusercontent.com/60532479/82375623-da2efc80-99ee-11ea-83f7-1b9c4be29341.png)















