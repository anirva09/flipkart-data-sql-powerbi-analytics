# Flipkart E-Commerce Analytics Dashboard

A SQL, Python and Power BI-based analytics project built to analyse a Flipkart-style e-commerce business across revenue performance, product demand, customer ratings, discounts, delivery efficiency, return policies, seller performance and brand/category contribution.

---

## Project Overview

This project presents an end-to-end **Flipkart E-Commerce Analytics Dashboard** using **SQL, Python, Jupyter Notebook, pandas and Power BI**.

The project was first analysed using SQL queries inside Jupyter Notebook with Python support, and later converted into an interactive Power BI dashboard for business reporting and decision-making.

The dashboard helps understand sales performance, product behaviour, seller contribution, customer response, discount impact, delivery performance and return policy patterns.

---

## Business Problem

E-commerce platforms handle large volumes of product, seller, order, pricing, logistics and review data. Business teams need a structured view to answer questions such as:

* Which categories and products generate the highest revenue?
* Which sellers contribute most to business performance?
* How do discounts affect revenue and demand?
* Which products have strong customer ratings and reviews?
* Which categories face delivery or return policy issues?
* Which brands perform well across revenue and customer response?

This project solves the problem by creating a structured analytics workflow using SQL for analysis and Power BI for dashboard reporting.

---

## Tools Used

| Tool             | Purpose                                    |
| ---------------- | ------------------------------------------ |
| SQL              | Data querying and business analysis        |
| Python           | Data handling and workflow support         |
| Jupyter Notebook | SQL analysis environment                   |
| pandas           | Data reading and result handling           |
| SQLAlchemy       | Database connection                        |
| Power BI         | Dashboard development and visual analytics |
| Excel            | Initial data review and supporting checks  |

---

## Data Model Summary

The project uses a relational structure instead of one flat dataset.

| Table       | Purpose                                                                         |
| ----------- | ------------------------------------------------------------------------------- |
| `products`  | Stores product name, category, brand, colour, size, weight and warranty details |
| `orders`    | Stores price, discount, final price, units sold, stock and listing date         |
| `reviews`   | Stores rating, review count and product score                                   |
| `logistics` | Stores delivery days and shipping-related fields                                |
| `returns`   | Stores return policy days and returnable status                                 |
| `sellers`   | Stores seller name, city and seller rating                                      |
| `payments`  | Stores available payment modes                                                  |

This structure supports cleaner analysis across product, customer, seller, logistics and returns dimensions.

---

## Dashboard Modules

| Page | Module                          | Focus                                                                             |
| ---- | ------------------------------- | --------------------------------------------------------------------------------- |
| 1    | Executive Overview              | Overall revenue, sales, ratings, discounts and product performance                |
| 2    | Product & Customer Analytics    | Product demand, brand revenue, ratings, reviews and discount behaviour            |
| 3    | Operations & Seller Analytics   | Seller performance, delivery days, returnable products and return policy analysis |
| 4    | Navigation / Dashboard Overview | Dashboard navigation, user flow and report structure                              |

---

## Dashboard Preview

### Executive Overview
<img width="3834" height="2234" alt="flipkart_executive_overview" src="https://github.com/user-attachments/assets/2506f806-b3a4-41c3-9d30-e76a909ec7ae" />



### Product & Customer Analytics
<img width="3834" height="2234" alt="flipkart_product_customer_analytics" src="https://github.com/user-attachments/assets/e61a37ab-e751-4057-9b88-3b82caac4a1a" />


### Customer & Return Analytics
<img width="3834" height="2234" alt="flipkart_customer_return_analytics" src="https://github.com/user-attachments/assets/bcf013bc-39ac-46f9-a813-9fa6ae727506" />



### Seller & Operations Analytics
<img width="3834" height="2234" alt="flipkart_seller_operations_analytics" src="https://github.com/user-attachments/assets/2a90a6a0-d7d1-45b3-a8a4-446e2cb1a993" />




---

## Key Metrics Tracked

| Area                | Metrics                                                      |
| ------------------- | ------------------------------------------------------------ |
| Sales Performance   | Total Revenue, Total Units Sold, Monthly Revenue Trend       |
| Product Analytics   | Total Products, Top Products, Product Score, Product Demand  |
| Customer Response   | Average Rating, Review Count, Rating Distribution            |
| Pricing & Discounts | Average Discount, Revenue by Discount Range                  |
| Seller Performance  | Total Sellers, Average Seller Rating, Top Sellers by Revenue |
| Logistics           | Average Delivery Days, Delivery Days by Category             |
| Returns             | Returnable Products %, Average Return Policy Days            |
| Payments            | Payment Mode Distribution                                    |

---

## Key Business Questions Answered

### Revenue & Sales

* Which categories generate the highest revenue?
* Which products contribute most to revenue?
* How does revenue change month by month?
* Which sellers generate the highest sales?

### Pricing & Discounts

* Which discount ranges contribute the most revenue?
* Are higher discounts always linked with higher revenue?
* Which products perform well despite lower discounting?

### Customer Behaviour

* Which products have the highest review counts?
* How do ratings vary across products and brands?
* Which brands perform strongly in terms of revenue and customer response?

### Logistics & Delivery

* Which categories have higher average delivery days?
* What is the overall average delivery time?
* Which categories may need logistics improvement?

### Returns & Policies

* What percentage of products are returnable?
* Which categories have longer return policy periods?
* How do return policies vary by category?

### Seller Performance

* Which sellers generate the most revenue?
* What is the average seller rating?
* How do sellers contribute to marketplace performance?

---

## SQL Analysis Workflow

SQL was used to answer business questions before building the dashboard.

The analysis included:

* Revenue by category
* Top products by revenue
* Units sold by product and category
* Seller-wise revenue contribution
* Discount bucket analysis
* Rating and review analysis
* Delivery performance by category
* Return policy analysis
* Stock and demand gap checks

This helped validate the business logic before converting the analysis into Power BI visuals.

---

## Important DAX Measures

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
Average Delivery Days =
AVERAGE(logistics[delivery_days])
```

---

## Key Insights

* Revenue analysis helps identify the categories and products driving business performance.
* Seller-level analysis highlights which marketplace sellers contribute most to revenue.
* Discount analysis shows how pricing strategy affects revenue contribution.
* Rating and review metrics help measure customer response toward products.
* Delivery days and return policy metrics provide an operational efficiency view.
* A relational data model improves analysis quality compared with using a single flat table.

---

## Project Outputs

| Output                | Description                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------- |
| SQL Analysis          | Business queries written and tested in Jupyter Notebook                                        |
| Power BI Dashboard    | Interactive dashboard covering sales, products, customers, sellers, logistics and returns      |
| Data Model            | Relational structure using products, orders, reviews, sellers, logistics, returns and payments |
| Dashboard Screenshots | Four dashboard screenshots showing the final report pages                                      |
| Documentation         | README and project explanation for GitHub portfolio                                            |

---

## Skills Demonstrated

* SQL-based business analysis
* Python and pandas workflow support
* Jupyter Notebook analysis
* Relational data modelling
* Power BI dashboard development
* DAX measure creation
* E-commerce analytics
* Seller and product performance analysis
* Customer rating and review analysis
* Logistics and returns analysis
* Business insight communication

---

## Future Improvements

* Add customer-level data for segmentation and retention analysis.
* Add cost and profit fields for margin analysis.
* Build product recommendation analysis.
* Add revenue and demand forecasting.
* Improve seller analysis using seller IDs and historical seller performance.
* Deploy the dashboard using Power BI Service.

---

## Project Positioning

This project demonstrates an end-to-end e-commerce analytics workflow using SQL, Python and Power BI. It combines data modelling, SQL analysis, dashboard development and business interpretation to present a professional data analytics portfolio project.

---

## Author

**Anirva Manchikatla**
B.Tech CSE | Data Analytics | Business Intelligence | Power BI | SQL
