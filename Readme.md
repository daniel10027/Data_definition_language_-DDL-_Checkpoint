# 🧾 Relational Model – SQL Implementation

This README describes the SQL script to create a relational model based on the provided diagrams and apply additional modifications using `ALTER TABLE`.

---

## 📘 Relational Model Reference

- 🔗 Relational model diagram: [View Model](https://i.imgur.com/aZeHhHe.png)
- 🗂️ Data types and structure: [View Data Types](https://i.imgur.com/vx1xFvS.png)

---

## 🧱 Table Creation in SQL

### 1️⃣ `CUSTOMER` Table

```sql
CREATE TABLE CUSTOMER (
    Cust_id NUMBER PRIMARY KEY,
    Cust_name VARCHAR2(20),
    Cust_address VARCHAR2(30)
);
```

---

### 2️⃣ `PRODUCT` Table

```sql
CREATE TABLE PRODUCT (
    Product_id NUMBER PRIMARY KEY,
    Product_name VARCHAR2(20),
    Price NUMBER(6,2)
);
```

---

### 3️⃣ `ORDERS` Table

```sql
CREATE TABLE ORDERS (
    Order_id NUMBER PRIMARY KEY,
    Cust_id NUMBER,
    Product_id NUMBER,
    Quantity NUMBER,
    CONSTRAINT fk_orders_customer FOREIGN KEY (Cust_id) REFERENCES CUSTOMER(Cust_id),
    CONSTRAINT fk_orders_product FOREIGN KEY (Product_id) REFERENCES PRODUCT(Product_id)
);
```

---

## 🔧 Table Modification Instructions

### ✅ Add a `Category` column to the `PRODUCT` table:

```sql
ALTER TABLE PRODUCT ADD Category VARCHAR2(20);
```

---

### ✅ Add an `OrderDate` column to the `ORDERS` table with default value `SYSDATE`:

```sql
ALTER TABLE ORDERS ADD OrderDate DATE DEFAULT SYSDATE;
```

---

## ✅ Summary

- All constraints (primary keys, foreign keys) are implemented.
- Data types respect the model specifications.
- Additional columns were added correctly using `ALTER TABLE`.

> You can now use this script to initialize your database for the hotel/shop/order management system.

---
