# Домашнее задание к занятию 12.1. «Базы данных» Баранов Сергей


---


### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

Какие данные хранятся в этих таблицах :

1. Сотрудники (staff) - ФИО (varchar(50)), дата найма сотрудника (date);
2.Данные о зарплате сотрудников (salary) - (numeric); 
3.Должность (position) - занимаемая должность сотрудника (varchar(50));
4.Подразделение (division) - Структурное подразделение (varchar(50));
5.Тип подразделения (structura) - отдел в котором работает сотрудник (varchar(50));
6. Адреса филиала (branch_address) - адрес (varchar(50));
7. Проекты (project) - наименование проекта для конкретного сотрудника(varchar(50)).


Какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

1. фио - строковый (varchar)
2. ОКЛАД - числовой (decimal/numeric)
3. должность - строковый (varchar)
4. Тип подразделения - строковый (varchar)
5. Дата - дата (date)
6. Адрес - местонахождение филиала (varchar)
7. Проект - строковый (varchar)

staff (

staff_id integer primary_key,

last_name varchar(50),

first_name varchar(50),

patronymic varchar(50),

divisions_id integer foreign_key,

structura_id integer foreign_key,

date date,

position_id integer foreign_key,

salary_id numeric foreign_key,

address_id integer foreign_key,

project_id integer foreign_key

)


salary (

salary_id integer primary_key,

pay numeric

)


position (

position_id integer primary_key,

position_name, varchar(50),

salary_id integer foreign_key

)


divisions (

divisions_id integer primary_key,

department varchar(50),

department_type varchar(50)

)


structura (

structura_id integer primary_key,

group varchar(50),

structura_type varchar(50),

structura_title varchar(50)

)


branch address (

address_id integer primary_key,

region varchar(50),

city varchar(50),

street varchar(50),

house varchar(50)

)


project (

project_id integer primary_key,

project_name varchar(50)

)

