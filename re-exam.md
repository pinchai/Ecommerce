# Re-exam (E-Commerce Website)

## 1. Overview
Build a mini e-commerce website where users can browse products, add them to a cart, and place simple orders. No real payment integration is required.

---

## 2. Scenario
You are developing a mini store called **MiniShop** where:
- Users browse products.
- Users add products to a cart.
- Users checkout as guests.
- Admin manages products.


## 3. Functional Requirements

#### Public Pages
1. **Home Page**
   - Display product list with name, price, description.
   - Actions: View Detail, Add to Cart.

2. **Product Detail Page**
   - Full product info with quantity selector and Add to Cart.

3. **Cart Page**
   - List items with quantity, subtotal, total.
   - Allow update and remove.
   - Checkout button.

4. **Checkout Page**
   - Form fields:
     - Name
     - Email
     - Phone
     - Address
   - Save order to DB.

5. **Order Confirmation Page**
   - Show order ID and total.

---

### Admin Pages
6. **Admin Product List**
   - List products with ID, name, price, stock, status.
   - Add/Edit/Delete functionality.

7. **Admin Product Form**
   - Fields:
     - Name
     - Description
     - Price
     - Stock
     - Image URL
     - Status

---

## 4. Database Design

### Table: products
```sql
CREATE TABLE products (
    product_id   INT PRIMARY KEY AUTO_INCREMENT,
    name         VARCHAR(100) NOT NULL,
    description  VARCHAR(500),
    price        DECIMAL(10,2) NOT NULL,
    stock        INT NOT NULL,
    image_url    VARCHAR(255),
    status       VARCHAR(10) DEFAULT 'ACTIVE',
    created_at   TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Table: orders
```sql
CREATE TABLE orders (
    order_id         INT PRIMARY KEY AUTO_INCREMENT,
    customer_name    VARCHAR(100),
    customer_email   VARCHAR(100),
    customer_phone   VARCHAR(20),
    shipping_address VARCHAR(255),
    total_amount     DECIMAL(10,2),
    created_at       TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Table: order_items
```sql
CREATE TABLE order_items (
    order_item_id INT PRIMARY KEY AUTO_INCREMENT,
    order_id      INT,
    product_id    INT,
    quantity      INT,
    unit_price    DECIMAL(10,2),
    subtotal      DECIMAL(10,2),
    FOREIGN KEY (order_id) REFERENCES orders(order_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);
```
---

## 5. Submit
- Hosting Project.
- Github repo.
- Video demo about project  .
- Send me via telegram(private).
