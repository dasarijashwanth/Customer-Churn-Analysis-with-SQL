# Customer-Churn-Analysis-with-SQL

## 📌 Project Overview
This project analyzes customer churn using SQL and a CSV dataset. The goal is to understand why customers leave and provide actionable insights to improve retention.

## 📂 Dataset
**File Name:** `customer_churn.csv`

### 🔍 Columns in the Dataset:
- `customer_id` - Unique customer identifier
- `name` - Customer name
- `age` - Customer's age
- `gender` - Customer's gender
- `location` - Customer's city
- `subscription_type` - Type of subscription (Basic, Premium, Enterprise)
- `monthly_spending` - Monthly subscription fee ($)
- `total_spending` - Total amount spent by the customer ($)
- `last_login` - Last login date
- `churn` - 1 (Churned), 0 (Active)

## 🎯 Business Problems & Solutions

### **1️⃣ Identify High-Risk Churn Customers**
**Problem:** Which customers are most likely to churn?
**SQL Query:**
```sql
SELECT customer_id, name, subscription_type, monthly_spending, total_spending
FROM customer_churn
WHERE churn = 1;
```
**Solution:**
- Offer personalized retention plans to high-risk customers.
- Provide discounts or loyalty programs.

### **2️⃣ Subscription Type vs. Churn Rate**
**Problem:** Which subscription type has the highest churn rate?
**SQL Query:**
```sql
SELECT subscription_type, COUNT(*) AS churned_customers
FROM customer_churn
WHERE churn = 1
GROUP BY subscription_type
ORDER BY churned_customers DESC;
```
**Solution:**
- Improve features or benefits for the high-churn subscription type.
- Adjust pricing or provide flexible plans.

### **3️⃣ Monthly Spending vs. Churn**
**Problem:** Is there a pattern between spending and churn?
**SQL Query:**
```sql
SELECT subscription_type, AVG(monthly_spending) AS avg_spending, COUNT(*) AS churned_customers
FROM customer_churn
WHERE churn = 1
GROUP BY subscription_type;
```
**Solution:**
- Analyze why high-paying customers are leaving.
- Provide better customer service or exclusive benefits.

### **4️⃣ Customer Engagement (Last Login Analysis)**
**Problem:** Do inactive users have a higher churn rate?
**SQL Query:**
```sql
SELECT COUNT(*) AS inactive_churned_customers
FROM customer_churn
WHERE churn = 1 AND last_login < '2023-12-01';
```
**Solution:**
- Implement engagement campaigns for inactive users.
- Send personalized emails or offers to re-engage customers.

## 🚀 How to Use
1. Download the `customer_churn.csv` file.
2. Load it into an SQL database.
3. Run the provided SQL queries to analyze churn patterns.

## 📌 Technologies Used
- **Database:** PostgreSQL / MySQL
- **Data Analysis:** SQL queries
- **Dataset Format:** CSV

## 🔥 Future Enhancements
- Use **machine learning** to predict churn probability.
- Implement **dashboard visualizations** using Tableau/Power BI.
- Analyze **demographic factors** influencing churn.

## 📩 Contact
For any queries, reach out via GitHub or LinkedIn!

---
📢 **Star ⭐ this repository if you found it helpful!**

