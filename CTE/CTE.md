## CTE

`CTE (Common Table Expressions)` — это способ временного создания подзапроса, который можно использовать в других частях SQL-запроса

```sql
-- Общий пример
-- Создается временная таблица Employee_CTE и используется в запросе в дальнейшем
WITH Employee_CTE (EmployeeID, EmployeeName, DepartmentID)
AS
(
  SELECT EmployeeID, EmployeeName, DepartmentID
  FROM Employees
  WHERE DepartmentID = 3
)
SELECT EmployeeID, EmployeeName, DepartmentID
FROM Employee_CTE;
```

### Так же удобно после всех JOIN-в использовать WHERE вместо WITH в начале

```sql
-- Пример 1 с CTE(WITH)
WITH sort AS (
	SELECT * FROM person
	WHERE address IN ('Moscow', 'Samara') AND gender = 'male'
)

SELECT s.name
FROM sort s
INNER JOIN person_order po ON po.person_id = s.id
INNER JOIN menu m ON m.id = po.menu_id
WHERE pizza_name IN ('pepperoni pizza', 'mushroom pizza')
ORDER BY s.name DESC;
```

```sql
-- Пример 1 с WHERE
select p.name
from person as p
inner join person_order as po on po.person_id = p.id
inner join menu as m on m.id=po.menu_id
where p.address in ('Samara', 'Moscow') and m.pizza_name in ('pepperoni pizza', 'mushroom pizza') and p.gender = 'male'
order by p.name desc
```

```sql
-- Пример 2 с CTE(WITH)
WITH pep AS (
	SELECT p.id, p.name FROM person p
	INNER JOIN person_order po ON p.id = po.person_id
	INNER JOIN menu m ON po.menu_id = m.id AND m.pizza_name = 'pepperoni pizza'
	WHERE p.gender = 'female'

)

SELECT pep.name
FROM pep
INNER JOIN person_order po ON pep.id = po.person_id
INNER JOIN menu m ON po.menu_id = m.id AND m.pizza_name = 'cheese pizza'
ORDER BY pep.name ASC;
```

```sql
-- Пример 2 с CTE(WITH)
WITH sel AS (
	SELECT * FROM menu
	WHERE pizza_name = 'pepperoni pizza' OR pizza_name = 'mushroom pizza'
)

SELECT sel.pizza_name, p.name AS pizzeria_name, sel.price
FROM sel
INNER JOIN pizzeria p ON p.id = sel.pizzeria_id
ORDER BY pizza_name ASC, pizzeria_name ASC;
```

```sql
-- Пример 2 с WHERE
select pizza_name, p.name as pizzeria_name, price
from menu
inner join pizzeria as p on p.id = menu.pizzeria_id
where pizza_name in ('mushroom pizza', 'pepperoni pizza')
order by pizza_name, pizzeria_name
```
