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
SELECT * FROM person WHERE address IN ('Moscow', 'Kazan');
SELECT * FROM person WHERE age IN (16, 33);
```

- `LIKE`: Используется для поиска по шаблону. Может использоваться с символами подстановки % (для любого количества символов) и _ (для одного символа).

``` sql
SELECT * FROM person WHERE first_name LIKE 'J%';
```
