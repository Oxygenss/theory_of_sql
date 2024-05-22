## DML (Data Manipulation Language)

`DML` — это подмножество SQL, используемое для манипулирования данными в базе данных. Операторы DML включают SELECT, INSERT, UPDATE, и DELETE. Они позволяют получать, добавлять, изменять и удалять данные в таблицах базы данных.

`Операции в DML:`

- `INSERT` используется для добавления новых строк в таблицу

``` sql
-- Базовый синтаксис
INSERT INTO table_name (column1, column2, column3,...)
VALUES (value1, value2, value3,...);
```

``` sql
-- Пример
INSERT INTO employees (first_name, last_name, age)
VALUES ('John', 'Doe', 30);
```

``` sql
-- Пример с добавление нескольких записей
INSERT INTO table_name (column1, column2,...)
VALUES (value1, value2,...), (valueA, valueB,...);
```

- `UPDATE` используется для изменения существующих записей в таблице

``` sql
-- Базовый синтаксис
UPDATE table_name
SET column1 = value1, column2 = value2,...
WHERE condition;
```

- `DELETE` используется для удаления существующих записей из таблицы

``` sql
-- Базовый синтаксис
DELETE FROM table_name WHERE condition;
```

``` sql
-- Удаление всех записей из таблицы
DELETE FROM table_name;
```