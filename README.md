# RYStore Fictional Supermarket Dataset

This is a fully fictional relational retail dataset for learning SQL, Python, PySpark, Power BI/Tableau, data warehousing, dashboards, and machine learning.

## Tables and approximate use

- stores.csv: 8 RYStore branches across UK cities.
- suppliers.csv: 12 fictional suppliers.
- products.csv: 66 supermarket products with category, brand, supplier, cost, price, VAT, and reorder level.
- customers.csv: 800 loyalty customers. Blank customer_id in orders represents anonymous/non-loyalty purchases.
- employees.csv: 120 fictional employees linked to stores.
- promotions.csv: 6 category-level promotional campaigns.
- orders.csv: 10000 orders from 2025 with channel, payment method, status, subtotal, VAT, delivery fee, and total.
- order_items.csv: 47512 item-level transaction lines linked to orders and products.
- inventory.csv: 528 store-product stock snapshot rows.

## Suggested relationships

- orders.store_id -> stores.store_id
- orders.customer_id -> customers.customer_id, nullable for anonymous purchases
- order_items.order_id -> orders.order_id
- order_items.product_id -> products.product_id
- order_items.promotion_id -> promotions.promotion_id, nullable when no promotion applied
- products.supplier_id -> suppliers.supplier_id
- inventory.store_id -> stores.store_id
- inventory.product_id -> products.product_id
- employees.store_id -> stores.store_id

## Useful analysis ideas

1. Monthly revenue, order count, and average basket value.
2. Top products and categories by revenue, quantity, and gross margin.
3. Online vs in-store performance.
4. Loyalty tier spending and customer segmentation.
5. Promotion uplift and discount impact.
6. Store-level inventory risk by comparing stock_on_hand with reorder_level.
7. Supplier/category profitability.
8. Basket analysis using order_items.
9. Demand forecasting using daily sales by product/category/store.
10. Build a star schema with orders/order_items as facts and products, stores, customers, date, suppliers as dimensions.

## Notes

All names, addresses, emails, stores, suppliers, and transactions are fictional. Any resemblance to real people or businesses is coincidental.
