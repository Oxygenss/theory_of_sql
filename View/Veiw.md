## View

- `View` - это виртуальное представление данных (данные нигде не сохраняются), которое основано на результате SQL-запроса, обращающегося к одной или нескольким реальным таблицам в базе данных.

```sql
-- Базовый синтаксис
CREATE VIEW v_name AS
SELECT * FROM table
WHERE column = value;
```

- `Materialized View` - физическое представления данных, при котором данные сохраняются, как реальная таблица. Создается физическая копия данных, что позволяет повторно использовать данные без необходимости каждый раз выполнять запрос. Но данные могут устаревать, если данные в базе данных изменяются. Для обновления данных в материализованных представлениях требуется выполнить процесс обновления.

```sql
-- Базовый синтаксис
CREATE MATERIALIZED VIEW mv_name AS
SELECT * FROM table
WHERE column = value;
```

`REFRESH MATERIALIZED VIEW` используется в PostgreSQL для обновления данных хранящихся в материализованном представлении (Materialized View). Выполняется запрос, который был использован для создания этого представления.

``` sql
-- Обновление данных 
REFRESH MATERIALIZED VIEW mv_name;
```
<br>
<br>
<br>
<br>
<br>

## EXTRA
--- 

### То есть `View` при вызове заново выполняет запрос, на основе которого создан, а `Materialized View` делает это один раз и потом каждый раз обращается к уже созданным данным. Но данные в `Materialized View` могут устаревать, так как данные в базе данных могут обновляться, поэтому нужно выполнять процесс обновления.



`Разница между With и View:`

Представления (View) создаются как объекты в базе данных и могут быть повторно использованы в различных запросах. Они хранят определение в каталоге данных и могут быть индексированы или иметь другие свойства, связанные с безопасностью. С другой стороны, конструкция WITH представляет собой временный объект, который существует только в рамках одного запроса. Он не сохраняется в базе данных и не может быть индексирован или иметь другие свойства безопасности, связанные с базой данных.