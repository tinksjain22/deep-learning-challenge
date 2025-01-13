# **Report on the Neural Network Model for Alphabet Soup**

## **Overview of the Analysis**  
The purpose of this analysis was to create a deep learning model to help Alphabet Soup, a nonprofit organization, strategically select funding applicants. The model was designed to predict the likelihood of an applicant's success after receiving funding from the organization, enabling Alphabet Soup to make informed funding decisions.

## **Results**

**Data Preprocessing**

- **Target Variable:**  
  The target variable for the model is **IS_SUCCESSFUL**, which indicates whether an organization that received funding was successful or not.

- **Features:**  
  The features used for the model include 59 variables derived from the following columns:  
  - **APPLICATION_TYPE**
  - **AFFILIATION**
  - **CLASSIFICATION**
  - **USE_CASE**
  - **ORGANIZATION**
  - **STATUS**
  - **INCOME_AMT**
  - **SPECIAL_CONSIDERATIONS**
  - **ASK_AMT**
  - **NAME_CATEGORY**  
  These columns were processed using `np.get_dummies()` for binary classification, converting categorical data into numerical values that could be used for model training.

- **Variables to Remove:**  
  The **NAME** and **EIN** columns were removed from the dataset. These variables were used for identifying organizations and were not relevant for predicting success, as they do not contribute directly to the model’s decision-making process.

**Compiling, Training, and Evaluating the Model**

- **Neurons, Layers, and Activation Functions:**  
  The final model consisted of the following architecture:
  - 1 input layer with 80 neurons
  - 2 hidden layers:
    - First hidden layer with 80 neurons and **ReLU** activation function
    - Second hidden layer with 40 neurons and **ReLU** activation function  
  The **ReLU** activation function was used in the hidden layers to introduce non-linearity, enabling the model to learn complex patterns from the data. 

  - The output layer used a **sigmoid** activation function to produce a binary outcome (IS_SUCCESSFUL: Yes or No).

- **Achieving Target Performance:**  
  The model successfully achieved an accuracy of **75.6%**, which surpasses the target accuracy of 75%. This means the model was able to correctly predict whether an organization would be successful after receiving funding in 75.6% of cases.

- **Steps Taken to Increase Model Performance:**  
  Several optimization strategies were implemented to improve the model’s accuracy:
  - **Adjusting the APPLICATION_TYPE column:** Application types with fewer than 10 occurrences were grouped into an “Other” category to prevent rare application types from negatively affecting the model’s performance.
  - **Categorizing the NAME column:** The organization names were split into various categories based on keywords. This allowed the model to better predict success by leveraging patterns in the names of organizations, which helped enhance predictive accuracy.

## **Summary**

The deep learning model performed well, exceeding the target accuracy of 75% and providing a useful tool for Alphabet Soup to assess funding applicants. However, it is important to note that the model is not perfect and may require additional fine-tuning or special considerations, particularly when evaluating applicants seeking large amounts of funding.

## **Recommendation for a Different Model:**

An alternative model to solve this classification problem could be a **logistic regression model**. Logistic regression is well-suited for binary classification tasks like this one, where the outcome is either success or failure. By using logistic regression, Alphabet Soup could interpret the model’s coefficients and gain a clearer understanding of how each feature impacts the likelihood of an applicant's success. This transparency could complement the deep learning model’s performance, offering a more interpretable solution for decision-making.
