### DVD Rental database analysis

This was the first project from Udacity's Programming for Data Science Nanodegree covering the block on SQL.

The goal of this project is to query the Sakila DVD Rental database, provided by Udacity. This database holds information about a fictional company that rents movie DVDs.

Students need to answer four questions chosen of their choice and this way gain an understanding of the customer base, such as what the patterns in movie watching are across different customer groups, how they compare on payment earnings, and how the stores compare in their performance. The schema for the DVD Rental database is also provided:

![image](https://github.com/user-attachments/assets/f2015e73-4cd8-4e41-9991-4804f706d851)

# Question 1
What are the top 5 most rented movies?

To find out which movies were the most popular, I counted the total rentals for each film title. The query uses a WITH clause (CTE) to first group the data by film and then limit the output to the top 5 titles.
Result:
Top rented titles include Bucket Brotherhood, Rocketeer Mother, and Grit Clockwork.

![Screenshot 2025-07-05 155836](https://github.com/user-attachments/assets/26e9f0a5-43d7-4185-bf91-b19d5677c58b)
![Chart2](https://github.com/user-attachments/assets/22263b0d-2358-46b3-b9cb-c2a8e6c4cc2b)

 Question 2
Which store makes more money, and how does their revenue change from month to month?

I grouped payments by store and month, and used a LAG() window function to compare each month’s revenue to the previous one. This helped reveal trends and sudden drops.
Result:
Both stores earned more in March and April. Revenue fell sharply in May for both stores, with Store 2 consistently earning slightly more.

![Screenshot 2025-07-05 190358](https://github.com/user-attachments/assets/037c3e45-c4cf-4997-ac8d-eea1a5281955)

![Chart4](https://github.com/user-attachments/assets/cf3cc672-17d2-4e17-97a8-48732941b538)

# Question 3
How many rentals does each staff member handle on average per week?

Using a CTE, I grouped rentals by staff and week, and then averaged the weekly counts per employee.

Result:
Both employees handle a similar workload, with Mike slightly ahead in average weekly rentals.
![Screenshot 2025-07-05 155008](https://github.com/user-attachments/assets/3e369570-3f42-4481-b3e0-8e82bacf26e0)


![Screenshot 2025-07-05 154912](https://github.com/user-attachments/assets/9c1f75e7-95f8-4366-ae05-5ff7a9bbcc32)

Question 4
Which film categories generate the most revenue?

I joined payment data with film categories and summed the revenue per category. Then I used a RANK() window function to assign a revenue-based ranking.

Result:
Sports, Sci-Fi, and Animation are the top 3 revenue-generating categories.

![Screenshot 2025-07-05 161428](https://github.com/user-attachments/assets/055b5b95-9d97-4e70-a80e-c4c18156fe1a)
![Chart3](https://github.com/user-attachments/assets/4fbb3171-2999-4e6b-9c33-306f39409ef8)
