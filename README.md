# 4h-w

CREATE TABLE products
(
    id SERIAL PRIMARY KEY,
    productName VARCHAR(30) NOT NULL,
    company VARCHAR(20) NOT NULL,
    productCount INT DEFAULT 0,
    price NUMERIC NOT NULL,
    isDiscounted BOOL
);

INSERT INTO products (productName, company, productCount, price, isDiscounted)
VALUES ('iPhone X', 'Apple', 3, 76000, false),
       ('iPhone 8', 'Apple', 2, 71000, true),
       ('iPhone 7', 'Apple', 5, 42000, true),
       ('Galaxy S9', 'Samsung', 2, 46000, false),
       ('Galaxy S8 Plus', 'Samsung', 1, 56000, true),
       ('Desire 12', 'HTC', 5, 28000, true),
       ('Nokia 9', 'HMD Global', 6, 38000, true);

---------- 1 ----------
select productName from products
except  select productName from products where company= 'HTC';

select productName from products where company='Apple' AND price<75000;

select productName from products where price>=46000;

SELECT productName
FROM products  order by price desc limit 2

SELECT MIN(price) AS smallestPrice
FROM products;


select productName from products
where isDiscounted='true';

select productName from products
where isDiscounted='false';

select price from products order by price desc ;

SELECT SUM(price)
FROM products;


SELECT company from products
group by company having count(productName)<=2 ;



