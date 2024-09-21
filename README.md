# Churn Modelling
In the fast-paced world of modern banking, customer retention is a critical focus. One day, a team of analysts at a leading financial institution was given a challenge: identify the factors that lead customers to leave, or "churn," and develop a model to predict churn based on customer data. This model would enable the bank to intervene early and take action to retain valuable clients.

The project aimed to analyze customer data, uncover patterns related to churn, and build predictive models that could forecast whether a customer would leave the bank. Through this process, we could identify key variables that contribute to customer churn and provide actionable insights to reduce it.

To achieve these goals, we adopted a problem-solving approach that involved:
1. Understanding the data, identifying potential gaps, and cleaning it for analysis.
2. Visualizing churn-related patterns across different features like geography, gender, and tenure.
3. Implementing machine learning models (Logistic Regression and Random Forest) to predict churn and evaluate their performance.

### 2. Dataset Description

The dataset used for this project is the **Churn_Modelling.csv** file, sourced from **Kaggle**. It contains 10,000 records of bank customers and includes information about their demographics, account details, and whether or not they exited (churned).

#### Dataset Structure:
- **Source:** Kaggle - Churn Modelling Dataset
- **Type and Size:** 
  - Rows: 10,000 
  - Columns: 14 (after preprocessing, 11 columns are used for modeling)
  
#### Variables:
1. **RowNumber:** Sequence of customers (not used in analysis)
2. **CustomerId:** Unique customer ID (not used in analysis)
3. **Surname:** Customer’s last name (not used in analysis)
4. **CreditScore:** Customer's credit score (integer)
5. **Geography:** Customer's location (nominal, 3 categories: France, Spain, Germany)
6. **Gender:** Male or Female (nominal)
7. **Age:** Customer's age (numeric, years)
8. **Tenure:** Number of years the customer has been with the bank (integer)
9. **Balance:** Customer’s bank balance (numeric, currency)
10. **NumOfProducts:** Number of bank products the customer is using (ordinal, 1-4)
11. **HasCrCard:** Whether the customer has a credit card (binary, Yes/No)
12. **IsActiveMember:** Whether the customer is an active member (binary, Yes/No)
13. **EstimatedSalary:** Customer’s estimated salary (numeric, currency)
14. **Exited:** Whether the customer exited the bank (binary: 1 = exited, 0 = retained)

#### Data Quality:
- **Missing values:** There are no missing values in the dataset.
- **Duplicates:** No duplicate entries are present.
- **Measurement Scale:** Variables range from nominal (e.g., gender) to ordinal (e.g., number of products) and continuous (e.g., balance, age).
- **Data accuracy:** The dataset seems reliable and clean, with no obvious errors.

### 3. Objectives of the Project

The primary objectives of the project were:
1. **Content-related objectives:**
   - Identify the factors most strongly associated with customer churn.
   - Understand the distribution of churn across different customer segments (e.g., by gender, geography).
   
2. **Statistical objectives:**
   - Develop predictive models to estimate the likelihood of churn for each customer.
   - Evaluate the performance of Logistic Regression and Random Forest classifiers to determine the best model for churn prediction.

Key questions we aimed to answer:
- What are the main factors driving customer churn?
- Can we predict churn accurately using customer data?
- Which model performs better in predicting churn, and how can we improve its performance?

### 4. Tools

We used the following tools and libraries for the analysis:
- **Pandas:** For data manipulation and exploration.
- **NumPy:** For numerical computations.
- **Matplotlib and Seaborn:** For data visualization.
- **Scikit-learn:** For machine learning models (Logistic Regression, Random Forest) and evaluation metrics (accuracy, confusion matrix, classification report, ROC curve).
- **Python Programming Language.**

### 5. Insights

#### Churn Rate
The pie chart shows that about **20.37%** of customers churned, while **79.63%** were retained. This insight helped us focus on understanding the factors behind churn.

![download](https://github.com/user-attachments/assets/237987a4-f297-49d3-afe7-fcb2089f1f90)




#### Churn by Gender
The bar plot revealed that males had a slightly higher churn rate than females, suggesting that gender may be a modest factor in customer retention.

![download](https://github.com/user-attachments/assets/d2be22e9-4dd8-4225-8ca5-2145ee99d228)



#### Churn by Geography
We noticed that customers from Germany had the highest churn rate compared to France and Spain. This geographic trend indicated potential regional issues in service or customer satisfaction.

![download](https://github.com/user-attachments/assets/1c00deea-08a4-4bc7-9452-0f908bb2c1b0)


#### Churn by Tenure
Customers with shorter tenures (1–5 years) showed a higher churn rate compared to long-term customers. This trend suggested that newer customers might be at higher risk of leaving the bank.

![download](https://github.com/user-attachments/assets/063f4ea9-fe0e-4b6d-beae-22af509a60d1)




#### Churn by Balance and Estimated Salary
- Customers with low or zero balances tended to churn more frequently.
- Interestingly, salary did not show a clear trend in relation to churn, implying that income alone may not determine customer loyalty.

![download](https://github.com/user-attachments/assets/d7b32f3a-4d4f-4010-a14a-83324e2edb42)
![download](https://github.com/user-attachments/assets/86f0dbdc-312c-4fd8-af30-b2ed7ce3e295)


#### Churn by Number of Products and Active Membership
- Customers with only 1 or 2 products were more likely to churn compared to those with more products.
- Active members were significantly more likely to stay, reinforcing the value of customer engagement.

![download](https://github.com/user-attachments/assets/5923b88b-28fc-41fd-95e9-77a8b28be594)
![download](https://github.com/user-attachments/assets/7adf83f4-bc3b-4e34-abd9-c1dac63c7b49)



### Model Results

#### Logistic Regression Results
- **Accuracy:** 81.55%
- **Confusion Matrix:** 
  \[
  \begin{bmatrix}
  1527 & 68 \\
  299 & 106
  \end{bmatrix}
  \]
- **Classification Report:**
  - Precision for churn: 60.92%
  - Recall for churn: 26.17%
  
Logistic Regression showed decent accuracy but struggled with predicting churn accurately, as seen from the relatively low recall.

#### Random Forest Classifier Results
- **Accuracy:** 86.55%
- **Confusion Matrix:** 
  \[
  \begin{bmatrix}
  1555 & 40 \\
  216 & 189
  \end{bmatrix}
  \]
- **Classification Report:**
  - Precision for churn: 82.54%
  - Recall for churn: 46.67%
  
Random Forest outperformed Logistic Regression, especially in detecting churn (higher recall). The ROC curve and AUC score of 0.84 further demonstrated its strength.

### 6. Recommendations and Future Analysis

1. **Improving Customer Retention:** The bank should focus on customers with low balances, short tenures, and limited product engagement. Offering targeted promotions, loyalty programs, or personalized services could help reduce churn in these segments.
  
2. **Regional Strategies:** Since churn is highest in Germany, the bank should investigate region-specific factors, such as service issues or competition, that might be influencing customer behavior.

3. **Future Analysis:** 
   - Collect more data on customer interactions and satisfaction to build a more comprehensive churn prediction model.
   - Experiment with other machine learning models (e.g., Gradient Boosting, XGBoost) to further improve prediction accuracy.
