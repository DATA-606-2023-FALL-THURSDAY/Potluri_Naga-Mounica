# <p align="center"> Enhancing On-Time Delivery Predictions in E-Commerce: A Predictive Modeling Approach </p>

- Author: Naga Mounica Potluri
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- GitHub: [https://github.com/TI29978/UMBC-DATA606-FALL2023-THURSDAY], [https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica]
- LinkedIn: https://www.linkedin.com/in/mounica-potluri-3576b928b/
- Code: https://github.com/TI29978/Enhancing-On-Time-Delivery-Predictions-in-E-Commerce/blob/519548aacc2c7ed34c4066107efd30f9ca01a3e3/Mounica%20606%20project.ipynb
- Link to your PowerPoint presentation file
- Link to your  YouTube video 
    
## 2. Background

The e-commerce business has had a remarkable development in the modern environment of globalised trade and digital connection. Due to this transition, prompt and effective product distribution has become of utmost importance. For e-commerce businesses, the ability to forecast with a high degree of accuracy whether a product will be delivered on time is becoming increasingly crucial. With the help of this predictive capability, businesses can make better judgements, streamline their logistical processes, and better satisfy client needs.

The prompt delivery of goods has important effects on the standing and success of e-commerce businesses; it is not only an issue of convenience for the client. Customer discontent, an increase in customer service requests, and perhaps the loss of profitable business possibilities can all result from product delivery delays. As a result, improving the total customer experience and maintaining a competitive edge in the e-commerce sector need the creation of precise predictive models for on-time delivery.

This study intends to investigate the following essential concerns in light of the challenges and opportunities that on-time delivery within the e-commerce sector presents:
1.	How well can a global e-commerce company's operational structure use predictive modelling to determine if a product will be delivered on time?
2.	What complex elements affect the timely delivery of goods, and how can this nuanced knowledge be applied to improve and optimise the delivery procedures?

We want to uncover practical insights by probing these crucial issues in order to help e-commerce companies streamline their processes, reduce delivery delays, and, ultimately, exceed customers' expectations.

## 3. Data 
**Data Sources:** The dataset is obtained from Kaggle and is related to an international e-commerce company's shipping data.
**Data Size:** The dataset is relatively small, with a size of approximately 124 KB.
**Data Shape:** The dataset contains 10,999 rows and 12 columns.
Each entry in the dataset reflects a record or transaction pertaining to a shipment of goods made by the online retailer. In further detail, every row corresponds to a particular shipment or order placed by a consumer

### Data Dictionary
Here's a breakdown of the columns in the dataset:
1.	ID: ID number of customers (Integer).
2.	Warehouse_block: Warehouse block categorization (Categorical - A, B, C, D, E).
3.	Mode_of_Shipment: Mode of shipment (Categorical - Ship, Flight, Road).
4.	Customer_care_calls: The number of calls made for inquiries about the shipment (Integer).
5.	Customer_rating: Customer rating (Integer, 1 to 5, with 1 being the lowest and 5 being the highest).
6.	Cost_of_the_Product: Cost of the product in US Dollars (Integer).
7.	Prior_purchases: The number of prior purchases made by the customer (Integer).
8.	Product_importance: Importance categorization of the product (Categorical - Low, Medium, High).
9.	Gender: Gender of the customer (Categorical - Male, Female).
10.	Discount_offered: Discount offered on the specific product (Integer).
11.	Weight_in_gms: Weight of the product in grams (Integer).
12.	Reached.on.Time_Y.N: Target variable, where 1 indicates that the product has NOT reached on time, and 0 indicates it has reached on time (Binary classification).

### Target Variable/Label:
- The "Reached.on.Time_Y.N" variable, which denotes whether the product arrived on time or not, is the target variable for the machine learning models. It has the binary values of 1 (Not on time) and 0 (On time), and it is a variable.

### Potential Features/Predictors:
- All columns except the target variable may have potential to be utilised as feature columns in machine learning models. The following are listed: ID, Warehouse_block, Mode of Shipping, Customer Care Calls, Customer Rating, Cost of the Product, Prior Purchases, Product Importance, Gender, Discount Offered, and Weight in Gms.


## 4. Exploratory Data Analysis
- On the dataset, performed an exploratory data analysis (EDA), omitting all other columns and concentrating on the target variable "Reached.on.Time_Y.N" and chosen characteristics. The following are the main conclusions and actions taken during the EDA:

### 4.1 Data Summary Statistics
For each of the dataset's numerical columns, we computed summary statistics. 
Here are some significant figures:
1.	Customer_care_calls: Mean of 4.05, with a minimum of 2 and a maximum of 7.
2.	Customer_rating: Mean of 2.99, with a minimum of 1 and a maximum of 5.
3.	Cost_of_the_Product: Mean cost of 210.20, ranging from 96 to 310.
4.	Prior_purchases: Mean of 3.57, with values between 2 and 10.
5.	Discount_offered: Mean discount of 13.37%, ranging from 1% to 65%.
6.	Weight_in_gms: Mean weight of 3634.02 grams, with weights ranging from 1001 to 7846 grams.

### 4.2 Data Cleansing
**4.2.1 Missing Values**: The dataset contains no missing values; all columns include non-null items.

**4.2.2 Duplicate Rows**: The dataset contains no duplicate rows.
### 4.3 Data Visualizations
#### Plot 1: Count Plot for the Product to Reaching on Time or Not
- The count plot represents the count v/s reached on time or not. From this plot, we can say that the data contains more products that did not reach on time than those of reached on time.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/5e684b02-eec8-47bb-9472-249ac427dcf4)

#### Plot 2: Count v/s Features
- The below graphs represent the count v/s of all the features that are present in the data. Those are count v/s Warehouse_block, count v/s mode_of_shipement, count v/s Product_importance, count v/s Customer_care_calls, count v/s customer_rating, count v/s Cost_of_the_product, count v/s prior_purchase, count v/s discount_offered, count v/s weight_in_gms, count v/s reached.on.time_Y.N

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/3b58a011-8741-4cd2-b1ee-cdd444de0599)

#### Plot 3: Count plot for Warehouse Block
- This plot represents the total count of the products that reached on time or not from a warehouse block. In this graph, we can see that there are products in a warehouse that reach on time and there are also products from the same warehouse that did not reach on time.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/0adfa258-ce84-4bbc-bff6-038303b832a7)

#### Plot 4: Count Plot for Mode of Shipment
- This plot represents the total count of the products which reached on time or not by a Mode of shipment. In this graph, we can see that there are products by a Mode of shipment which reached on time and there are also products by the same Mode of shipment that did not reach on time.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/53aa4812-a1ba-4a5d-99ec-63d26eefc933)

#### Plot 5: Cost of Product vs Discount Offered
- The scatter plot represents the cost_of_the_products v/s discount_offered based on whether the product reached on time or not. From this plot, we can say that the chance of the product reaching on time is higher when the discount on the product is less than 10% and the chances of the product not to reach on time is higher when the discount on the product is higher than 10%.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/f6948731-bc35-447d-a397-5ffdcf3cf0d6)

#### Plot 6: Cost of product vs Weight
- The scatter plot represents the cost_of_the_products v/s Weight_in_gms based on whether the product reached on time or not. From this plot, we can say that the chance that the product will not arrive on time is higher when the product weighs between 2000-4000 gms and the chances that the product reaching on time is higher when the cost of the product is high with the weighing between 1000-2000 gms.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/ed8083b0-a9a9-4df6-ac0e-aa4b89b029f1)

#### Plot 7: Customer rating vs Discount offered
- The scatter plot represents the Customer_rating v/s Discount_offered based on whether the product reached on time or not. From this plot, we can say that the chance of the product will not reach on time when the discount is higher them 10% with respect to the customer rating and the chances of the product reaching on time is higher when the discount of the product is less than 10% we can also see that the customer rating is also high when it reaches on time.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/9477f1c1-a2a8-412b-a25c-c7ad93e80114)

#### Plot 8: Heatmap Showing the Correlation between the columns
- From the heatmap, the goal is to see the correlation between the target variable and the features. We can see that the Discount_offered is highly correlated to the target variable that is Reached.on.time_Y.N.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/b24e2c87-1bac-403d-9e7b-25942832b2cd)

### 4.4 Data Tidiness
Given that each row reflects a distinct order and each column has a distinctive quality or attribute of that order, the resultant dataset is thought to be tidy. The information is organized and prepared for additional analysis or machine learning operations

# 5. Model Training
## 5.1 Models Used for Machine Learning
1.	Logistic Regression
2.	Random Forest Classifier
3.	Gradient Boosting Classifier
4.	XGBoost Classifier (Hyperparameter tuned)
5.	Best Random Forest Classifier (After Hyperparameter Tuning)
6.	Best Gradient Boosting Classifier (After Hyperparameter Tuning)

## 5.2 Process of Training The Models
### 5.2.1.Train-Test Split
We divided the data into an 80/20 train-test split, using 80% of the data for training the models and 20% for testing. With the use of this split, it is possible to assess how effectively the models generalize to new shipments using previously unreported data.

### 5.2.2 Data Preprocessing
The Column ‘ID’ was dropped from the dataset as it does not have any usage in machine learning.
Categorical Variable Labeling: We manually labeled the category columns to get them ready for machine learning models. Specifically:
- The "Warehouse_block" column was mapped to numerical values: 'A' -> 0, 'B' -> 1, 'C' -> 2, 'D' -> 3, and 'F' -> 4.
- The "Mode_of_Shipment" column was mapped to numerical values: 'Ship' -> 0, 'Flight' -> 1, 'Road' -> 2.
- The "Product_importance" column was mapped to numerical values: 'low' -> 0, 'medium' -> 1, 'high' -> 2.
- The "Gender" column was mapped to numerical values: 'F' -> 0, 'M' -> 1.

**Standardization:** 
The StandardScaler was used to standardize the numerical characteristics. A frequent preprocessing procedure called standardization adjusts numerical characteristics to have a mean of 0 and a standard deviation of 1. Models that depend on distance measures, such as logistic regression, and gradient boosting, perform better as a result of this phase. For consistency, the StandardScaler was applied to the training and testing sets after being fitted on the training data.

### 5.2.3 Python Packages
For a variety of tasks throughout the project, we used the Python packages and libraries listed below:
- scikit-learn: For building, training, and evaluating machine learning models.
- pandas: For data manipulation and analysis.
- numpy: For numerical operations.
- matplotlib and seaborn: For data visualization.
- pickle: For saving the trained StandardScaler and models

### 5.2.4 Development Environment
Kaggle served as the project's development environment since it offers a Jupyter Notebook environment with access to crucial tools and resources for data science and machine learning. Kaggle is appropriate for data science projects since it enables seamless collaboration, code exchange, and simple access to datasets.

## 5.3 Measuring and Comparing Model Performance
We employed the following assessment indicators to gauge and compare the models' performance:
- Accuracy: This statistic assesses how accurately the model's predictions were made in general. It is the proportion of accurate forecasts to all predictions.
- Precision: How much of the model's favorable predictions were accurate is known as precision. In order to compute it, divide the total number of true positives by the total number of false positives, or TP / (TP + FP).
- Recall: Recall indicates the proportion of real positive cases that the model accurately predicted. TP / (TP + FN), where TP is the total number of true positives and FN is the total number of false negatives, is the formula used to compute it.
- F1-Score: The F1-score, which is important when there is an imbalance in the classes, is the harmonic mean of accuracy and recall. It is calculated as 2 * (Precision * Recall) / (Precision + Recall) and strikes a balance between the two measurements.
- Confusion Matrix: A confusion matrix gives a thorough description of the right and wrong guesses. True positives (TP), true negatives (TN), false positives (FP), and false negatives (FN) are a few of the measures it offers.

## 5.4 Result and Interpretations
### 1. Logistic Regression:
 
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/ac234e3e-c4ff-4cc4-8856-7d5f430f30b2)


- Accuracy: 64.45%
- True Positives (TP): 913 - The model correctly predicted that 913 shipments would reach on time.
- True Negatives (TN): 505 - The model correctly predicted that 505 shipments would not reach on time.
- False Positives (FP): 390 - The model incorrectly predicted that 390 shipments would reach on time when they didn't.
- False Negatives (FN): 392 - The model incorrectly predicted that 392 shipments would not reach on time when they did.
Interpretation: The logistic regression model was 64.45% accurate, meaning that in 64.45% of situations, it was able to predict whether a delivery will be on time or delayed. However, because of its moderate precision, this model could not offer the greatest results in terms of prediction. It will need further investigation to evaluate other parameters.

### 2. Random Forest Classifier:
 
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/b78ac4c1-eace-4987-80e6-53eb8f3ebddd)


- Accuracy: 65.95%
- True Positives (TP): 817 - The model correctly predicted that 817 shipments would reach on time.
- True Negatives (TN): 634 - The model correctly predicted that 634 shipments would not reach on time.
- False Positives (FP): 261 - The model incorrectly predicted that 261 shipments would reach on time when they didn't.
- False Negatives (FN): 488 - The model incorrectly predicted that 488 shipments would not reach on time when they did.
Interpretation: With an accuracy of 65.95%, the random forest classifier performed marginally better than logistic regression. It suggests that the predictions generated by this ensemble model, which comprises many decision trees, were more accurate. To further understand its performance, we must investigate more measures.

### 3. Gradient Boosting Classifier:

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/a0c2eac1-a6a7-4f7d-ac21-d5820d3c2a6e)

- Accuracy: 68.73%
- True Positives (TP): 733 - The model correctly predicted that 733 shipments would reach on time.
- True Negatives (TN): 779 - The model correctly predicted that 779 shipments would not reach on time.
- False Positives (FP): 116 - The model incorrectly predicted that 116 shipments would reach on time when they didn't.
- False Negatives (FN): 572 - The model incorrectly predicted that 572 shipments would not reach on time when they did.
Interpretation: An even greater level of accuracy—68.73%—was obtained using the gradient boosting classifier. Both logistic regression and random forest underperformed compared to an ensemble model, which creates trees in a sequential manner to rectify faults in the prior trees. However, more research is necessary.

## 5.5 Feature Importance
In this section, we plotted Top 10 Important Features for Each Model. This Section gives us information of which and How Much a Feature in Important in Model Training.
1. Random Forest:

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/32810a05-cd31-42e7-8046-1dbb3a96ade3)

2. Gradient Boosting:
 
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/67eca764-cc0c-48c5-9d9b-72e746ec9d7f)

3. Random Forest (After Hypertuning):
 
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/9ebaa8a5-48a9-402c-8653-9e3a4596d8e3)

4. Gradient Boosting(After Hyper Tuning):
 
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/cb5bb228-3db3-4f20-bcf0-59bdbd7ab0a0)

5. XGBoost (Hypertuned):
 
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/63eb736a-ed85-4e0d-9b13-fc84f246f49a)


## 6. Application of Trained Model
We have created a user-friendly web application using the Flask framework to make the predictive capability of our trained machine learning models available to a wider audience. With the help of this online application, consumers may interact with our algorithms and get immediate predictions about whether a product will arrive on time or not. We choose Flask because of its clarity, adaptability, and simplicity in integrating with our machine learning algorithms.
You can read a quick description of the online application and how it allows users to exploit our models' predictive power below:
### 6.1 Web Application Overview
Our online application offers consumers a simple and clear interface to enter pertinent cargo information. The application uses our trained models to produce predictions when the user enters the necessary information. Users are informed right away if a product delivery is anticipated to be on time or delayed.

### 6.2 Features of the Web Application
1.	Input Fields: Users may add a variety of shipping-related information, such as warehouse block, mode of shipment, customer service calls, customer rating, cost of the goods, previous purchases, significance of the product, gender, discount provided, and weight in grammes.
2.	Predictive Power: Our machine learning models, such as XGBoost, are implemented in the background. These models have been accuracy-tuned after being trained on large datasets.
3.	User-Friendly Feedback: Users receive simple response after making their opinion, including whether the delivery is anticipated to arrive on time or be delayed.
4.	Accessibility: Our web application is made to be accessed from several platforms and on different devices, making it easy for users to access on desktop and mobile platforms.

### 6.3 How to Use the Web Application
Using the application is a straightforward process:
1.	You may use your favourite web browser to access the web app.
2.	Fill up the entry blanks with the necessary cargo information.
3.	To start the delivery prediction procedure, click the "Predict Delivery" button.
4.	Observe the forecast result that is shown on the screen.

### 6.4 Why Flask
Since Flask is a quick and effective development framework, we used it for our application. Anyone interested in forecasting delivery outcomes may readily access our trained machine learning models because to Flask's ability to incorporate them into a web-based interface. Grinberg (2018)
### 6.5 Screenshots

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/ddbce044-7284-40fe-a5bb-96f1c4cd25c6)

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/54f8d0b4-154e-479e-815c-2fd69e4c56d1)

# 7. Conclusion
Through the use of predictive modelling, we set out on a mission in this project to improve on-time delivery estimates in the e-commerce industry. We have created, trained, and successfully used machine learning models that can forecast whether a product will arrive on time or not. Our research has enormous promise for the supply chain management and e-commerce sectors, providing insightful information and foresight tools to enhance user experience and operational effectiveness.
## 7.1 Summary of Our Work and Its Potential Application
Our research attempted to overcome significant problems with on-time delivery in the e-commerce industry. We performed exploratory data analysis using a dataset from a global e-commerce firm, preprocessed the data, and trained machine learning models including Logistic Regression, Random Forest, Gradient Boosting, and XGBoost. To attain the best accuracy, we further fined-tune these models (Kotsiantis et al. (2007), Pedregosa et al. (2011), Raschka (2015), García et al. (2016)).
## 7.2 Usage of Our Research
Our research has several possible uses:
1.	Operational Efficiency: Our models may be used by e-commerce businesses to streamline their delivery procedures, cut down on delays, and better manage resources.
2.	Customer Satisfaction: On time delivery boost client loyalty and happiness, which enhances the reputation of the company.
3.	Inventory Management: Predictive analytics may help with more effective inventory management, lowering expenses related to excess or inadequate stock.
4.	Decision Support: Our models may assist logistics managers in making data-driven choices by acting as decision support tools.

## 7.3 Limitations of Our Work
Despite the encouraging outcomes, our project has certain drawbacks:
1.	Dataset Size: Because the training dataset was so limited, the models' capacity to generalise to bigger and more varied datasets may be constrained.
2.	Feature Engineering: Model performance may be improved by using more complex feature engineering approaches.
3.	External Factors: Our models do not take into consideration outside variables that may affect delivery timeframes, such as the state of the weather or traffic.

## 7.4 Lessons Learned
During the course of this study, we discovered numerous things:
1.	Data Preprocessing: It is impossible to overestimate the significance of data preparation, which includes feature scaling and encoding categorical variables.
2.	Model Selection: Performance is greatly influenced by the careful selection of models and their hyperparameters.
3.	Interpretability: The interpretation and justification of model predictions to stakeholders is crucial for model adoption.

## 7.5 Future Research Directions
Our research establishes the framework for further study in the area of logistics and e-commerce:
1.	Integration of External Data: To improve forecast accuracy, future research might investigate the integration of external data sources including weather and traffic data.
2.	Real-Time Predictions: Constructing real-time prediction systems that take dynamic shifts in supply chain variables into consideration.
3.	Customer Behavior Analysis: To better understand how customer interactions affect delivery times, data on consumer behaviour will be analysed.
4.	Advanced Forecasting: Applying sophisticated time series forecasting techniques to make more precise delivery time predictions.
Our approach is a huge step in the right direction for e-commerce on-time delivery forecasts. There is a lot more opportunity for study and innovation in this field, even if our models provide useful insights and prediction powers. We may contribute to the continued development of supply chain management and e-commerce practises by iteratively improving our models and investigating new research directions.

# 8. References
- 1. Ballestar, M. T., Grau-Carles, P., & Sainz, J. (2019). Predicting customer quality in e-commerce social networks: a machine learning approach. Review of Managerial Science, 13, 589-603.
- 2. Gupta, M. K., Goel, M., Kumar, S., & Rawat, N. (2021). Multi-vendor ecommerce website. International Research Journal of Modernization in Engineering Technology and Science, 3(3), 142-147.
- 3. Iyer, K. N., Germain, R., & Frankwick, G. L. (2004). Supply chain B2B e‐commerce and time‐based delivery performance. International Journal of Physical Distribution & Logistics Management, 34(8), 645-661.
- 4. Lolla, R., Harper, M., Lunn, J., Mustafina, J., Assi, J., Loy, C. K., & Al-Jumeily OBE, D. (2022, December). Machine Learning Techniques for Predicting Risks of Late Delivery. In The International Conference on Data Science and Emerging Technologies (pp. 343-356). Singapore: Springer Nature Singapore.
- 5. Issaoui, Y., Khiat, A., Haricha, K., Bahnasse, A., & Ouajji, H. (2022). An advanced system to enhance and optimize delivery operations in a smart logistics environment. IEEE Access, 10, 6175-6193.
- 6. Grinberg, M. (2018). Flask web development: developing web applications with python. " O'Reilly Media, Inc.".
- 7. Kotsiantis, S. B., Zaharakis, I., & Pintelas, P. (2007). Supervised machine learning: A review of classification techniques. Emerging artificial intelligence applications in computer engineering, 160(1), 3-24.
- 8. Raschka, S. (2015). Python machine learning. Packt publishing ltd.
- 9. Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., ... & Duchesnay, É. (2011). Scikit-learn: Machine learning in Python. the Journal of machine Learning research, 12, 2825-2830.
- 10. García, S., Ramírez-Gallego, S., Luengo, J., Benítez, J. M., & Herrera, F. (2016). Big data preprocessing: methods and prospects. Big Data Analytics, 1(1), 1-22.

