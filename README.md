# deep-learning-challenge

## **Background:**  
Alphabet Soup, a nonprofit, seeks a tool to predict which funding applicants are most likely to succeed. Using a dataset of over 34,000 organizations that received funding, you will build a binary classifier to determine if applicants will succeed based on their features.

### **Step 1: Data Preprocessing**  
- Load the dataset and identify the target variable (**IS_SUCCESSFUL**) and features.  
- Drop identification columns (**EIN**, **NAME**).  
- Analyze unique values in categorical columns and bin "rare" categories into "Other."  
- Encode categorical variables with `pd.get_dummies()` and split the data into features (X) and target (y).  
- Scale the data using `StandardScaler()`.

### **Step 2: Model Development**  
- Design a neural network model using TensorFlow and Keras for binary classification.  
- Determine the number of neurons and layers based on the input features.  
- Compile, train, and evaluate the model.  
- Implement a callback to save model weights every five epochs and assess loss and accuracy.  
- Save the model in an HDF5 file named **AlphabetSoupCharity.h5**.

### **Step 3: Model Optimization**  
- Aim for an accuracy higher than 75%.  
- Optimize the model by adjusting the data (e.g., dropping more columns, changing bin sizes), adding neurons or layers, and adjusting activation functions or epochs.
