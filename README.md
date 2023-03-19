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
2. Данные о зарплате сотрудников (salary) - (serial); 
3. Должность (position) - занимаемая должность сотрудника (varchar(50));
4. Подразделение (devision) - Структурное подразделение (varchar(50));
5. Тип подразделения (structura) - отдел в котором работает сотрудник (varchar(50));
6. Адреса филиала (branch_address) - адрес (varchar(50));
7. Проекты (project) - наименование проекта для конкретного сотрудника(varchar(50)).


Какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.
1. фио - строковый (varchar)
2. оклад - числовой (decimal/numeric)
3. должность - строковый (varchar)
4. тип подразделения - строковый (varchar)
5. дата - дата (tinyint)
6. адрес - местонахождение филиала (varchar)
7. проект - строковый (varchar)

staff (
staff_id primary_key,
FIO varchar(50),
devision_id varchar(50),
structura_id varchar(50),
date date,
salary_id numeric,
address_id varchar(50),
project_id varchar(50),
)

salary (
salary_id primary_key
staff_id
)

position (
position _id primary_key
position _name, varchar(50)
salary, money
)

devision (
devision_id primary_key
department varchar(50)
department_type
)

structura (
structura_id primary_key
group varchar(50)
structura_type
structura_title
)

branch_address (
address_id primary_key
edge varchar(50)
city varchar(50)
street varchar(50)
house varchar(50)
)

project (
project_id primary_key
project_name, varchar(50))
)
