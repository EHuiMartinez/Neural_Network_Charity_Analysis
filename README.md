# Neural_Network_Charity_Analysis

## Overview of the analysis: 
This analysis used deep learning model to predict whether applicants of the Alphabet Soup charity would be successul.  A dataset of over 34,000 organizations that received funding from  Alphabet Soup over the years was used to help create deep neuro network models.

## Results: 

### Model:
Train data result
![nn_train.png](/Resources/nn_train.png)

Test data result
![nn_test.png](/Resources/nn_test.png)

#### Data Preprocessing
1. From the dataset, the IS_SUCESSFUL column is the target variable.  The results are in binary (0,1) where 1 indicates successful and 0 indicates unsuccessful.

2. The features were APPLICATION_TYPE, AFFILATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT.

3. The EIN and NAME columns were identification columns that was not relevant and was removed.

#### Compiling, Training, and Evaluating the Model
1. How many neurons, layers, and activation functions did you select for your neural network model, and why?
2. Were you able to achieve the target model performance?
3. What steps did you take to try and increase model performance?


### Optimized Model #1:
Train data result
![nnopt1_train.png](/Resources/nnopt1_train.png)

Test data result
![nnopt1_test.png](/Resources/nnopt1_test.png)

### Optimized Model #2:
Train data result
![nnopt2_train.png](/Resources/nnopt2_train.png)

Test data result
![nnopt2_test.png](/Resources/nnopt2_test.png)

### Optimized Model #3:
Train data result
![nnopy3_train.png](/Resources/nnopt3_train.png)

Test data result
![nnopt3_test.png](/Resources/nnopt3_test.png)


## Summary: 
Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.