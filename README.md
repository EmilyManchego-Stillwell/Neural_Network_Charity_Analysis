# Neural_Network_Charity_Analysis

### Overview:
- Purpose:
    - The purpose of this analysis was to use a deep neural network machine learning model<br>
to determine which charity organizations will be most successful if funded by the company,<br>
Alphabet Soup. 

- Tools used:
    - Google Colab Notebooks
    - Scikit-Learn
    - Pandas
    - Tensorflow

### Results:
**(These results are based on the final attempt to optimize the performance of the initial model)**
- Data Preprocessing:
    - Target variable column(s):
        - IS_SUCCESSFUL
    - Feature column(s) (a total of 43):
        - STATUS
        - ASK_AMT
        - APPLICATION_TYPE_(Other, T10, T19, T3, T4, T5, T6, T7, T8)
        - AFFILIATION_(CompanySponsored, Family/Parent, Independent, National, Other, Regional)
        - CLASSIFICATION_(C1000, C1200, C2000, C2100, C3000, Other)
        - USE_CASE_(CommunityServ, Heathcare, Other, Preservation, ProductDev)
        - ORGANIZATION_(Association, Co-operative, Corporation, Trust)
        - INCOME_AMT_(0, 1-9999, 10000-24999, 25000-99999, 100000-499999, 1M-5M, 5M-10M, 10M-50M, 50M+)
        - SPECIAL_CONSIDERATIONS_(N, Y)
        ![List_Showing_Target_and_Features_for_Model](/Images/List_Showing_Target_Features.png)
    - Removed Columns that were neither Features or the Target variable:
        - EIN
        - NAME
- Compiling, Training, and Evaluating the Model
    - For my model I used 3 hidden layers with 100, 50, and 25 neurons respectively, and used the tanh activation<br> 
    function. I used 3 hidden layers with increased numbers of neurons for the first two hidden layers to try and<br>
    add more information for the machine to generate better performance and try to attempt better accuracy. I decided<br>
    to use the tanh activation function to also see if it would work better for the data. 

    - I was not able to achieve the target model performance of 75%, the best I was able to do was 72.54%, which was<br> 
    actually the initial model used before trying to optimize the model for better performance. The model I am<br> 
    using as my basis for these results was the next highest with 72.48%.

    - Steps taken to try and increase model performance:
        - First Attempt:
            - Decreased the number of features during the data preprocessing step:
                - Removed the USE_CASE column to see if it was considered a 'noisy' feature
                - Adjusted the value used to determine which values would be binned into the 'Other' column for both the<br>
                APPLICATION_TYPE and CLASSIFICATION columns. 
            - Added an extra hidden layer
            ![Attempt_1_to_Increase_Performance](/Images/Optimization_Attempt_1_Model.png)
            ![Attempt_1_Evaluation](/Images/Optimization_Attempt_1_Accuracy.png)

        - Second Attempt:
            - Used same preprocessed data as first attempt.
            - Used same number of hidden layers as first attempt, and each hidden layer had the same number of neurons as<br> 
            the first attempt
            - Changed the activation function to tanh instead of relu
            ![Attempt_2_to_Increase_Perfomance](/Images/Optimization_Attempt_2_Model.png)
            ![Attempt_2_Evaluation](/Images/Optimization_Attempt_2_Accuracy.png)
        
        - Third Attempt:
            - Used the same preprocessed data as first and second attempts
            - Used the same number of hidden layers and number of neurons per hidden layer as attempt 2
            - Increased the number of epochs from 100 to 175
            ![Attempt_3_to_Increase_Performance](/Images/Optimization_Attempt_3_Model.png)
            ![Attempt_3_Evaluation](/Images/Optimization_Attempt_3_Accuracy.png)

        - Fourth Attempt:
            - Still used 3 hidden layers
            - Decreased the number of neurons per hidden layer to 50, 25, 10 (just to see how this affected the accuracy)
            - Increased number of epochs to 200
            ![Attempt_4_to_Increase_Performance](/Images/Optimization_Attempt_4_Model.png)
            ![Attempt_4_Evaluation](/Images/Optimization_Attempt_4_Accuracy.png)

        - Fifth Attempt:
            - Still using 3 hidden layers
            - Increased number of neurons per layer to 100, 50, 25
            - Used 200 for number of epochs
            ![Attempt_5_to_Increase_Perfomance](/Images/Optimization_Attempt_5_Model.png)
            ![Attempt_5_Evaluation](/Images/Optimization_Attempt_5_Accuracy.png)

        - Sixth Attempt:
            - Used original preprocessed data with 43 features and 1 target
            - Used 3 hidden layers with number of neurons per layer being 100, 50, 25
            - Used tanh activation
            - Used 200 epochs
            ![Attempt_6_to_Increase_Performance](/Images/Optimization_Attempt_6_Model.png)
            ![Attempt_6_Evaluation](/Images/Optimization_Attempt_6_Accuracy.png)

### Summary:
- Overall, the deep learning model had about a 72.5% accuracy when trying to determine which organizations were successful<br>
after being funded by Alphabet Soup. However, the deep learning model was not able to perform at the desired accuracy level<br>
of 75%. There could be a chance of achieving the desired accuracy level if the number of epochs run for the model is increased<br>
significantly, but doing so would require a lot of time and machine power for the model to run. The benefit of adjusting the<br>
deep learning model to achieve the desired accuracy level may not be worth the amount of time and machine power it would take<br>
to reach that level, so a different machine learning model may be more appropriate to use for this particular data set.  