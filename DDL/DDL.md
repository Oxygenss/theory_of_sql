# DDL (Data Definition Language)

`DDL` - это подмножество SQL, предназначенная для создания, изменения и удаления структуры объектов базы данных, таких как таблицы, представления, схемы и индексы. DDL операторы используются для определения схемы базы данных и не имеют прямого доступа к данным, в отличие от DML (Data Manipulation Language) операторов, которые используются для манипулирования данными в пределах схемы, созданной DDL. Основные операторы DDL включают.

- `CREATE` Используется для создания новых объектов базы данных, например, таблиц, представлений или индексов

``` sql
-- Пример сохдания функции
CREATE TABLE Student_info
(
    College_Id number(2),
    College_name varchar(30),
    Branch varchar(10)
);
```

- `ALTER` Позволяет изменять существующие объекты базы данных, например, добавлять или удалять столбцы в таблице

``` sql
-- Добавление нового столбца Email в таблицу Customers
ALTER TABLE Customers
ADD Email varchar(255);
```

- `DROP` Удаляет существующие объекты базы данных, например, таблицы или индексы

``` sql
-- Удаление столбца Email из таблицы Customers
ALTER TABLE Customers
DROP COLUMN Email;
```

```sql
-- Удаление индекса
DROP INDEX idx_1;
```

- `TRUNCATE` Удаляет все строки из таблицы, сохраняя при этом структуру таблицы и индексы

``` sql
-- Очистка всех записей из таблицы Student_info, сохраняя структуру таблицы
TRUNCATE TABLE Student_info;
```

- `RENAME` Переименовывает существующие объекты базы данных, например, таблицы

``` sql
-- Переименование таблицы Employee в EMP
RENAME TABLE Employee To EMP;
```