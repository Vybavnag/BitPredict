This is a summary of my machine-learning model that predicts the price of Bitcoin.

This is an ML model project in TensorFlow that utilizes transfer learning, convolutional neural networks, and relational neural networks.

## Table of Contents 
* [Motivation](#motivation)
* [Summary of approach](#summary-of-approach)
* [Results](#results)
* [Insights](#insights)
* [What I learned](#what-i-learned)
* [How to use this repository](#how-to-use-this-repository)

## Motivation
Upon starting my ML journey, I wanted to create something that could predict stuff in the future like house prices or Bitcoin prices.
![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/Bitcoin_chart.jpg)


## Summary of approach
I started with a basic sequential CNN with 2 layers with a portion of data and then I scaled them up. The evaluation results are here:

Model1:

![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/model_1_preds.jpg)

Model2:

![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/model_2_preds.jpg)

Model3:

![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/model_3_preds.jpg)


The results weren't what I wanted so I decided to create a Conv1d model. The evaluation results are here: 

**{'mae': 574.57104,**


 **'mse': 1195531.0,**

 
 **'rmse': 1093.4034,**

 
 **'mape': 2.5650182,**

 
 **'mase': 1.0093622}**
 

I decided to use the LSTM for the time series data. The evaluation results are here:

**{'mae': 579.0948,**


 **'mse': 1206146.1,**

 
 **'rmse': 1098.2468,**

 
 **'mape': 2.613475,**

 
 **'mase': 1.0173092}**


It looks like our model is performing worse. I decided to use multivariate time series data for the next model. The evaluation results are here:

**{'mae': 568.42395,**


 **'mse': 1179631.1,**

 
 **'rmse': 1086.1083,**

 
 **'mape': 2.541055,**

 
 **'mase': 0.99856347}**


I then replicated the layers presented in the N-Beats model from "NEURAL BASIS EXPANSION ANALYSIS FOR
INTERPRETABLE TIME SERIES FORECASTING" paper. Here is what the model looks like:

![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/nbeats.jpg)



The evaluation results are here:

**{'mae': 590.5516,**


 **'mse': 1231043.1,**

 
 **'rmse': 1109.5238,**

 
 **'mape': 2.6545231,**

 
 **'mase': 1.0374355}**

To end it off I created an ensemble and staked the models on top of each other. Results are shown in the results section

## Results
**{'mae': 566.77386,**


**'mse': 1151240.8,**

 
 **'rmse': 1072.9589,**

 
 **'mape': 2.5520275,**

 
 **'mase': 0.9956647}**
 
Prediction results:


 ![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/prediction_results.jpg)
 

Comparing Models:


 ![alt text](https://github.com/Vybavnag/BitPredict/blob/main/images/comparing_models.jpg)
 


 

## Insights
Trying to predict future results does give us a model that is successful in doing so however, especially when it comes to cryptocurrency everything is volatile and relies on a series of factors that can never fully be implemented into our model. It is like predicting the stock market. We can get close but never fully accurate. The N-beats models and others do get close but they can never predict the future fully.

## What I learned
* How to scale data into models using Windows.
* Implementing RNNs and how to create your layers in Tensorflow.
* How to vizualize timeseries data.
* Can never fully predict the future, especially with cryptocurrency.
  
## How to use this repository
Open the ipynb file in Google Colab or Jupyter Notebook and run. Make sure there is a GPU with high RAM.
