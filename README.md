`\с` - показывает в какой бд мы находимся и через какого юзера
`\с name_of_db` - переключается к этой бд
`\l` - показывает все бд
`\dt` - показывает все таблицы в бд
`\du` - показывает всех юзеров
`\q` - выход


```sql
CREATE DATABASE name_of_db; 
-- создает базу данных
```

```sql
CREATE TABLE name_of_table (
    name_of_column1 data_type constraint,
    name_of_column2 data_type constraint,
    ...
); 
-- создает таблицу с полями
```

```sql
INSERT INTO name_of_table (name_of_column1, name_of_column2) 
VALUES (val1, val2);
-- добавляет запись в таблицу
```

```sql
SELECT * FROM name_of_table; 
-- достает все поля и записи из таблицы

SELECT name_of_column1, name_of_column2 FROM name_of_table; 
-- достает только указанные столбцы из таблицы
```