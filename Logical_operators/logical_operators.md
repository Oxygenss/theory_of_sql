## Логические операторы 

- `AND`: Используется для соединения двух или более условий. Запрос вернет строки, которые удовлетворяют всем условиям.

``` sql
SELECT * FROM person WHERE age > 21 AND address = 'Moscow';
```

- `OR`: Используется для соединения двух или более условий. Запрос вернет строки, которые удовлетворяют хотя бы одному из условий.

``` sql
SELECT * FROM person WHERE age > 21 OR address = 'Moscow';
```

- `NOT`: Используется для инвертирования условия. Запрос вернет строки, которые не удовлетворяют условию.

``` sql
SELECT * FROM person WHERE NOT address = 'Moscow';
```

- `BETWEEN` или `<=>`: Используется для выбора значений в диапазоне. Запрос вернет строки, где значение столбца находится в указанном диапазоне.

``` sql
SELECT * FROM person WHERE age BETWEEN 21 AND 27;
SELECT * FROM person WHERE age >= 21 AND rating <= 27 ;
```

- `IN`: Используется для проверки, содержится ли значение столбца в списке значений.

``` sql
-- Пример 1
SELECT * FROM person WHERE address IN ('Moscow', 'Kazan');

-- Пример 2
SELECT * FROM person WHERE age IN (16, 33);

-- Пример 3
SELECT * FROM orders
WHERE order_id IN (SELECT order_id FROM order_details WHERE quantity > 5);
```

- `EXISTS` используется для проверки наличия строк, удовлетворяющих определенному условию, в подзапросе. Он возвращает TRUE или FALSE, в зависимости от того, есть ли хотя бы одна строка, удовлетворяющая условию. EXISTS часто используется в условиях WHERE для фильтрации записей.

``` sql
-- "1" - Это номер столбца
SELECT * FROM orders
WHERE EXISTS (SELECT 1 FROM order_details WHERE order_details.order_id = orders.order_id);
```

- `LIKE`: Используется для поиска по шаблону. Может использоваться с символами подстановки % (для любого количества символов) и _ (для одного символа).

``` sql
SELECT * FROM person WHERE first_name LIKE 'J%';
```
