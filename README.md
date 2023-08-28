# Module-14-Challenge
Module 14 Challenge 
## Description 

In this module, we will be improving an algorithmic trading bot by assesing and modifying signals and using various algorithms to test and see which is best.
First and foremost, we must test the original algorithm and then we will test it again with different windows and tune the inputs to see if that results in a better outcome.

## Analysis

### Original/Baseline

![SVM_Model_Report](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/b12b8dd9-3600-421d-98e8-b85ff46b4872)

![SVM_Model](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/4d744a0d-5829-4a9f-980d-ac6e8c1e4102)

Based on the above data, this model accuracy was around 55-56%. The signals here which used crossing SMA with a SMA short window of 4-days and a SMA long window of 100 days. 

### Adjusting the Algorithm

![SVM_Model_Modified_Training_Set_Report](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/98773dda-cc3a-49b6-a248-6cd66bc4d247)

![SVM_Model_Modified_Training_Set](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/9955fc37-e637-4994-be3c-097e812113d3)

These models are when the dataset window was doubled for the trained data. The accuracy and returns increased some where the accuracy was 56%.
This data tells us that increasing the training window improves the accuracy and cumulative returns. That being said, we should try to decrease the window to see what would happen.
When the window was decreased, it did not really change the accuracy or cumulative returns.

### Decreased Short Window

![SVM_Model_Modified_SMA_Window_Report](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/944707e7-b1c3-4764-a8c9-d42e8678c9cd)

![SVM_Model_Modified_SMA_Window](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/16dd368c-ebca-4d34-9328-d6bd672f67d8)

The data above is from when the SMA short window was decreased in half from 4 days to 2 days. You can see some increased accuracy but the cumulative returns were reduced.
This tells us that there was no improvement from actual returns and the buy/sell signals also decreased. Out of curiosity, when I increased the window, it further decreased the buy/sell signals so that tells me that the original data was better.

### Original Model Optimization Testing

Based on all the above data, we can see that increasing the training data set to 6 months from 3 months, this had the largest increase on cumulative returns with the original SVC classifier. When adjusted, the new returns were up 84% vs 48% from the original.

![SVM_Model_Modified_Training_Set](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/41c33f12-bbb5-4988-b915-85dfff3a2b91)

### Using a New Machine Learning Model

The following data uses a different model and will be compared to the original. The particular classifier for this model is going to be AdaBoost.
What is AdaBoost? It is a meta-estimator which will fit a classifier on the original data but then will fit copies of it onto the original while adjusting weights of poorly classified cases.

![AdaBoost_Model_Report](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/d21dae4c-864a-407d-9086-8c6210df2371)

![AdaBoost_Model](https://github.com/nkp1027/Module-14-Challenge/assets/133065472/aaff2d28-df34-4d00-b8f7-8c95ae765d76)

By looking at this model, we can appreciate a similar accuract but an increased return. To put it in numbers, we see the same exact accuracy but the return went from 48% (original) to 57% (new model) which shows us that this model is acutally preferred to use. The window was not changed either so that makes us believe that this model is definitely the correct choice to use.

## Tech
Pandas, sklearn, numpy

installation of tech is done by:
conda install pandas
conda install numpy
pip install -U scikit-learn
