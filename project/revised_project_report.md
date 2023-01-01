# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### ANJALI SURESAN

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Initially, I was unable to submit the predictions due to the error:'kaggle: not found'. This was solved using the '!pip install -U kaggle" command. Secondly, the negative values in the predictions had to be set to zero before the submission could be made. 

### What was the top ranked model that performed?
The top ranked model was the 'WeightedEnsemble_L3". The evaluation metric used was the root mean squared error. For this model, the validation score was 52.820442

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The EDA showed the distribution of the different features relative to the data using a histogram. The heatmap of the correlation between the features is also presented. 
I added two additional features by separating out the datetime into the hour and month features. The season and weather fetaures were also set to "category" 

### How much better did your model preform after adding additional features and why do you think that is?
After adding the two additional features and testing the models, the top ranked model (WeightedEnsemble_L3) had a validation score of 29.917493. The added features of hour and month give additional insights and data for training the model, improving its effectiveness. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After the hyperparameter optimization, the the top ranked model  was WeightedEnsemble_L2 that had a validation score of 66.471960.  The hyperparameters were changed for the Neural Network Models. The changes made were in the dropout probability, the activation function and the learning rate. These were set to values other than the default to observe changes compared to the two previous implementations.     

### If you were given more time with this dataset, where do you think you would spend more time?
Hyperparameter optimization for individual models like optimizing the current 'best' model. Changing hyperparameters for other models such as the Gradient Boosting based models could be explored.  

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
The table below shows the modified hyperparameters for the Neural Network models across three different models.

|model|learning_rate|dropout probability|activation function|score|
|--|--|--|--|--|
|initial|0.0005|0.5|relu|1.81039|
|add_features|0.0005|0.5|relu|0.71644|
|hpo|value in the range of 1e-4 to 1e-2	|value in the range of 0.0 to 0.5|tanh|0.62257|

### Create a line plot showing the top model score for the three (or more) training runs during the project.



![model_train_score.png](model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.



![model_test_score.png](model_test_score.png)

## Summary
The first figure shows the validation score for the top model for the three training runs. The second plot shows the kaggle score for the three prediction submissions.
