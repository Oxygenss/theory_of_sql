## CONCAT && AS

Функция `CONCAT` в SQL используется для объединения двух или более строк в одну. Она принимает два или более аргумента и возвращает результат их объединения.

Ключевое слово `AS` в SQL используется для переименования столбцов или таблиц в результате запроса.

``` sql
-- Столбец будет называться person_information
SELECT CONCAT(first_name, ' (last_name:', last_name, ',age:', age, ')') AS person_information 
FROM person;
```

## Coalesce


## CAST
CAST (price - price * 0.1 AS INTEGER) AS discount_price

(m.price - m.price * 0.1) :: int AS discount_price