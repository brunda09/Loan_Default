# Predicting Loan Default for Czech Bank
Loan lending plays an important role in our everyday life. However, loan default is still unavoidable, which carries a great risk and may even end up in a financial crisis. Therefore, it is particularly important for a bank to identify whether a candidate is eligible to receive a loan. In the past, the evaluation primarily depended on manual review, which was time-consuming and labor-intensive. Recently, banks have opted for machine learning approaches to automatically predict loan defaults based on certain features since it can highly enhance the accuracy and efficiency of the prediction.

### Dataset description 
For my analysis, the dataset is “1999 Czech Financial Dataset - Real Anonymized Transactions” which has been obtained from [data.world](https://data.world/lpetrocelli/czech-financial-dataset-real-anonymized-transactions). It contains real anonymized Czech Bank transactions, account information, and loan records released for PKDD’99 Discovery Challenge.

The relation between the 8 tables is given as:
![image](https://github.com/brunda09/Loan_Default/assets/59004632/98361280-07de-4007-a2a2-4ac10060efcd)

### Data Preprocessing
First datasets are merged based on common columns. Few columns were renamed for the purpose of `join()` operation. Then columns with more than 50% missing values were removed. Column containing target variable was converted to binary and also converted few categorical columns to numeric format. All the column values were normalized/standardized using `scale()` as few columns had only single digit values while others had more than 5 digit values. Most important step: In this dataset the number of non – defaulters are 275989 and defaulters are 26262. Under – sampling involves randomly removing instances from the majority class to create a more balanced distribution. This process ensures that the machine learning models are not biased towards predicting the majority class and can better identify patterns associated with the minority class. `ovun.sample` function from ‘ROSE’ library has been used here.

### Data Splitting
In this project we created a 80-20 split that is 80% training data and 20% testing data.

### Model Development and Evaluation
For my analysis I considered 3 cases for model development and evaluation for comparison of their performance: Full Model, Reduced model using correlation matrix, and LASSO reduced model.

