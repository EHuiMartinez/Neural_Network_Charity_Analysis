# Neural_Network_Charity_Analysis

## Overview of the analysis: 
This analysis used deep learning model to predict whether applicants of the Alphabet Soup Charity would be successful.  A dataset of over 34,000 organizations that received funding from  Alphabet Soup over the years was used to help create deep neuro network models.

## Results: 

### Data Preprocessing
* From the dataset, the IS_SUCESSFUL column is the target variable.  The results are in binary (0,1) where 1 indicates successful and 0 indicates unsuccessful.

* The features are APPLICATION_TYPE, AFFILATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT.

* The EIN and NAME columns are identification columns that was not relevant and was removed.

* The APPLICATION_TYPE and CLASSIFICATION columns were binned to reduce the number of categories and updated the dataframe.  Then the data was converted using scikit learn's OneHotEncoder, then standardized with StandardScaler.

### Compiling, Training and Evaluating the Model
#### Model:

* For the initial model, the number of neurons for the first layer is 80 and 30 for the second layer.  Relu activation was used for these 2 layers and sigmoid activation is used for the outer layer.  Since the target is binary, we used the "binary_crossentropy" for loss and "adam" for optimizer and "accuracy" for metrics.  The model was trained to 100 epochs.

* The model performed at 72.5% with training data and 72.4% with the testing data.  The loss of data is 56.0% for training and 58.0% for testing data.

Train data result
![nn_train.png](/Resources/nn_train.png)

Test data result
![nn_test.png](/Resources/nn_test.png)

## For the Optimized Models, the goal is to increase the accuracy of the predictions to >75%.  More than 20 trials were performed, 3 best results were captured from the various trials.

Note: What is not captured in the data processing steps is because they created worse outcomes than the initial model's processed data.

* For data preprocessing, the STATUS and SPECIAL_CONSIDERATIONS columns were dropped.  Any null or na values were dropped.  After adjusting the APPLICATION_TYPE and CLASSIFICATION columns in several trials, using the original set categories provided the best results.  Attempts to bin the ASK_AMT column also did not improve results.  This updated dataset was used for the below 3 Optimized Models.

### Optimized Model #1:
* A 3rd layer was added to this model and all 3 layers increased in neurons by 3x the input features.  The activation of relu and sigmoid on the outer layer was used.  The model was trained to 200 epochs.
* The results of this optimized model was similar to the initial model; training data accuracy was 72.5% and 72.4%. The loss for this model is higher than the initial model at 64.6% for the training data and 68.6% for the testing data.  Even though the loss was higher for this model, the increase in neurons, layers and epochs produced the same accuracy as the initial model.  

Train data result
![nnopt1_train.png](/Resources/nnopt1_train.png)

Test data result
![nnopt1_test.png](/Resources/nnopt1_test.png)

### Optimized Model #2:
* The same amount of layers and neurons were used for this model but the activation for the layers was changed to LeakyReLU and the outer layer activation to tanh. These activations were used as an attempt to improve the accuracies since the standardized dataset used is in small negative to positve numbers.
* The model performance did not improve with the change in activation and decreased in accuracy to 72.3% with 60.3% loss in training data and 71.8% with 76.4% loss in testing data.

Train data result
![nnopt2_train.png](/Resources/nnopt2_train.png)

Test data result
![nnopt2_test.png](/Resources/nnopt2_test.png)

### Optimized Model #3:
* The layers of this model was increased to 10 layers with 3x the number of input features for each layer.  The activation was reverted to ReLU and sigmoid.
* With this increase in layers and neurons, the accuracy results increased to 72.7% with 91.8% loss for the training data and 72.6% accuracy with 97.9% loss.  Although this loss is very high, the accuracy is also the highest amongst all the trials.

Train data result
![nnopy3_train.png](/Resources/nnopt3_train.png)

Test data result
![nnopt3_test.png](/Resources/nnopt3_test.png)


## Summary: 

The overall results of the deep learning models discussed ranges from 71.8% - 72.7%. The accuracy results were only slightly varied between all the models but the loss increases as we increased the layers and nodes.  The optimized model #3 performed the best in accuracy but highest in loss.  

As mentioned earlier, the models discussed were the better results from multiple testing through additional preprocessing of data, such as changing the APPLICATION_TYPE and CLASSIFICATION bin ranges, as well as attempt to bin the ASK_AMT data.  All attempts produced lower than presented models in this report and the preprocessed data from the initial model was kept, with additional dropping of the STATUS and SPECIAL_CONSIDERATIONS columns.

Using sort features importance, the AMT_STATUS column is ranked the highest importance in the prediction and was included without any preprocessing.

![feature_rank.png](/Resources/feature_rank.png)

Besides deep neuro network, the Alphabet Soup Charity dataset was tested with easy ensemble AdaBoost classifier and resulted in only a 71% accuracy score.  As another supervised machine learning model, this also did not accomplish the goal of >75% accuracy.

![easy_ensemble.png](/Resources/easy_ensemble.png)

To increase the accuracy to >75%, other factors to consider may be to increase the dataset or continued transformation of the dataset.  Also increasing the layers and neurons did show an increase in accuracy slightly - the model could be optimized further with additional layers and neurons beyond the 10 layers in this analysis.

