# Pricing Prediction Summary

To summarize this process of predicting a better pricing model, we will move step by step starting from the Problem Statement, to the algorithms used and then finishing with the price recommendation and also potential future work. To preface this document, broadly speaking it is regarding a skiing resort called Big Mountain, which has business executives looking to re-evaluate their pricing model.

## Problem Statement

The problem statement part of this process is to simply get an understanding and summary of the initial problem that we are trying to solve. It is here where we clarify what exactly we are trying to do. In particular, the issue was decided to be that the ticket prices are to be adjusted. Whether the ticket prices will be increased depends on whether or no costs are cut by removing assets, or assets are added to justify a ticket price increase. These assets are the features of the data that will be used to predict the ticket prices, and success is dependent on predicting a better pricing model for the tickets.

## Data Wrangling

In this step the data was origanized and cleaned. Starting off with simply exploring the data via histograms, there were noticeable outliers that skewed certain features in the data set. Some of these data points had obviously flawed data (like the Years Open feature), so they were corrected. We also added some population data for the states, found on wikipedia. Ulitimately, the arguably most important thing done in this step was deciding on the target feature that we would use out model to predict. In particular, there were two possible target features, the weekend ticket price and the weekday ticket price. Plotting them against each other, we found that they are fairly correlated, as you can see below.

![Weekend vs Weekday Ticket Prices](https://user-images.githubusercontent.com/41649635/204149826-488d37fb-1c9d-415d-ae10-cd502b6b8db1.jpg)

This plot itself is rather inconclusive, but as it turns out, the ticket prices for weekdays was actually missing more data than the weekend ticket prices, so in the end the weekend ticket prices were chosen.

## Exploratory Data Analysis
