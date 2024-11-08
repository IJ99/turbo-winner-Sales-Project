# Turbo-Winner Sales-Dashboard

### Dashboard Link :https://app.powerbi.com/view?r=eyJrIjoiZmExMmMzOTQtNzMxMS00ZGY3LWI5NDEtZGI1OTBkYWZmMDdiIiwidCI6IjM0YTkxMjU3LWU1NzctNDliNi05ZmQ3LTJmNjNmNzMzMDRhYyJ9" 

The Business Brief: Sales Analysis and Visualization 
As a data analyst that has just been employed by an e-commerce company, you were provided with this 
dataset that has six (6) tables for your analysis. The objective of the project is to analyze the sales data 
across the various tables to extract valuable insights, patterns, and opportunities for improvement while 
Visualizing the data in a clear and actionable manner. The analysis will be conducted using Power BI to 
create interactive visualizations that will help stakeholders make informed business decisions. 

## PROBLEM STATEMENT:

This Power BI dashboard enables an e-commerce company to gain a deeper understanding of sales performance and customer behavior, guiding data-driven decisions to optimize business outcomes. It visualizes insights across six key tables—sellers, orders, delivery status, reviews, products, and payment methods—revealing patterns and improvement areas. The dashboard answers critical questions such as identifying top-selling products, analyzing sales trends over time, assessing customer demographics’ impact on purchasing behavior, and evaluating seller performance by region. It also investigates delivery efficiency, showing the effect of on-time versus late deliveries on customer satisfaction and sales. Preferred payment methods are highlighted to understand their influence on purchasing frequency and order value.

Insights reveal areas to enhance, particularly around delivery timing and seller consistency across regions. Interactive Power BI visuals empower stakeholders with a clear view of product trends, demographic preferences, and logistical bottlenecks, supporting targeted strategies to improve sales, streamline delivery, and boost customer satisfaction. This project offers actionable recommendations to drive growth by aligning operations with customer expectations and market demands.

##DATA SOURCES: 

▪ sellersa_table: Information about sellers, including their IDs, zip codes, cities, and 
states. 
▪ Orders_table: Details of orders, including customer IDs, product IDs, seller IDs, 
dates, prices, quantities, and shipping information. 
▪ Delivery_status table: Status of orders, including delivery dates and estimated 
delivery dates. 
▪ Review_table: Customer reviews of products, including ratings, comments, and 
timestamps. 
▪ products_table: Information about products, including categories, names, 
descriptions, dimensions, and weight. 
▪ payment_mode table: Details of payment methods used for orders, including 
payment types and installments. 

## KEY QUESTIONS TO ANSWER:

1.  Build a proper data model for the various tables for easy and accurate analysis. 
2. Identify the top-selling products based on quantity sold and revenue generated. 
3. What is the overall sales trend over time ( month-over-month, year-over-year)? 
4. How do customer demographics (e.g., age, location) correlate with purchasing behavior? 
5. What are the top-performing sellers based on total sales, and how do their performance trends vary 
by region ( state)? 
6. How does delivery efficiency (on-time delivery vs. late delivery) impact customer satisfaction and 
sales? 
7. Which payment methods are most preferred by customers, and how do they influence the 
frequency and value of sales? 
Deliverables: 
✓ Interactive dashboards in Power BI displaying insights on the questions above. 
✓ Recommendations for improving sales performance, delivery efficiency, and customer 
satisfaction.

##VISUALS:  

  (a) Total Sales

  (b) Total No of Sellers
  
  (c) Total Quantity Ordered
  
  (d) Seller-ID Slider
  
  (e) Delivery Status
  
  (f) Total Sales by Payment Type

  (g) Top Selling Product by Sales or quantity
  
  (h) Top Sellers by Sales and State
  
  (i) Overall Sales Trend Overtime(Month on Month,Year over Year)
  

Calculated Entries were made Using the following DAX expressions and were written as ;

  ##Running Total Sales     
  Running Total Sales = CALCULATE(
    [Total sales],
    FILTER(
        ALL(DateTable), 
        DateTable[Date] <= MAX(DateTable[Date])
    )
)
##Total No of Sellers
Total No of Sellers = COUNTROWS('sellers_dataset')

##YoY Sales of Change(Year on Year)
Yoy Sales change % = DIVIDE([Total sales]-CALCULATE([Total sales], SAMEPERIODLASTYEAR(DateTable[Date])), CALCULATE([Total sales], SAMEPERIODLASTYEAR(DateTable[Date])))

##MoM Sales of Change(Month on Month)
MoM Sales Change % = DIVIDE([Total sales] - CALCULATE([Total sales],DATEADD(DateTable[Date],-1,MONTH)),CALCULATE([Total sales],DATEADD(DateTable[Date],-1,MONTH)))

##Total Sales 
Total sales = SUMX(orders_dataset,orders_dataset[price]*orders_dataset[quantity])

##Total Orders
Total Orders = COUNTROWS('orders_dataset')


    
Snap of the Model view of the project ;

![Screenshot (270)](https://github.com/user-attachments/assets/f57f771e-6eea-414d-a5a1-929a0e8210aa)

               
Power Query Editior Outlook of  the data tables being cleaned and transformed;

![Screenshot (271)](https://github.com/user-attachments/assets/f3920dd8-ba67-44af-a24d-52821d1e8db5)

Table view of the dataset with the Orders dataset Selected;    
 
![Screenshot (272)](https://github.com/user-attachments/assets/71a6ec48-e08e-4bf8-a33e-314b660eff72)

 - Step 18 : The report was then published to Power BI Service.

![Screenshot (276)](https://github.com/user-attachments/assets/42311ea7-e415-4f56-a1fb-d15d733a710a)

# Snapshot of Dashboard   

![Screenshot (274)](https://github.com/user-attachments/assets/470e7488-5779-44ae-bc6b-b3ab9fd89a1c)


# Insights:

A single page report was created on Power BI Desktop & the Following inferences can be drawn from the dashboard;

### [1] Total Sales = 26.94 Million Naira:

The dashboard shows a significant total sales volume of ₦26.94 million, which highlights the overall revenue generated by the e-commerce platform.


           thus, indicating a very high intake of Preeceds/Income
           
### [2] Number of Sellers:

 There are 3,095 active sellers contributing to this revenue. This metric indicates the diversity of seller participation on the platform, which implies a broad range of products and availability for consumers
  
  ### [3] Total Quantity Ordered:

  A high total of 111K units ordered suggests strong customer engagement and a high demand for the products offered by these sellers.
     

 ### [4] Delivery Status:

 Most orders have a delivery status marked as "delivered," with a notable volume of sales attributed to these completed orders. There is a small percentage of orders with "blank" or "canceled" statuses, which may need investigation to understand reasons for cancellation or missing data.
 
 ### Total sales by payment Type:
 
 The pie chart indicates that the majority of sales (76.8%) are made through a specific payment type (likely represented as "debit card" or similar), with smaller contributions from other payment methods like credit cards, vouchers, and boleto. This insight helps understand customer payment preferences and may suggest focusing on optimizing these popular payment options to enhance the user experience.
 
 
 ### Total Selling Products by Sale or Quantity:
 The bar chart ranks products based on total sales and quantity sold. The highest-selling product categories include "beleza_sa..." (likely beauty products), "relogios" (likely watches), "cama_me..." (bedding or furniture), and others. This view allows the company to identify product categories that drive the most revenue and sales volume, aiding in inventory and promotional decisions.

### Monthly Sales Trends (MoM by Year and Month):
The line chart shows monthly trends over several years, indicating sales fluctuations throughout the year. It reveals any seasonality in sales, which can guide strategic planning for peak sales periods and inventory management.

### Top Sellers by Sales and State: 
This bar chart visualizes the performance of sellers by total sales and regional distribution. The chart provides insight into which sellers are the highest contributors and how their sales vary across states, offering a view of geographic strengths and opportunities for targeted regional promotions.
