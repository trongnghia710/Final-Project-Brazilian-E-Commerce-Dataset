# Final-Project-Brazilian-E-Commerce-Dataset
https://colab.research.google.com/drive/1GEi4T5MCQ-mhDQkzAw1uk_l4mhzJ2I6k?authuser=3#scrollTo=GgjalnUs-Qiv (Google Collab)

https://drive.google.com/drive/folders/1nwfoZnxOfPebME5adHh-faVi8wSrYm4H?usp=sharing (POWERBI FINAL PROJECT FILE)
## 1. Project Overview
*This project analyzes the Brazilian Olist E-commerce Dataset using Python (ETL) and Power BI to build an interactive dashboard and uncover business insights about sales, payments, customer behaviors, product performance, shipping efficiency, and customer satisfaction.*
### Main Goals
- Conduct ETL
- Build a Star Schema data model
- Create measures using DAX
- Build Sales Overview Dashboard
- Build Order & Shipping Performance Dashboard
- Build Customer Insights Dashboard
- Build Product Performance Dashboard
### Tool used
- Power BI
- Google Colab / Python
- Pandas / NumPy
- GitHub
## 2. Dataset
The Olist Brazilian E-commerce Public Dataset consists of multiple tables:
- orders.csv
- customers.csv
- order_items.csv
- products.csv
- payments.csv
- sellers.csv
- reviews.csv
- category_translation.csv
Total: 100k+ orders, 9 relational tables, 2016–2018.
## 3. Business Questions
## 4. ETL Process (Python – Google Colab)
https://colab.research.google.com/drive/1GEi4T5MCQ-mhDQkzAw1uk_l4mhzJ2I6k?usp=sharing
### 4.1 Extract
Loaded 9 CSVs from the Olist dataset.
### 4.2 Transform
**Performed data cleaning:**
- Converted datetime columns
- Removed duplicates
- Standardized category translations
- Joined tables using primary keys:
- order_id
- customer_id
- seller_id
- product_id

**Created fact tables and dimension tables:**

**Fact Tables:**
- fact_orderitems
- fact_payment
- fact_reviews

**Dimension Tables:**
- dim_customers
- dim_orders
- dim_products
- dim_sellers
- dim_payment_type
- dim_date
### 4.3 Load
All cleaned CSV files were exported and imported into Power BI to create a Star Schema model.

## 5. Data Modeling (Star Schema)
**Star-schema gồm:**
Fact Tables:
- fact_orders
- fact_orderitems
- fact_payment
- fact_reviews

**Dimension Tables:**
- dim_customers
- dim_sellers
- dim_products
- dim_payment_type
- dim_date

**Relationships**
1. fact_orderitems (customer_id) → dim_customers (customer_id)
Cardinality: Many-to-One ( * → 1 ) — Active

2. fact_orderitems (order_id) → dim_orders (order_id)
Cardinality: Many-to-One ( * → 1 ) — Active

3. fact_orderitems (OrderDate) → dim_date (Date)
Cardinality: Many-to-One ( * → 1 ) — Active

4. fact_orderitems (product_id) → dim_products (product_id)
Cardinality: Many-to-One ( * → 1 ) — Active

5. fact_orderitems (seller_id) → dim_sellers (seller_id)
Cardinality: Many-to-One ( * → 1 ) — Active

6. fact_payment (order_id) → dim_orders (order_id)
Cardinality: Many-to-One ( * → 1 ) — Active

7. fact_payment (payment_type) → dim_payment_type (payment_type)
Cardinality: Many-to-One ( * → 1 ) — Active

