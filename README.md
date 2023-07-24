### Домашнее задание к занятию 4. «PostgreSQL» 6.4 Баранов Сергей

### Задача 1

Используя Docker, поднимите инстанс PostgreSQL (версию 13). Данные БД сохраните в volume.

Подключитесь к БД PostgreSQL, используя `psql`.

Воспользуйтесь командой `\?` для вывода подсказки по имеющимся в `psql` управляющим командам.

**Найдите и приведите** управляющие команды для:

- вывода списка БД,
- подключения к БД,
- вывода списка таблиц,
- вывода описания содержимого таблиц,
- выхода из psql.

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_1.1(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_1.2(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_1.3(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_1.4(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_1.5(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_1.6(6.4).png)


---


### Задача 2

Используя `psql`, создайте БД `test_database`.

Изучите [бэкап БД](https://github.com/netology-code/virt-homeworks/tree/virt-11/06-db-04-postgresql/test_data).

Восстановите бэкап БД в `test_database`.

Перейдите в управляющую консоль `psql` внутри контейнера.

Подключитесь к восстановленной БД и проведите операцию ANALYZE для сбора статистики по таблице.

Используя таблицу [pg_stats](https://postgrespro.ru/docs/postgresql/12/view-pg-stats), найдите столбец таблицы `orders` 
с наибольшим средним значением размера элементов в байтах.

**Приведите в ответе** команду, которую вы использовали для вычисления, и полученный результат.


![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_2.1(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_2.2(6.4).png)

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_2.3(6.4).png)


---



### Задача 3

Архитектор и администратор БД выяснили, что ваша таблица orders разрослась до невиданных размеров и
поиск по ней занимает долгое время. Вам как успешному выпускнику курсов DevOps в Нетологии предложили
провести разбиение таблицы на 2: шардировать на orders_1 - price>499 и orders_2 - price<=499.

Предложите SQL-транзакцию для проведения этой операции.

Можно ли было изначально исключить ручное разбиение при проектировании таблицы orders?

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_3(6.4).png)

При начальном проектировании таблиц можно сделать ее секционированной, тогда не нужно переименовывать исходную таблицу и переносить данные в новую.


---


### Задача 4

Используя утилиту `pg_dump`, создайте бекап БД `test_database`.

Как бы вы доработали бэкап-файл, чтобы добавить уникальность значения столбца `title` для таблиц `test_database`?

![monitoring](https://github.com/12sergey12/6.4_PostgreSQL/blob/main/images/postgres_4(6.4).png)


title character varying(80) NOT NULL UNIQUE

---
