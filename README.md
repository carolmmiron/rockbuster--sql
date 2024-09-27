
![Captura de pantalla 2024-08-13 120650](https://github.com/user-attachments/assets/fbee51cc-38c7-4f21-9c6c-69aad88f7544)

# ROCKBUSTER-SQL
Rockbuster Stealth LLC is a **movie rental company** that used to have stores around the world. Facing stiff competition from streaming services such as Netflix and Amazon Prime, the Rockbuster Stealth management team is planning to use its existing movie licenses to **launch an online video rental service in order to stay competitive**.
In this project I will use **SQL** to **analyze the data** and **answer any ad-hoc business questions** that other departments may have.

![Captura de pantalla 2024-08-13 145627](https://github.com/user-attachments/assets/0e9bcebf-0dd0-405e-a573-88d3868bd1f9)




# Key Questions 
The Rockbuster Stealth Management Board has asked a series of business questions and they expect data-driven answers that they can use for their 2020 company strategy. 

Here are the **main questions** they’d like to answer:

● Which **movies** contributed the **most/least to revenue** gain?
````bash
CODE SAMPLE

SELECT title, rental_duration, F.name, SUM(D.amount)AS total_amount_paid
FROM film A
INNER JOIN inventory B ON A.film_id=B.film_id
INNER JOIN rental C ON B.inventory_id=C.inventory_id
INNER JOIN payment D ON C.rental_id=D.rental_id
INNER JOIN film_category E ON A.film_id=E.film_id
INNER JOIN category F ON E.category_id=F.category_id
GROUP BY title,rental_duration, F.name
ORDER BY total_amount_paid ASC
LIMIT 10;
````

● What was the **average rental duration** for all videos? [descriptive analysis script](https://github.com/MIRONW64/ROCKBUSTER-SQL/blob/main/Scripts/Descriptive%20analysis%20descriptive%20analysis%20from%20the%20film%20table)

● Which **countries** are Rockbuster customers based in? [script link](https://github.com/MIRONW64/ROCKBUSTER-SQL/blob/main/Scripts/Top%2010%20countries%20location%20of%20the%20most%20valuable%20clients)

● Where are **customers** with a **high lifetime value** based? [script link](https://github.com/MIRONW64/ROCKBUSTER-SQL/blob/main/Scripts/Most%20valuable%20customers)

● Do **sales figures** vary between **geographic regions**? [script link](https://github.com/MIRONW64/ROCKBUSTER-SQL/blob/main/Scripts/Title%2C%20movie%2C%20Genre%20and%20revenue%20generated%20from%20the%20top%205%20revenue%20driver%C2%B4s%20countries)


# Tools

- PostgreSQL 
- Excel
- Powerpoint
- [Tableau](https://public.tableau.com/app/profile/carolina.martin7470/viz/Rockbuster2020planning/ROCKBUSTER2020Planning)


# Data Set 
In this Achievement, you’ll be using a data set that contains information about Rockbuster’s film inventory, customers, and payments, among other things. 
For this Achievement you will load the data set into the **PostgreSQL** database. 
