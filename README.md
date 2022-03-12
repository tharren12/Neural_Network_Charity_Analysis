# Neural Network Charity Analysis

## Project Overview

Extracted, transformed, and loaded charity_data.csv onto the Jupyter Notebook environment. The data was then trained and tested to create a prediction using neural networks to predict which charities are successful or not. The accuracy was measured to see how succesful the prediction was.

## Resources

* Data Sources: charity_data.csv
* Software: Python 3.8.0, Jupyter Notebook 6.0.1, TensorFlow 2.0.0, Pandas 1.0.1, Scikit-learn 0.22

## Summary

There were a lot of messy data in the charity_data.csv file. Each data value had to be classified as either the target, features, or trash. The target variable for the model was the 'IS_SUCCESSFUL' column. The features were 'APPLICATION_TYPE', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', and 'ASK_AMT'. The variables that were removed were 'EIN' and 'NAME' because these values had too many unique values and were not import to the analysis.

![image](https://user-images.githubusercontent.com/92001105/158037523-f28a5cb3-0c1a-4377-ada6-036cefc98fc8.png)

* Looking at the APPLICATION_TYPE graph, there is a higher density of values with the unique count from 0 to 10000. The graph can help visualize which values need to be joined to make the a less congested encoded dataframe.

![image](https://user-images.githubusercontent.com/92001105/158037569-a678cea9-8a23-4bd1-b9a5-e203417423d8.png)

* CLASSIFICATION graph displays much more significant spike in unique values between 0 to 2500. This means that those values can really congest an encoded dataset which means that the columns should be grouped into one column.

## Analysis

Used three different optimizations of models to compare accuracy. In the original model 2 hidden layers were used with 80 neurons in the first layer and 30 neurons in the second layer and with the activation layer being relu. The results were Loss: 0.8082101941108704, Accuracy: 0.4417492747306824.

In the first optimization attempt a third layer was added with 30 neurons but did not significantly change the accuracy Loss: 0.7324989438056946, Accuracy: 0.4481632709503174.

In the second optimization attempt the neurons were increased to 100 in the first layer and 50 in the second and third and the activation layer was changed to sigmoid, but did not significantly change the accuracy Loss: 0.6977050304412842, Accuracy: 0.48758018016815186.

In the third optimization attempt the third layer was removed, the neurons were increased to 200 in the first layer and 100 in the second layer and the activation layer was changed back to relu, but did not significantly change the accuracy Loss: 0.6870083212852478, Accuracy: 0.5058892369270325.

Potentially additional variables could be removed to ensure there is not overfitting and increase the accuracy, but at this time it would not be reommended to utilize these models as the accuracy is not strong enough.
