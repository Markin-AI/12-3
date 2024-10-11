# Домашнее задание к занятию "`SQL. Часть 1`" - `Маркин Алексей`

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

---

### Решение 1

```
select district from address where district like 'K%a' and district not like '% %';
```

![Задание 1](https://github.com/Markin-AI/12-3/blob/main/img/1-1.png)

---

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

---

### Решение2

```
select * from payment
where date(payment_date) >= '2005-06-15' and date(payment_date) <= '2005-06-18' and amount > 10.00;
```

![Задание 2](https://github.com/Markin-AI/12-3/blob/main/img/2-1.png)

---

### Задание 3

Получите последние пять аренд фильмов.

---

### Решение3

```
SELECT * FROM rental ORDER BY rental_date DESC LIMIT 5;
```

![Задание 3](https://github.com/Markin-AI/12-3/blob/main/img/3-1.png)

---

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

---

### Решение4

```
SELECT   REPLACE(LOWER(first_name), 'll', 'pp') AS first_name,  
REPLACE(LOWER(last_name), 'll', 'pp') FROM customer 
WHERE first_name='KELLY' or first_name='WILLIE'
```

![Задание 4](https://github.com/Markin-AI/12-3/blob/main/img/4-1.png)

---