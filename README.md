# Neural_Network_Charity_Analysis

## Overview of the analysis:
The project aims to build a binary classification model to predict whether applicants will be successful if funded by Alphabet Soup using neural networks. The dataset contains over 34,000 organizations that have received funding from Alphabet Soup over the years and 12 columns. 

## Results: 
- Data Preprocessing: this step involves dropping identification columns, such as nEIN and NAME. Also, some categorical features have many unique values, and encoding them directly will affect the model performance. Therefore, rare occurrences values are binned into the "Other" category for those columns.
For example, in the APPLICATION_TYPE column, there is a total of 17 unique categories. Values with low occurrences (<528) are binned into one category. Similar binning was performed on each of the following columns: 'APPLICATION_TYPE', 'AFFILIATION','CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', and 'INCOME_AMT'. Once the binning step is completed, encode those categorical variables into integer values using the onehotencoder method.

<img width="656" alt="Screenshot 2023-02-08 at 10 00 46 AM" src="https://user-images.githubusercontent.com/48078471/217613927-a5f07c8b-b038-4856-a61e-6063068b56c7.png">


<img width="986" alt="Screenshot 2023-02-08 at 10 03 03 AM" src="https://user-images.githubusercontent.com/48078471/217614391-09419c21-f4d7-4c42-a0cb-915cc075b829.png">

- Input features: encoded categorical variables ('APPLICATION_TYPE', 'AFFILIATION','CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', and 'INCOME_AMT', and 'SPECIAL_CONSIDERATIONS'), 'ASK_AMT', and 'IS_SUCCESSFUL'
- Output feature: 'STATUS'
- Compiling, Training, and Evaluating the Model: the model structure has three layers (input, hidden, and output) with a total of 5,981 trainable parameters. The number of neurons for the input layer is 80, which is two times the number of input dimensions with relu activation function. For the hidden layer, the number of neurons is reduced to 30 to avoid overfitting by reducing the number of trainable parameters. The output layer has only one neuron with a sigmoid function to help with the binary classification. The model achieved an accuracy of >99% on the testing dataset (33% of the total dataset)

<img width="1105" alt="Screenshot 2023-02-08 at 10 11 17 AM" src="https://user-images.githubusercontent.com/48078471/217616103-4900f19b-0cc9-4290-8b72-4bd8d3e6806d.png">

To further improve the model performance, binning is done to avoid over-fitting. In addition, the NN model structure was further optimized by reducing the number of neurons in different layers and the number of epochs. Those changes ensure to decrease in the number of trainable parameters, which helps improve the accuracy of the testing set to 100%.

## Summary: 
The NN model is a great candidate for Alphabet Soup application status prediction. The flexibility in modifying the structure of the NN model makes it achieve high prediction accuracy with model hyperparameter optimization. Compared to traditional machine learning models, such as k-nearest neighbors, the prediction performance might improve much with hyperparameter tuning as model performance is limited by its capability. 