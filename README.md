# SALES-ANALYSIS-AT-READIFY-BOOKSTORE
This repository demostrates a beginner project on data analysis and data manipulation 
### Project Overview 
As a junior Data Analyst at "Readify", a well-known bookstore chain. Your primary task is to analyze the company's book sales data to understand recent sales trends. This analysis will help "Readify" in making informed decisions about stock management and marketing strategies.

### Objective
To identify the top 5 best-selling authors based on the total quantity of books sold.

### Data Sources
The "book sales" and "book details"dataset will be used to conduct the analysis. this dataset contains detailed information in obtaining our objective.

### Tools 
- MS Excel: result presentation 
- Sql Lite : Data analysis 

### SQL Analysis
- Joining tables 
  - book_sales and book_details tables on the book_id field. This step links each sale to the corresponding book and its author.
```sql
SELECT *
FROM book_sales bs
JOIN book_details bd ON bs.book_id = bd.book_id;
```
- Grouping by author and SUM Quantities 
  - grouping the results by the author and sum the quantities of books sold for each author. This step calculates the total sales for each author.
  
```sql
SELECT bd.author, SUM(bs.quantity) AS total_quantity_sold
FROM book_sales bs
JOIN book_details bd ON bs.book_id = bd.book_id
GROUP BY bd.author;
```
- Order and Limit the Results
  - put results in order by the total quantity sold in descending order and limit the output to the top 5 authors. this step provides us with an answer to our key question 

```sql
SELECT bd.author, SUM(bs.quantity) AS total_quantity_sold
FROM book_sales bs
JOIN book_details bd ON bs.book_id = bd.book_id
GROUP BY bd.author
ORDER BY total_quantity_sold DESC
LIMIT 5;
```
### Excel result representation 
List of top five best-selling authors [Download here](https://eu.docworkspace.com/d/sICqD4pbTAcXwuL0G)


