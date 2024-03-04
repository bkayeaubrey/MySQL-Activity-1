# MySQL-Activity-1

Submitted by:
  Kaye Aubrey Bolotano
  Frichie Ann Ortiz
Subject: 
  ITBAN 2

1.1.SELECT name, description FROM products;
![SELECT1](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/a353a8c1-ff91-42ba-9443-bd37740c5cea)

1.2.SELECT name, description, JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size, JSON_EXTRACT(attributes,'$.prize') AS prize FROM products;
![Screenshot (401)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/7cf600c8-ebee-449e-a455-a0215b236e2a)

2.1.SELECT o.order_date, o.customer_id, p.name AS product_name, od.quantity, od.price FROM orders o JOIN order_details od ON o.order_id = od.order_id JOIN products p ON od.product_id = p.product_id;
![Screenshot (402)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/6031e129-345d-47e0-a5c1-27fb86c34d93)

2.2.SELECT o.order_id, SUM(od.quantity * od.price) AS total_cost FROM orders o JOIN order_details od ON o.order_id = od.order_id GROUP BY o.order_id;
![Screenshot (403)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/7970e6fc-d35a-4264-a6bc-549484520e71)

3.1.SELECT * FROM products WHERE JSON_EXTRACT(attributes,'$.price') > 50;
![Screenshot (404)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/c18db233-91c2-4ce3-8f0a-2d936e9b94b4)

3.2.SELECT name, JSON_EXTRACT(attributes,'$.price') AS price FROM products JSON_EXTRACT(attributes,'$.color') = 'Hotpink' AND JSON_EXTRACT(attributes,'$.brand') = 'Holt Group';
![Screenshot (405)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/395d228e-dcad-44ba-998f-d8118913de7f)

4.1.SELECT p.name, SUM(od.quantity * od.price) AS total_revenue FROM products p JOIN order_details od ON p.product_id = od.product_id GROUP BY p.name;
![Screenshot (406)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/e479133c-c9fc-443d-91a8-313d8fbf3769)

4.2.SELECT p.name, SUM(od.quantity) AS total_quantity_ordered FROM products p JOIN order_details od ON p.product_id = od.product_id GROUP BY p.name;
![Screenshot (407)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/d79860f1-dd04-46d4-b1e2-ee045eb84049)

5.1.SELECT p.name, SUM(od.quantity) AS total_quantity_sold FROM products p JOIN order_details od ON p.product_id = od.product_id GROUP BY p.name ORDER BY total_quantity_sold DESC LIMIT 5;
![Screenshot (408)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/f9584d2f-2038-4bbc-acf9-e3420be97e9f)

5.2.SELECT AVG(CAST(JSON_EXTRACT(attributes,'$.prize') AS DECIMAL)) AS avg_price FROM products WHERE JSON_EXTRACT(attributes,'$.brand') = 'Meyer Inc';
![Screenshot (409)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/44ffdaf8-5d58-4661-9335-e742df0aad77)

6.1.SELECT JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size FROM products WHERE product_id = 1;
![Screenshot (410)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/ddf12512-2d01-4140-b025-9cb5853a82b8)

6.2.SELECT JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size, JSON_EXTRACT(attributes,'$.prize') AS prize, JSON_EXTRACT(attributes,'$.brand') AS brand FROM products;
![Screenshot (411)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/a1f5d9a1-68b2-404d-a0b5-3f2bcca86c99)

7.1.SELECT o.order_id, o.order_date, o.customer_id, p.name AS product_name, od.quantity FROM orders o JOIN order_details od ON o.order_id = od.order_id JOIN products p ON od.product_id = p.product_id;
![Screenshot (412)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/e7bfab43-d0ed-4f1c-beff-2c060f395985)

7.2.SELECT o.customer_id, SUM(od.quantity * od.price) AS total_revenue FROM orders o JOIN order_details od ON o.order_id = od.order_id GROUP BY o.customer_id;
![Screenshot (413)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/ddb1c67c-2de9-466d-be40-edba4f7f3ffc)

8.1.UPDATE products SET attributes = JSON_SET(attributes, '$.price', '61') WHERE product_id = 1;
![Screenshot (414)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/cf0567d3-3d92-4f9d-ac2b-220a7c79e676)
![Screenshot (415)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/bbc882e1-dbd3-4453-b38a-808cf41eebdc)

8.2.UPDATE products SET attributes = JSON_SET(attributes, '$.bagong_COlumn ', 'mao_NANI');
![Screenshot (416)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/25db6349-e07c-4897-85d2-a9c556af9e81)

9.1.SELECT * FROM products WHERE JSON_CONTAINS_PATH(attributes, 'one', '$.color') = 1;
![Screenshot (417)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/89623816-7fe2-44bd-8e4f-247aeefcc13c)

9.2. SELECT JSON_EXTRACT(attributes, '$.color[0]') AS first_feature FROM products;
![Screenshot (418)](https://github.com/bkayeaubrey/MySQL-Activity-1/assets/125627955/bd44395e-394f-4744-9b05-53aae08a06b4)






