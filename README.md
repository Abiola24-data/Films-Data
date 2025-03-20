
# 🎬 **SQL Data Analysis: Insights from the Films Database**  

### **📌 Project Overview**  

In this project, I leveraged **SQL** to analyze the **"Films_data"** database, which contains information about films, people, reviews, and roles. By applying **data retrieval, aggregation, filtering, and joins**, I extracted meaningful insights that can help film industry stakeholders make data-driven decisions.  

This project showcases my expertise in **SQL query writing, database exploration, and analytical problem-solving** to uncover trends in movie performance, audience engagement, and industry success factors.  

---

## **📂 Data Source & Objectives**  

The **"Films_data"** database includes multiple tables related to:  
🎥 **Films** – Movie titles, release years, countries, languages, and financial performance.  
👥 **People & Roles** – Actors, directors, and other contributors.  
⭐ **Reviews & Ratings** – IMDb scores, user reviews, and social media engagement.  

### **🎯 Key Project Objectives**  
✅ Extract insights using **SQL queries** for data retrieval and trend analysis.  
✅ Gain practical experience in **data manipulation** and relational database queries.  
✅ Combine datasets using **SQL joins** to answer complex business questions.  

---

## **📊 Key Business Insights & SQL Solutions**  

### **1️⃣ Top 10 Highest-Grossing Films**  
📌 Identified the **top 10 highest-grossing films** along with their release years.  
```sql
SELECT release_year, title, gross
FROM films
WHERE gross IS NOT NULL
ORDER BY gross DESC
LIMIT 10;
```
📢 *Business Impact:* Understanding box office trends can help studios optimize **release timing and marketing strategies** for future films.  

---

### **2️⃣ Film Production by Country – Top 5 Countries**  
📌 Determined which countries **produced the most films** in the database.  
```sql
SELECT country, COUNT(*) AS release_count
FROM films
GROUP BY country 
ORDER BY release_count DESC
LIMIT 5;
```
📢 *Business Impact:* Helps **global investors & studios** identify the most **active film industries** for expansion and collaboration.  

---

### **3️⃣ Most Popular Movie Languages – Top 3**  
📌 Analyzed the distribution of films based on **language preference**.  
```sql
SELECT language, COUNT(*) AS total_movies
FROM films
GROUP BY language
ORDER BY total_movies DESC
LIMIT 3;
```
📢 *Business Impact:* Provides insights into **audience language preferences**, helping streaming platforms and producers **tailor content offerings**.  

---

### **4️⃣ Average IMDb Score for All Films**  
📌 Computed the **average IMDb score** for films in the database.  
```sql
SELECT AVG(imdb_score) AS avg_imdb_score
FROM reviews;
```
📢 *Business Impact:* Averages help evaluate **industry-wide content quality** and **identify trends in audience ratings**.  

---

### **5️⃣ Most Profitable Country in the Film Industry**  
📌 Determined which **country generates the highest average revenue** from films.  
```sql
SELECT country, AVG(gross) AS avg_revenue
FROM films
WHERE gross IS NOT NULL
GROUP BY country
ORDER BY avg_revenue DESC
LIMIT 1;
```
📢 *Business Impact:* This insight can influence **investment decisions** and **film distribution strategies** in high-profit markets.  

---

### **6️⃣ Highest-Grossing Movie of the 21st Century**  
📌 Found the **highest-grossing** film released after 2000.  
```sql
SELECT title, release_year, gross
FROM films
WHERE release_year >= 2001 AND gross IS NOT NULL
ORDER BY gross DESC
LIMIT 1;
```
📢 *Business Impact:* Helps studios and investors **benchmark financial success** against top performers.  

---

### **7️⃣ Living vs. Deceased People in the Database**  
📌 Counted **how many individuals (actors, directors, writers) are still alive**.  
```sql
SELECT COUNT(*) AS alive_count
FROM people
WHERE deathdate IS NULL;
```
📢 *Business Impact:* Useful for **talent agency databases** and **historical film studies**.  

---

### **8️⃣ Year with the Highest Number of Movie Releases**  
📌 Identified the **busiest year for film production**.  
```sql
SELECT release_year, COUNT(*) AS number_of_movies
FROM films
GROUP BY release_year
ORDER BY number_of_movies DESC
LIMIT 1;
```
📢 *Business Impact:* Helps streaming services and analysts **track industry trends** over time.  

---

### **9️⃣ Top 10 People with the Most Roles**  
📌 Determined the most active individuals in the industry.  
```sql
SELECT people.name, COUNT(roles.id) AS total_roles
FROM people
JOIN roles ON people.id = roles.person_id
GROUP BY people.name
ORDER BY total_roles DESC
LIMIT 10;
```
📢 *Business Impact:* Identifies **highly versatile actors or directors**, beneficial for casting agencies.  

---

### **🔟 Average Number of User Reviews & Votes per Film**  
📌 Calculated the **average user review count & votes** per film.  
```sql
SELECT AVG(num_user) AS avg_user_reviews, 
       AVG(num_votes) AS avg_votes
FROM reviews;
```
📢 *Business Impact:* Helps gauge **audience engagement and review credibility** for films.  

---

### **1️⃣1️⃣ Films with the Highest User & Critic Reviews**  
📌 Identified films that received the most **audience and critic engagement**.  
```sql
SELECT title, MAX(num_user) AS highest_user_reviews, 
       MAX(num_critic) AS highest_critic_reviews
FROM reviews
WHERE num_user IS NOT NULL
ORDER BY highest_user_reviews DESC
LIMIT 1;
```
📢 *Business Impact:* Helps determine **which movies gained the most public & critical attention**.  

---

### **1️⃣2️⃣ Most Facebook-Liked Film & IMDb Score Correlation**  
📌 Found the **most popular movie on Facebook** and examined its IMDb rating.  
```sql
SELECT title, facebook_likes, imdb_score
FROM reviews
ORDER BY facebook_likes DESC
LIMIT 1;
```
📢 *Business Impact:* Identifies how **social media engagement correlates with audience ratings**.  

---

## **📌 Business Takeaways & Strategic Recommendations**  

✅ **Expand production in high-grossing countries**: Investors should focus on **markets with high film profitability**.  
✅ **Prioritize language preferences**: Streaming platforms can **focus on the most-watched languages** for better audience reach.  
✅ **Leverage social media for engagement**: High Facebook likes correlate with **higher audience interest**.  
✅ **Target the most active actors/directors**: Casting agencies can focus on **high-role professionals** for impactful productions.  
✅ **Analyze top-performing years**: Film production companies can **strategically time movie releases** based on past trends.  

---

## **📊 Final Thoughts & Portfolio Value**  

This project demonstrates **SQL expertise** in data extraction, transformation, and trend analysis to uncover insights in the film industry. **By structuring data-driven recommendations**, I translated raw data into **actionable business insights** that can guide decision-making for studios, investors, and streaming services.  

🚀 **Looking for an SQL/Data Analyst role?** Let’s connect and discuss how I can help your organization **turn data into valuable insights!**  

👩🏾‍💻 Connect with me on twitter: https://x.com/General1AB, LinkedIn: www.linkedin.com/in/yussuf-abiola-180474230
---
