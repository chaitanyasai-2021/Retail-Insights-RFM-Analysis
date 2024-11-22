# 🛍️ Customer Segmentation for Retail Sales using RFM Analysis  

This repository demonstrates a comprehensive project focused on analyzing retail sales data to gain actionable insights using **RFM (Recency, Frequency, Monetary)** analysis. By leveraging **SQL** for data segmentation and **Tableau** for visualization, the project explores customer purchase patterns, designs interactive dashboards, and proposes data-driven strategies to boost sales and customer retention.  

---

## 📖 **Project Overview**  

This project focuses on segmenting retail customers and analyzing their purchase behaviors using **RFM Analysis**. Key objectives include:  
- Understanding customer purchasing habits.  
- Creating dynamic dashboards to visualize insights.  
- Proposing actionable strategies to enhance sales and retention.  

---

## 🛠️ **Techniques and Tools**  

### ✅ **RFM Analysis**  
Segmented customers into meaningful categories using **Recency, Frequency, and Monetary** metrics.  

### ✅ **SQL**  
- Querying and analyzing large datasets for customer segmentation.  
- Advanced queries for extracting business insights.  

### ✅ **Tableau**  
Designed interactive dashboards to visualize customer behavior and sales trends.  

---

## 📊 **RFM Analysis**  

RFM analysis evaluates customer value by analyzing:  
- **Recency (R)**: Time since the last purchase.  
- **Frequency (F)**: Number of purchases made by the customer.  
- **Monetary (M)**: Total amount spent by the customer.  

### 📝 **SQL Query Examples**  

#### 🎯 **RFM Segmentation Query**  
This query segments customers into categories like "Loyal," "Potential Churners," and more.  
```sql
SELECT CUSTOMERNAME, rfm_recency, rfm_frequency, rfm_monetary, 
       CASE
           WHEN rfm_cell_string IN (111, 112, 121, 122) THEN 'Lost Customer'
           WHEN rfm_cell_string IN (133, 143, 244) THEN 'Slipping Away'
           WHEN rfm_cell_string IN (311, 421) THEN 'New Customer'
           WHEN rfm_cell_string IN (222, 322) THEN 'Potential Churners'
           WHEN rfm_cell_string IN (333, 432) THEN 'Active'
           WHEN rfm_cell_string IN (433, 444) THEN 'Loyal'
       END AS Segment
FROM #rfm;
```  

#### 📍 **Top Countries by Revenue**  
This query identifies the most profitable regions based on sales data.  
```sql
SELECT COUNTRY, SUM(SALES) AS Revenue
FROM sales_data_sample
GROUP BY COUNTRY
ORDER BY Revenue DESC;
```  

#### 🧑‍🤝‍🧑 **Customer Purchases by Month**  
This query tracks customer purchase trends over time.  
```sql
WITH MonthlyPurchases AS (
    SELECT CUSTOMERNAME, DATEPART(MONTH, PURCHASE_DATE) AS Month, SUM(SALES) AS TotalSpent
    FROM sales_data
    GROUP BY CUSTOMERNAME, DATEPART(MONTH, PURCHASE_DATE)
)
SELECT Month, AVG(TotalSpent) AS AvgMonthlySpent
FROM MonthlyPurchases
GROUP BY Month
ORDER BY Month;
```  

---

## 📈 **Dashboards**  

Using **Tableau**, I created dynamic dashboards to visualize and analyze sales data:  

1. **Customer Segmentation Dashboard**: Visualized customer segments like *Loyal Customers*, *Lost Customers*, and *Potential Churners*.  
2. **Product Analysis Dashboard**: Showcased high-performing products, sales trends, and seasonal insights.  
3. **Geographical Dashboard**: Highlighted top-performing regions for targeted marketing campaigns.  

---

## 💡 **Business Solutions**  

### 🔍 **Customer Categories**  

1. **Lost Customers** 🕳️  
   - Understand reasons for disengagement.  
   - Offer tailored promotions to re-engage them.  

2. **Slipping Away (Big Spenders)** 💸  
   - Provide loyalty rewards and exclusive discounts.  
   - Simplify purchasing with flexible payment options.  

3. **New Customers** 🌱  
   - Introduce welcome offers and reward programs.  
   - Enhance their first purchase experience.  

4. **Potential Churners** ⚠️  
   - Send targeted discounts and personalized offers.  
   - Engage through customer feedback initiatives.  

5. **Active Customers** 🔄  
   - Incentivize bulk purchases with discounts.  

6. **Loyal Customers** 💖  
   - Offer VIP benefits like priority support and exclusive products.  

### 🛒 **Products Sold Together**  
- Introduce combo offers for frequently purchased items.  
- Use AI to recommend complementary products.  

---

## 🚀 **Benefits to Business**  

1. **Improved Customer Retention**: Enhanced loyalty programs tailored to customer segments.  
2. **Optimized Sales Strategies**: Personalized marketing campaigns for different groups.  
3. **Increased Revenue**: Insights from product bundling and seasonal sales trends.  

---

## 📂 **Repository Structure**  

- **`/SQL`**: Contains all SQL scripts used for analysis and segmentation.  
- **`/Dashboards`**: Tableau files showcasing interactive dashboards.  
- **`/Docs`**: Documentation on business strategies, methodologies, and insights.  
- **`README.md`**: Project overview  

---


4. Implement the strategies outlined in this project for actionable insights.  

---

**Happy Analyzing! 🎉**  

For further details or questions, feel free to explore the code or reach out. 🚀
