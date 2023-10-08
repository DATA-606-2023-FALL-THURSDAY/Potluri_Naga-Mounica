# <p align="center"> Enhancing On-Time Delivery Predictions in E-Commerce: A Predictive Modeling Approach </p>

- Author: Naga Mounica Potluri
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- GitHub: [https://github.com/TI29978/UMBC-DATA606-FALL2023-THURSDAY], [https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica]
- LinkedIn: https://www.linkedin.com/in/mounica-potluri-3576b928b/
- Code: 
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


## 4. Exploratory Data Analysis
On the dataset, performed an exploratory data analysis (EDA), omitting all other columns and concentrating on the target variable "Reached.on.Time_Y.N" and chosen characteristics. The following are the main conclusions and actions taken during the EDA:

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
- To understand the data, we produced a number of visualizations using Plotly and Matplotlib:
**Plot 1:** Distribution of Customer Ratings

 <img width="952" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/d9fa6844-0153-41ef-8776-cc1e584cfc21">


- The distribution of customer evaluations is shown via a histogram, with the scores being similar for each rating.
**Plot 2:** Product Cost by Shipment Mode
 
<img width="952" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/8fe0f233-5b67-445a-b912-fcf8439a8f41">


- Based on the method of delivery, a boxplot shows the price of the items. It offers information on the spread and median price for each mode of shipment. The Box Plot showed similar statistics for each Shipment Mode.
**Plot 3:** Customer Rating vs. Customer Care Calls
 
<img width="952" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/c9e81bab-c343-4d1f-88af-88b9be663dd9">


- The correlation between customer feedback and the volume of customer service calls is represented by a scatter plot. Whether orders arrived on time or not determines the colour of the points.
**Plot 4:** Count Plot, Reached on Time (Target Variable)
 
<img width="520" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/Potluri_NagaMounica/assets/98859616/fd42a25e-20a1-4c70-8ef9-08e819d7efe6">


- A count plot shows the distribution of the target variable "Reached.on.Time_Y.N." It indicates the number of orders that reached on time (1) and those that did not (0).

### 4.4 Data Tidiness
Given that each row reflects a distinct order and each column a distinctive quality or attribute of that order, the resultant dataset is thought to be tidy. The information is organized and prepared for additional analysis or machine learning operations.
