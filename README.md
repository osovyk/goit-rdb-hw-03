# Домашнє завдання до Теми 3. Завантаження даних та основи SQL. DQL команди

## 1. Напишіть SQL команду, за допомогою якої можна:
* вибрати всі стовпчики (За допомогою wildcard “*”) з таблиці products;
* вибрати тільки стовпчики name, phone з таблиці shippers,
* та перевірте правильність її виконання в MySQL Workbench.
```
SELECT * FROM hw3.products;
SELECT name, phone FROM hw3.shippers;
```

## 2. Напишіть SQL команду, за допомогою якої можна знайти середнє, максимальне та мінімальне значення стовпчика price таблички products, та перевірте правильність її виконання в MySQL Workbench*.*
```
SELECT AVG(price) as AVG, MAX(price) as MAX, MIN(price) as MIN FROM hw3.products;
```

## 3. Напишіть SQL команду, за допомогою якої можна обрати унікальні значення колонок category_id та price таблиці products. Оберіть порядок виведення на екран за спаданням значення price та виберіть тільки 10 рядків. Перевірте правильність виконання команди в MySQL Workbench.
```
SELECT DISTINCT category_id, price
FROM hw3.products
ORDER BY price DESC
LIMIT 10;
```

## 4. Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків), які знаходиться в цінових межах від 20 до 100, та перевірте правильність її виконання в MySQL Workbench.
```
SELECT COUNT(*) AS product_count
FROM hw3.products
WHERE price BETWEEN 20 AND 100;
```

## 5. Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків) та середню ціну (price) у кожного постачальника (supplier_id), та перевірте правильність її виконання в MySQL Workbench.
```
SELECT  supplier_id, COUNT(*) AS product_count, AVG(price) AS avg_price
FROM hw3.products
GROUP BY supplier_id;
```
