# Neural_Network_Charity_Analysis

## 1.	Overview of the analysis: 

The purpose of this analysis is to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup. A CSV file was received containing more than 34,000 organizations that have received funding over the years from Alphabet Soup. Below are provided columns that capture metadata about each organization. 
* EIN and NAME—Identification columns
* APPLICATION_TYPE—Alphabet Soup application type
* AFFILIATION—Affiliated sector of industry
* CLASSIFICATION—Government organization classification
* USE_CASE—Use case for funding
* ORGANIZATION—Organization type
* STATUS—Active status
* INCOME_AMT—Income classification
* SPECIAL_CONSIDERATIONS—Special consideration for application
* ASK_AMT—Funding amount requested
* IS_SUCCESSFUL—Was the money used effectively

## Results:

Variables that is considered the target for the model
  * “IS_SUCCESSFUL”

Variables that are considered features for the model:
  * Application_Type
  * Affiliation
  * Classification
  * Use_case
  * Organization
  * Status
  * Income_Amt
  * Special_Considerations
  * Ask_Amt

Variables that are neither targets nor features and should be removed from the input data:
  * Removed form initial data: EIN and NAME
  * Removed during later analysis: ASK_AMT

Compiling, Training, and Evaluating the Model
  * Initial attempt: For the initial model, two hidden layers were created, first layer contained 80 neurons and second layer contained 30 neurons. The functions   selected were relu and sigmoid for the output. 
  ![image](https://user-images.githubusercontent.com/26393180/168493595-2dcc4408-752e-48a0-b0bc-4488136a31d2.png)
  
    The initial model shows an accuracy score of 0.7254810333251953, shown below.
   ![image](https://user-images.githubusercontent.com/26393180/168493613-a7beef87-964a-42c6-b534-d13beab22052.png)

Successful in achieving the target model performance? 
I was not able to achieve the target model performance. Four attempts were made to achieve this goal. The details of the attempts are presented below. 

 * Optimization Attempt #1: 
 
    An additional hidden layer was created containing 15 neurons. 

    ![image](https://user-images.githubusercontent.com/26393180/168493718-9aa5d1cb-5849-443e-a34f-9a80ed1a0bc4.png)

    The accuracy score ended up decreasing after adding this additional layer. 
    ![image](https://user-images.githubusercontent.com/26393180/168493728-26e042b3-3036-48eb-ae80-5cc6dac541d3.png)

 * Optimization Attempt #2: 
 
    For attempt number 2, the number of layers was changed back to two layers. Number of epochs was change from 50 to 200. 
    ![image](https://user-images.githubusercontent.com/26393180/168493754-b8e54918-c900-4434-8ff7-2ab758033b88.png)

    ![image](https://user-images.githubusercontent.com/26393180/168493761-522cee85-4920-462c-839b-849593d1fa3d.png)

    Our second attempt shows the accuracy score did increase compared to the initial attempt but not by much. 
    
    ![image](https://user-images.githubusercontent.com/26393180/168493770-f5544b04-29e3-4dc2-8957-75d4fca9c99c.png)

 * Optimization Attempt #3: 
 
     For this attempt, the variable ASK_AMT was dropped from the dataset to see if this may be a noisy variable. The number of neurons in hidden layers was also increase as well. First layer now contains 100 while second layer contains 50. Epoch was changed back to 50.    
     
     ![image](https://user-images.githubusercontent.com/26393180/168493797-495976d9-63f8-4783-a1c4-34242bcb8463.png)

      ![image](https://user-images.githubusercontent.com/26393180/168493803-2333b8f0-fbe4-4202-a3bc-d43f2725bae1.png)

      The adjustment presents the highest accuracy score so far but it still does not meet the goal of 75%.
      ![image](https://user-images.githubusercontent.com/26393180/168493812-d84a15b6-adf5-4a70-a0df-e845e82740c1.png)

 * Optimization Attempt #4:
     The same code from attempt number 3 was used but the activation function was changed to tanh with the output function still being sigmoid. 
     
     ![image](https://user-images.githubusercontent.com/26393180/168493824-5ffd3e48-9687-4606-a354-5da4fe6e6b33.png)

      The accuracy score decreased when using the tanh function. 
      ![image](https://user-images.githubusercontent.com/26393180/168493829-1f3528d2-dd1b-4803-9a2c-6838774ae87e.png)


##Summary

Overall, after multiple attempts the goal of 75% accuracy was not able to be achieved. I would recommend using balanced random forest so it is clear what variables are important for the analysis. The unimportant variables can then be removed from the dataset. This may help create a more accurate model. 
