* `\с` - показывает в какой бд мы находимся и через какого юзера

* `\с name_of_db` - переключается к этой бд

* `\l` - показывает все бд

* `\dt` - показывает все таблицы в бд

* `\du` - показывает всех юзеров

* `\q` - выход


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


> primary key (pk) - первичный ключ
> это ограничение, которое мы указываем на те поля,которые должны быть уникальными для того, чтобы потом их использовать в связях (например id)

> foreign key (fk) - внешний ключ
> это ограничение, которое мы указываем на те поля, которые будут ссылаться на pk в другой таблице, для создания связи

```sql
CREATE TABLE author (
    id serial primary key,
    first_name varchar(50),
    last_name varchar(50)
)

CREATE TABLE book (
    id serial,
    title varchar(100),
    published year,
    author_id int foreign key referenses author (id)
)
```

> JOIN - инструкция, которая позволяет в запросах SELECT брать данные из нескольких таблиц
> INNER JOIN (JOIN) - когда достаются только те записи, у которых есть полная связь
> FULL JOIN - когда достаются абсолютно все записи со всех таблиц
> LEFT JOIN - когда достаются все записи с 'левой' таблицы и так же те записи с полной связью
> RIGHT JOIN - когда достаются все записи с 'правой' таблицы и так же те записи с полной связью

```sql
SELECT author.first_name, book.title 
FROM author
JOIN book ON author.id = book.author_id
```
