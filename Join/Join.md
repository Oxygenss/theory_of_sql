## JOIN 

`JOIN` используется для объединения строк из двух или более таблиц на основе связанного между ними поля.

`Типы объединений:`

- `INNER JOIN (Внутреннее объединение):` Возвращает строки, когда есть хотя бы одно совпадение в обеих таблицах. 

``` sql
-- Пример внутреннего соединения
SELECT orders.order_id, customers.customer_name
FROM orders INNER JOIN customers ON orders.customer_id = customers.customer_id;
```

- `LEFT OUTER JOIN (Левое внешнее объединение):` Возвращает все строки из левой таблицы и совпадающие строки из правой таблицы. Если нет совпадений, результатом является NULL с правой стороны.

``` sql
-- Пример левого внешнего объединения
SELECT orders.order_id, customers.customer_name
FROM orders LEFT JOIN customers ON orders.customer_id = customers.customer_id;
```

- `RIGHT OUTER JOIN (Правое внешнее объединение):` Возвращает все строки из правой таблицы и совпадающие строки из левой таблицы. Если нет совпадений, результатом является NULL с левой стороны.

``` sql
-- Пример правого внешнего объединения
SELECT orders.order_id, customers.customer_name
FROM orders RIGHT JOIN customers ON orders.customer_id = customers.customer_id;
```

`Левое и правое внешнее объединение можно переделать друг в друга, просто поменяв местами таблицы`

- `FULL OUTER JOIN (Полное внешнее объединение):` Возвращает строки, когда есть совпадение в одной из таблиц. Если нет совпадений, результатом является NULL с обеих сторон.

``` sql
-- Пример полного внешнего объединения
SELECT orders.order_id, customers.customer_name
FROM orders FULL OUTER JOIN customers ON orders.customer_id = customers.customer_id;
```

- `CROSS JOIN (Перекрестное объединение):` Возвращает декартово произведение (все возможные комбинации) строк из обеих таблиц. Это означает, что каждая строка из первой таблицы соединяется с каждой строкой из второй таблицы.

``` sql
-- Пример перекрестного объединения
SELECT orders.order_id, customers.customer_name
FROM orders CROSS JOIN customers;
```

- `NATURAL JOIN:` Автоматически сопоставляет столбцы с одинаковыми именами в обеих таблицах и выполняет внутреннее соединение `INNER JOIN` на этих столбцах. Это означает, что в результирующем наборе данных будут только те строки, для которых существуют совпадающие значения в обоих таблицах.

``` sql
-- Пример NATURAL JOIN
SELECT * FROM orders
NATURAL JOIN order_details;
```