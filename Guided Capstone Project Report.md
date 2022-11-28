# Pricing Prediction Summary

To summarize this process of predicting a better pricing model, we will move step by step starting from the Problem Statement, to the algorithms used and then finishing with the price recommendation and also potential future work. To preface this document, broadly speaking it is regarding a skiing resort called Big Mountain, which has business executives looking to re-evaluate their pricing model.

## Problem Statement

The problem statement part of this process is to simply get an understanding and summary of the initial problem that we are trying to solve. It is here where we clarify what exactly we are trying to do. In particular, the issue was decided to be that the ticket prices are to be adjusted. Whether the ticket prices will be increased depends on whether or no costs are cut by removing assets, or assets are added to justify a ticket price increase. These assets are the features of the data that will be used to predict the ticket prices, and success is dependent on predicting a better pricing model for the tickets.

## Data Wrangling

In this step the data was origanized and cleaned. Starting off with simply exploring the data via histograms, there were noticeable outliers that skewed certain features in the data set. Some of these data points had obviously flawed data (like the Years Open feature), so they were corrected. We also added some population data for the states, found on wikipedia. Ulitimately, the arguably most important thing done in this step was deciding on the target feature that we would use out model to predict. In particular, there were two possible target features, the weekend ticket price and the weekday ticket price. Plotting them against each other, we found that they are fairly correlated, as you can see below.

![Weekend vs Weekday Ticket Prices](https://user-images.githubusercontent.com/41649635/204149826-488d37fb-1c9d-415d-ae10-cd502b6b8db1.jpg)

This plot itself is rather inconclusive, but as it turns out, the ticket prices for weekdays was actually missing more data than the weekend ticket prices, so in the end the weekend ticket prices were chosen.

## Exploratory Data Analysis

With the data now organized, it can be explored in detail. Two notable things done in this stage were viewing the top states based on different features in the data, as well as principal component analysis, to find relationships among features. Naturally, when exploring data not everything you do will lead to notable conclusions, and these two things were unfortuneately examples of this. That being said, using a heatmap and histograms, some conclusions were drawn from this stage. Viewing the histograms below, you can see how this led to the observation that the main features that should be used for model prediction later on are the features: `Runs`, `total_chairs`, `vertical_drop` and `fastQuads`, as they have the most clear correlations with the Ticket Price feature.

![EDA Ticket Price Histograms](https://user-images.githubusercontent.com/41649635/204167016-70fed085-5e89-4d88-9405-f163da6e6414.jpg)

## Model Pre-Processing, Algorithms, and Evaluation Metrics

Before training the model, the data needs to be prepared, which is exactly what this stage entails. As is always done in machine learning, the data was first split into training and testing sets. The test size was 0.3, or 30 percent of the data. The only other important pre-processing step done here was that the training set was further split into 5 parts, since we used the cross validation techinique for model testing. The test set was saved for a final test at the end with the chosen model, as is standard practice in this field.

Before getting into the models, the accuracy metric to be used was chosen. We went with three here, namely the r2 score, mean squared error, and mean absolute error. In fact, these were used with a non-model, that simply predicted the mean price given any input, to make sure such a simple model like this was not good enough. Of course, it wasn't, giving an r2 score of 0, and some poor results with the other metrics as well. 

Finally, we move on to the model selection part. Two models were attempted, namely Linear Regression and Random Forest. In both cases gridsearch was used to find the best hyperparameters. Naturally, they both performed much better than simply predicting the mean, across all evaluation metrics. That being said, with the optimal hyperparameters, the Random Forest algorithm performed better than the Linear Regression model. Using the mean absolute error as an example, the Random Forest model was about half a dollar less than the Linear Regression model, and also had less variance with a standard deviation of about half a dollar less as well. Not only that, but the Random Forest model also proved the assumption before that the most important features would be the `Runs`, `total_chairs`, `vertical_drop` and `fastQuads` features. You can see this in the plot below, where these features are all in the top 5 most important.

![Random Forest Feature Importance](https://user-images.githubusercontent.com/41649635/204175047-a58c1341-e8cb-4fcc-becd-17d7cd817e10.jpg)

## Pricing Recommendation 

## Conclusion and Future Work


