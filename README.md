# deep-learning-challenge






## Overview of the Analysis

The goal of this analysis is to build a model able to predict if the applicants for fundings at the nonprofits foundation called Alphabet Soup will be successful in their ventures. We started from a dataframe of previous applicants that hosts fields like: `applicant name`, `application` and `organization type`, `affiliation`, `classification`(Government organization classification), `use case` for the founding, `income classification`, `founding amount` and lastly if the founding was `successful` or not. This last parameter being the target of our analysis, successful fundings being `0` and unsuccessful being `1`.
We proceed by dropping the name of the applicant that being an irrelevant field for the goal of our analysis we then proceeded to determine the number of unique values for each field in order to have a better understanding of our dataset, extracted the value count for the application types and aggregate the less relevant ones as `others` in order to leave only the most relevant for our analysis we then proceeded to do the same for the `classification` field.
Afterward we converted the categorical data in numeric in order to make this field analyzable by our model, in fact the neural model that we are trying to build works only with numerical datasets, we then proceed with the last step necessary to prepare our dataset to build the model, we assigned the `is_successful` column to our target variable and the remaining processed colum,ns to our features variable, we then split the two in test and train groups and lastly proceeded to standard scale them.
The whole process left us with 25724 records for 42 different dimensions.
The last step of our process was building the actual model this was done by setting three different hidden layers all with a `selu` activation function (Scaled Exponential Linear Units) the first receiving 42 input dimensions, and holding 128 perceptron the second hosting 64 and the last 32, at the end we have our outpull layer presenting a `sigmoid` function as activation.
We then ended our process by compiling our model, fitting it setting the number of epochs to 100 and then saved it for future use as `AlphabetSoupCharity.h5`.


## Results

* Deep Learning Neural Network Model:

    * **Model Accuracy** = 0.73 : This means that our model is able to accurately predict 73% of the training data sample.
    * **Model Loss** = 0.55 : this value shows the error of our model prediction compared to the actual values of our training dataset.
    * **Model Speed** = 354 ms/epoch : this data suggests that for each epoch our model took on the average 354 milliseconds.
   

## Summary

Overall the model has a good predictive score even if it doesn't get to 75%. That might be due to the diversity of the found raisins characteristics and intents, in fact every one of them might have encounter different difficulties in reaching their goals in the real life environment and that with the diversity of the scope of the various fundraising might have influenced the ability of our model to predict the outcome of some of the ones present in our dataset. These difficulties might be overcomed by adding more information about the amount of people that joined each fundraising and the amount collected by each funder and not just the overall amount collected.


All the code for the analysis was made by me with the help of the class materials.