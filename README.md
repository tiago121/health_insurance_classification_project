# Health Insurance Cross-Sell

![image](https://user-images.githubusercontent.com/88745881/207366706-d390a2c4-23d7-4a5e-b06e-f80248e2c9be.png)


#### Made by Tiago Araujo

# Description

The project aims to rank customers with a higher likelihood of purchasing additional insurance products using data and machine learning algorithms, providing business insights for decision-making.
# 1. Business Problem


A fictional insurance company aims to increase its annual revenue per customer. To achieve this, they have adopted a Cross-Sell strategy: offering car insurance to customers who already have life insurance. However, the company does not have a substantial budget to conduct an extensive marketing campaign and contact all customers. Therefore, there is a need for a solution that reduces customer acquisition costs while maximizing revenue as much as possible.
# 2. Solution Strategy

**Step 01. Data Description:**

The data is from the Kaggle platform and can be categorized into consumer demographics (gender, age, region), vehicle characteristics (age, condition), and marketing information. Link: https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction


**Step 02. Feature Engineering:**

Objective: To facilitate analysis and discover new insights.

Process: Renaming variables, such as vehicle_damage and vehicle_age.

**Step 03. Exploratory Data Analysis (EDA)**

Objective: Gain intuitive understanding of the data.

Process: Conducting various analyses (univariate, bivariate, and multivariate) to identify interesting patterns.
Packages used: Seaborn, Matplotlib, and Pandas.

**Step 04. Data Preparation:**

Objective: Prepare the data for model training.

Processes:
a) Splitting the data into training, validation, and testing sets.
b) Applying StandScaler to the annual_premium variable.
c) Applying MinMaxScaler to the age and vintage variables.
d) Applying One-Hot and Target encoding to the gender, region_code, vehicle_age, and policy_sales_channel variables.
Packages used: Pandas and Sklearn.

**Step 5: Feature Selection**

Objective: Select the best features for model training.
Processes:
a) Training an automatic feature selection algorithm (Boruta).
b) Selecting the most important features.
Packages used: Boruta, Sklearn.

**Step 6: Training Machine Learning Models**

Objective: Train and evaluate the performance of models on the validation data.

Models trained: K-Nearest Neighbors (KNN), Logistic Regression, Extra Trees Classifier, Random Forest.

Selection of the model with the best performance/least computational cost.

Visualization tool: Cumulative Gains Curve.

Packages used: Scikitplot and Sklearn.


**Step 7. Fine Tuning:**

Objective: Adjust model parameters to optimize performance.
Process: Using the Random Search algorithm.
Packages used: Sklearn.

**Step 8: Translation to Business Metrics**

Objective: Translate the information into simple language to present to the business team.
Process: Using the model results to generate metrics such as ROI and cumulative gain.


# 3. Model Evaluation

I performed the machine learning modeling phase. Three models were trained using cross-validation:

* K-nearest neighbors
* Logistic regression
* XGBoost classifier

# 4. Top Insights

* Men are more likely to purchase insurance.
* Age influences interest in insurance, but in a non-linear manner; the most likely age group is between 40 and 50 years, while the least likely is elderly individuals.
* Region influences interest in insurance.

# 5. Business Result

Among the 76,622 clients, a total of 9,342 are interested in vehicle insurance. The average premium for an annual health insurance is $31,669. The following questions were answered based on the assumption that clients interested in vehicle insurance will sign the contract, and that the average value of vehicle insurance will be the same as health insurance.

**1) What percentage of clients interested in vehicle insurance will the call center be able to contact with 20,000 calls?**

A: 20,000 calls represent 26.24% of our database. Therefore, if the sales team made all these calls, the insurance company would be able to contact 71.29% of the clients interested in new vehicle insurance (the value of 0.7129 is our recall at 20,000).

**2) If the call center's capacity increases to 40,000 calls, what percentage of clients interested in acquiring vehicle insurance will the call center be able to contact?**

A: 40,000 calls represent 52.48% of our database. In this case, if the sales team made all these calls, the insurance company would be able to contact 99.48% of the clients interested in new vehicle insurance. The value of 0.9948 is our recall at 40,000.

**3) What is the return on investment (ROI)?**

A: The ROI follows the curve below, according to the cost and revenue that the business can assume.

![image](https://user-images.githubusercontent.com/88745881/206486621-2da95845-c1d0-4ee6-8e52-5dfb58d087ae.png)


# 6. Conclusion

* Based on the business results, the insurance company gains a competitive advantage over its competitors by reducing customer acquisition costs and increasing revenue.
* The sales team can focus their attention on the first 20,000 or 40,000 clients on the list and, in the future, it is possible to focus on the first K clients from the new list.
* Insights have been revealed, and with the obtained results, it is possible to simulate customer profiles, which is highly valuable for the company.

# 7. Next steps


1. Deploy the model in a scalable production environment.
2. Use other algorithms that can improve performance.
