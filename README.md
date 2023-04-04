# Customer-Lifetime-Analysis

### Application of CLV in marketing strategy 
Customer lifetime value (CLV) is a critical concept for businesses to understand. It refers to the total amount of money a customer will spend with your company over the course of their relationship with you. CLV helps businesses determine how much they should invest in acquiring and retaining customers. By investing in strategies that increase customer loyalty, businesses can increase revenue over time. Understanding CLV is essential for any business looking to build a successful marketing strategy, as it allows them to invest in their existing customers and build a loyal customer base that will support their business for years to come.

### Problem Statement 
A XYZ ecommerce company wants to target customer in their portfolio to understand their buying behavioral pattern. Company wants to introduce tailored marketing campaign to target them

### Methodology
1.	We are going to use CLV analysis to understand the customers and segment customers based on their buying patterns.
2.	We are going to estimate the customers value over the period of 6 months. 
3.	Model Used: We will predict Customer Lifetime Value using a Buy till You Die (in this case, we will use BG/NBD) model to predict the number of purchases based on Poisson distribution and the Gamma Gamma Model to predict the average amount in the future. 
4.	Data preprocessing:
a.	Filter Data: Remove purchases with 0 value and return orders.
b.	Handle missing values.
c.	Handle Outliers: Anything outside range of 5-95 Percentile will be removed. 
5.	Data Preparation: Create RFM Dataset i.e., Recency, Frequency, T and Monetary dataset.
a.	Frequency = total purchases minus one; or count of time periods with purchases (using days as units).
b.	 Recency = duration between first and latest purchase (if only one purchase, recency is 0).
c.	T = duration between first purchase and end of period under study (weekly in the dataset). 
d.	Monetary Value = sum of customer's purchases divided by total number of purchases; denominator is different from frequency.
6.	Model Implementation: 
a.	BG/NBD: BetaGeoFitter, we will implement BG/NBD model to our new data frame and be able to predict the number of purchases for each customer for next 6 months.
 
b.	Gamma-Gamma Model: 
i.	We will use this model to predict the monetary value of each order in next 6 months.
ii.	Assumption check: We must check that there is no correlation between frequency and monetary values.	
 
7.	Segment the customers: Based on CLV value over next 6 month we will make customer segments based on quartile cuts.

### Results and Recommendations
After segmenting our customers by CLV
Champions	>=75	6.01	$3,096	$18,607
Loyal Customers	50-75	3.75	$1,235	$4,630
Need Attention	25-50	2.99	$746	$2,229
Hibernating 	>= 25 Percentile	2.55	$365	$930

Recommendations 
Offer specific products to each segment
Create a marketing plan to increase CLV for lower segment
Try to focus on the higher segments in order to decrease customer acquisition costs.
