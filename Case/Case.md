## Case

Для выполнения условной логики в SQL используется `CASE`

``` sql
-- Базовый синтаксис
CASE
    WHEN condition_1 THEN result_1
    WHEN condition_2 THEN result_2
    ELSE result_3
END AS pseudonym
```

``` sql
-- Пример
SELECT
	(SELECT p.name FROM person p WHERE p.id = po.person_id) AS NAME,
	CASE
		WHEN (SELECT name FROM person p WHERE p.id = po.person_id) = 'Denis' THEN true
		ELSE false
	END AS check_name
FROM person_order po
WHERE (po.menu_id = 13 OR po.menu_id = 14 OR po.menu_id = 18) AND po.order_date = '2022-01-07';
```