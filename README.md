# new1
# Steel Data Analysis Project

In this project, I analyzed a dataset from a car showroom to gain insights into car sales and salespersons. The case study includes three datasets: cars, sales, and salespersons.

![Data Analysis](https://github.com/prashant9621/steel-data-/assets/136049491/84b9fb7f-f5c3-4e12-b71c-f8de2b87d9fc)

## Questions Explored

### 1. Details of All Cars Manufactured in 2022

To find information about cars manufactured in 2022:

```sql
SELECT c.car_id, c.make, c.type, c.style, c.cost, s.purchase_date
FROM sales s
JOIN cars c ON c.car_id = s.car_id
WHERE YEAR(s.purchase_date) = 2022;


2. Total Number of Cars Sold by Each Salesperson
To find the total number of cars sold by each salesperson:
SELECT sp.name, COUNT(*) AS total_cars_sold
FROM salesperson sp
JOIN sales s ON sp.salesman_id = s.salesman_id
GROUP BY sp.name;


![Screenshot (8)](https://github.com/prashant9621/steel-data-/assets/136049491/06bdf6af-9f29-4867-811d-f67363dc1763)

3. Total Revenue Generated by Each Salesperson
To calculate the total revenue generated by each salesperson:

sql
SELECT sp.name, SUM(c.cost) AS total_revenue
FROM salesperson sp
JOIN sales s ON sp.salesman_id = s.salesman_id
JOIN cars c ON c.car_id = s.car_id
GROUP BY sp.name;

4. Total Revenue Generated by Each Car Type
To calculate the total revenue generated by each car type:

select sp.name,c(*) from saleperson sp join sales s on sp.salesman_id=s.s.salesman_id join cars c on s.car_id=c.car_id ;

5.what is the name and city of the salesperosn who sold the most number of cars i the year 2023 ?
select top1 sp.name as salespeson,sp.city,year(s.purchase_date) as year,count(car_id) as total_cars from salesperson sp join sales s onorer by total_cars desc;

Conclusion
.Tom Lee emerged as the best salesperson of 2023, suggesting the need for recognition or incentives.
.Car types "C-Class," "X5," and "Corolla" generated the most revenue, indicating potential for further focus.
.The car type "A4" had the lowest popularity, raising considerations to discontinue its maintenance.








