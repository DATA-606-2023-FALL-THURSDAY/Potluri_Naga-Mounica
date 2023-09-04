# <p align="center"> Enhancing On-Time Delivery Predictions in E-Commerce: A Predictive Modeling Approach </p>

- Author: Naga Mounica Potluri
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- GitHub: [https://github.com/TI29978/UMBC-DATA606-FALL2023-THURSDAY], [https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica]
- LinkedIn: https://www.linkedin.com/in/mounica-potluri-3576b928b/
- Code: 
- Link to your PowerPoint presentation file
- Link to your  YouTube video 
    
## 1. Background

The e-commerce business has had a remarkable development in the modern environment of globalised trade and digital connection. Due to this transition, prompt and effective product distribution has become of utmost importance. For e-commerce businesses, the ability to forecast with a high degree of accuracy whether a product will be delivered on time is becoming increasingly crucial. With the help of this predictive capability, businesses can make better judgements, streamline their logistical processes, and better satisfy client needs.

The prompt delivery of goods has important effects on the standing and success of e-commerce businesses; it is not only an issue of convenience for the client. Customer discontent, an increase in customer service requests, and perhaps the loss of profitable business possibilities can all result from product delivery delays. As a result, improving the total customer experience and maintaining a competitive edge in the e-commerce sector need the creation of precise predictive models for on-time delivery.

This study intends to investigate the following essential concerns in light of the challenges and opportunities that on-time delivery within the e-commerce sector presents:
1.	How well can a global e-commerce company's operational structure use predictive modelling to determine if a product will be delivered on time?
2.	What complex elements affect the timely delivery of goods, and how can this nuanced knowledge be applied to improve and optimise the delivery procedures?

We want to uncover practical insights by probing these crucial issues in order to help e-commerce companies streamline their processes, reduce delivery delays, and, ultimately, exceed customers' expectations.
## 2. Data 

Data Sources: The dataset is obtained from Kaggle and is related to an international e-commerce company's shipping data.

Data Size: The dataset is relatively small, with a size of approximately 124 KB.

Data Shape: The dataset contains 10,999 rows and 12 columns.

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
The "Reached.on.Time_Y.N" variable, which denotes whether the product arrived on time or not, is the target variable for the machine learning models. It has the binary values of 1 (Not on time) and 0 (On time), and it is a variable.

### Potential Features/Predictors:
All columns except the target variable may have potential to be utilised as feature columns in machine learning models. The following are listed: ID, Warehouse_block, Mode of Shipping, Customer Care Calls, Customer Rating, Cost of the Product, Prior Purchases, Product Importance, Gender, Discount Offered, and Weight in Gms.
