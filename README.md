# Домашнее задание к занятию "`SQL. Часть 1`" - `Савин Алексей`
Задание можно выполнить как в любом IDE, так и в командной строке.  

## Задание 1 

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Решение 1  

```
SELECT DISTINCT district FROM address WHERE (district LIKE 'K%a' AND district NOT LIKE '% %');
```
![part1](https://github.com/AI-Savin/hw_SQL-1/blob/main/img/part1.png)  

---
## Задание 2  

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

### Решение 2

```
SELECT * FROM payment WHERE (DATE(payment_date) BETWEEN '2005-06-15' AND '2005-06-18') AND amount > 10;
```
![part2](https://github.com/AI-Savin/hw_SQL-1/blob/main/img/part2.png)  

---
## Задание 3  

Получите последние пять аренд фильмов. 
### Решение 3 

```
SELECT * FROM payment ORDER BY payment_date DESC LIMIT 5;
```
![part3](https://github.com/AI-Savin/hw_SQL-1/blob/main/img/part3.png)  

---
## Задание 4  
Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.
### Решение 4  

```
SELECT customer_id, last_name, LOWER( REPLACE(first_name,'LL','PP')) FROM customer WHERE (first_name LIKE "Kelly" OR first_name LIKE "Willie");
```
![part4](https://github.com/AI-Savin/hw_SQL-1/blob/main/img/part4.png)   


