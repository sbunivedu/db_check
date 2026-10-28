# SQLite Check

This example demonstrates the use of CHECK Constraints on the following database:

* contacts(contact_id, first_name, last_name, email, phone)
* products(product_id, product_name, list_price, discount)

Sample data can be found in the [script file](script.txt), which can be run on https://sqliteonline.com/ for experimentation.

* Attribute-based checks
```sql
INSERT INTO contacts(first_name, last_name, phone)
VALUES('John','Doe','408123456');

INSERT INTO contacts(first_name, last_name, phone)
VALUES('John','Doe','(408)-123-456');
```

* Tuple-base checks
```sql
INSERT INTO products(product_name, list_price, discount)
VALUES('New Product',900,1000);

INSERT INTO products(product_name, list_price, discount)
VALUES('New XFactor',1000,10);   

UPDATE products
SET discount = -10
WHERE product_name = 'New XFactor';
```

source: https://www.sqlitetutorial.net/sqlite-check-constraint/
