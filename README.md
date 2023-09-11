# Venture Funding with Deep Learning

## Overview

The business team has given you a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. With your knowledge of machine learning and neural networks, you decide to use the features in the provided dataset to create a binary classifier model that will predict whether an applicant will become a successful business.

## Files
#### Resources
* [Analysis File](Colab_venture_funding_with_deep_learning.ipynb)
* [Seed Data](/Resources/applicants_data.csv)

#### Output Models
* [Model (Original)](/Models/AlphabetSoup.h5)
* [Model 2](/Models/AlphabetSoup_A1.h5)
* [Model 3](/Models/AlphabetSoup_A2.h5)
* [Model 4](/Models/AlphabetSoup_A3.h5)

## Instructions

The steps for this challenge are broken out into the following sections:

* Prepare the data for use on a neural network model.

* Compile and evaluate a binary classification model using a neural network.

* Optimize the neural network model.

## Outcome

After running the original model, we saw a 
Loss  | Accuracy
------------- | -------------
0.5571369528770447  | 0.7286297082901001
55.7%  | 72.9%

To optimize the model, I added another hidden layer to reduce the number of inputs heading into the hidden layer before the  output. With this optimization we saw a minimal improvement to the model:
Loss  | Accuracy
------------- | -------------
0.5552924871444702  | 0.7304956316947937
55.5%  | 73.0%

Trying to adjust for overfitting, I created a 3rd model that included a Dropout as well as adjusted the data to remove potentially irrelevant datapoints that could skew the data. With this optimization we saw a decrease in performance of the model:
Loss  | Accuracy
------------- | -------------
0.6328471302986145  | 0.6310204267501831
63.3%  | 63.1%

From this result, it can be concluded that the orgnaization type and affiliation are important indicators of success rate. 

Finally, I tried another optimization by removing the Dropout and altering the excluded columns.  This model netted out:
Loss  | Accuracy
------------- | -------------
0.5726754665374756  | 0.7233819365501404
57.3%  | 72.3%

After seeing improvement, it can be concluded that status, ask ammount, classification, and "No" special considerations are not good indicators of success rate.

Overall, the optimal model I designed was the first optimization in Model A1.  This model produced a 73% accuracy with a 55.5% loss.  While this isn't an amazing result, this model outperformed the other 3.  With more time, I would continue to alter columns included in the analysis, number of hidden layers, and test activation functions. 