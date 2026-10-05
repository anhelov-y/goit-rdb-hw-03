# Домашня робота №3

## Завдання 1. Виведення всіх даних з таблиць `products` та `shippers` (p1_Anhelov.png і p1_2_Anhelov.png).

```sql
USE mydb;

SELECT \* FROM products;

SELECT name, phone FROM shippers;
```

## Завдання 2. Пошук середнього, максимального та мінімального значення ціни (p2_Anhelov.png).

```sql
USE mydb;

SELECT
AVG(price) AS average_price,
MAX(price) AS max_price,
MIN(price) AS min_price
FROM products;
```

## Завдання 3. Вибірка унікальних значень `category_id` та `price` зі сортуванням та лімітом (p3_Anhelov.png).

```sql
USE mydb;

SELECT DISTINCT category_id, price
FROM products
ORDER BY price DESC
LIMIT 10;
```

## Завдання 4. Підрахунок кількості продуктів у ціновому діапазоні від 20 до 100 (p4_Anhelov.png).

```sql
USE mydb;

SELECT COUNT(\*) AS product_count
FROM products
WHERE price BETWEEN 20 AND 100;
```

## Завдання 5. Кількість продуктів та середня ціна у кожного постачальника (p5_Anhelov.png).

```sql
USE mydb;

SELECT
supplier_id,
COUNT(\*) AS product_count,
AVG(price) AS average_price
FROM products
GROUP BY supplier_id;
```
