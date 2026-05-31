# 🛒 Flipkart E-Commerce Analytics Dashboard

## SQL + Python + Power BI

## 📌 Overview

This project analyzes a Flipkart-style e-commerce dataset to uncover business insights related to sales performance, product demand, pricing, discounts, customer ratings, delivery efficiency, return policies, seller performance, and brand/category performance.

The project was first analyzed using **SQL in Jupyter Notebook** with **Python pandas**, and later converted into an interactive **Power BI dashboard**.

---

## 🧰 Tools Used

* SQL
* Python
* Jupyter Notebook
* pandas
* SQLAlchemy
* Power BI
* Excel

---

## 🗂️ Database Schema

The project uses the following relational tables:

* **products** → product name, category, brand, color, size, weight, warranty
* **orders** → order ID, product ID, seller, price, discount, final price, units sold, stock, listing date
* **reviews** → rating, review count, product score
* **logistics** → delivery days and shipping weight
* **returns** → return policy days and returnable status
* **sellers** → seller name, seller city, seller rating
* **payments** → available payment modes

---

## 📊 Power BI Dashboard Pages

### 1. Executive Overview

This page gives a high-level view of business performance.

Key metrics and visuals:

* Total Revenue
* Total Units Sold
* Average Rating
* Average Discount
* Total Products
* Total Sellers
* Top 5 Categories by Revenue
* Monthly Revenue Trend
* Payment Method Distribution
* Top 5 Products by Revenue

---

### 2. Product & Customer Analytics

This page focuses on product performance, customer response, and discount behavior.

Key metrics and visuals:

* Average Product Price
* Average Product Score
* Average Review Count
* Average Rating
* Revenue Contribution by Brand
* Revenue by Discount Range
* Top Performing Products Table

---

### 3. Operations & Seller Analytics

This page analyzes operational efficiency, delivery performance, seller contribution, and return policies.

Key metrics and visuals:

* Average Seller Rating
* Average Delivery Days
* Returnable Products %
* Average Return Policy Days
* Top Sellers by Revenue
* Average Delivery Days by Category
* Returnable vs Non-Returnable Products
* Return Policy Days by Category

---

## 🖼️ Dashboard Screenshots

### Executive Overview
<img width="1314" height="760" alt="flipkart_dashboard1" src="https://github.com/user-attachments/assets/0f6d3e34-5012-452d-8aed-3403ff3b4e34" />
<img width="1437" height="829" alt="flipkart_dashboard2 1" src="https://github.com/user-attachments/assets/6ff45480-2e7b-40d3-9dce-6b69b27db8c6" />

### Product & Customer Analytics

<img width="1422" height="822" alt="flipkart_dashboard2" src="https://github.com/user-attachments/assets/6de53c07-8d47-421f-9762-b6b995692985" />

### Operations & Seller Analytics

<img width="1418" height="817" alt="flipkart_dashboard3" src="https://github.com/user-attachments/assets/603b1641-4e1f-424a-b9b4-e5be4864f368" />

---

## 🔍 Key Business Questions Answered

### 📈 Revenue & Sales

* Which categories generate the highest revenue?
* Which products contribute most to revenue?
* How does revenue change month by month?
* Which sellers generate the highest sales?

### 💸 Pricing & Discounts

* Which discount ranges contribute the most revenue?
* Are higher discounts always linked with higher revenue?
* Which products perform well despite lower discounting?

### ⭐ Customer Behaviour

* Which products have the highest review counts?
* How do product ratings compare across top products?
* Which brands perform strongly in terms of revenue?

### 🚚 Logistics & Delivery

* Which categories have higher average delivery days?
* What is the overall average delivery time?
* Which categories may need logistics improvement?

### 🔁 Returns & Policies

* What percentage of products are returnable?
* Which categories have longer return policy periods?
* How do return policies vary by category?

### 🏷️ Seller Performance

* Which sellers generate the most revenue?
* What is the average seller rating?
* How do sellers contribute to marketplace performance?

---

## 🧠 Key Learnings

* Built a relational data model using multiple tables instead of one flat dataset.
* Used SQL for exploratory data analysis and business question solving.
* Used Power BI relationships to connect products, orders, reviews, returns, logistics, sellers, and payments.
* Created DAX measures for revenue, units sold, average rating, returnable percentage, average delivery days, and seller rating.
* Designed a 3-page professional dashboard with navigation buttons and business-focused visuals.
* Learned that clear business storytelling is more important than adding too many charts.

---

## 📌 Important DAX Measures

```DAX
Total Revenue =
SUMX(
    orders,
    orders[final_price] * orders[units_sold]
)
```

```DAX
Total Units Sold =
SUM(orders[units_sold])
```

```DAX
Average Rating =
AVERAGE(reviews[rating])
```

```DAX
Returnable Products % =
DIVIDE(
    CALCULATE(
        COUNTROWS(returns),
        returns[is_returnable] = TRUE()
    ),
    COUNTROWS(returns)
)
```

```DAX
Avg Delivery Days =
AVERAGE(logistics[delivery_days])
```

---

## 🚀 Future Improvements

* Add customer-level data for segmentation and retention analysis.
* Add profit and cost fields for margin analysis.
* Build product recommendation analysis.
* Add forecasting for future revenue and demand.
* Improve seller analysis using seller IDs and historical seller performance tracking.
* Deploy dashboard using Power BI Service.

---

## ✅ Conclusion

This project demonstrates end-to-end data analytics workflow: data modeling, SQL-based analysis, Python support, and Power BI dashboard development. The dashboard helps understand revenue performance, product trends, customer response, delivery efficiency, return policies, and seller contribution in an e-commerce business context.
