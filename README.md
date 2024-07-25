# Phase 3 Project
## Group Members


1.   Yusuf Ali
2.   Winny Chepkoech
3.   Festus Muchemi
4.   Krop Leonard


![pandas](https://img.freepik.com/free-vector/online-cinema-banner-with-open-clapper-board-film-strip_1419-2242.jpg)

# Overview
In the evolving landscape of the entertainment industry, major companies are increasingly investing in original video content to capture audience attention and secure market share. Following this trend, our company has decided to venture into the movie production business by establishing a new movie studio. However, given our lack of experience in this domain, it is crucial to understand the current dynamics of the box office to make informed decisions about the types of films to produce. This analysis will help our company’s new movie studio to strategically plan and create films that are more likely to perform well at the box office, thereby ensuring a competitive edge in the market.

# Business understanding
The film industry is a highly competitive and dynamic sector, where the success of a movie depends on various factors, including genre, budget, runtime,  and release timing. By analyzing these factors, we can gain insights into what makes a movie successful and use this knowledge to guide our production choices. Understanding the preferences and behaviors of moviegoers, as well as the strategies employed by successful films, will be critical in shaping our studio's content creation strategy.

# Objectives
1.	Identify leading movie genres in terms of gross sales to determine which consistently produce high-performing films.
2.	Compare production costs to revenue to identify optimal investment strategies for maximizing return on investment.
3.	Analyze movie ratings and audience preferences to understand what elements contribute to higher viewer satisfaction.
4.	Predict the best movie genres that return highest profit to the firm.

# Data Understanding
The Data that was used for this analysis will be pulled from Three Diffrent sources

`tn.movie_budgets.csv`

* **Source**: The dataset can be found in  [The Numbers database](https://www.the-numbers.com/)

* **Format**: The data is stored in a csv (comma separated value ) file

`tmdb.movies.csv`

* **Source**: The dataset can be found in  [Movies DB database](https://www.themoviedb.org/)

* **Format**: The data is stored in a csv (comma separated value ) file

`rt.movie_info.tsv`

* **Source**: The dataset can be found in  [Rotten tomatos database](https://www.rottentomatoes.com/)

* **Format**: The data is stored in a csv (comma separated value ) file

`im.db`

* **Source**: The dataset can be found in  [IMDB database](https://www.imdb.com/)

* **Format**: The data is stored in a db(database) file 

The Specific rows used in the data set are 

* `budget_release_date` - The date the movie was released
* `title` - The title of the Movie
* `domestic_gross` - The money the movie made in the country it was made
* `worldwide_gross` - The money the movie made around the world 
* `region` - the country the movie was made 
* `runtime_minutes` - The duration of the movie in minutes  
* `genre` - The genre of the movie 

### **Top 10 genres vs budget/worldwide gross**
![Top 10 genres vs budget/worldwide gross](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Top%2010%20genres%20vs%20budget%3Aworldwide%20gross.png)
- `Adventure, Action` and `Animation`: Leads in both worldwide gross and budget, indicating it generates the highest revenue and requires significant investment among the top 10 genres.
- `Comedy, Thriller, and Family`: Rank lowest in worldwide gross and budget, suggesting these genres may face challenges in achieving high revenue and require fewer resources for production.



### **Average Profit Margin by Genre**
![Average Profit Margin by Genre](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Average%20Profit%20Margin%20by%20Genre.png)
- `High-Profit Genres`: Investing in Adventure, History, Mystery, and Music genres is likely to yield higher returns, with Adventure being the most profitable.
- `Low-Profit Genre`: Westerns tend to have lower profitability, indicating a potential riskier investment.
- `Strategic Focus`: To maximize profit margins, the production strategy should prioritize high-margin genres while carefully evaluating the potential and marketing strategies for Westerns.


### **Top runtime vs budget/worldwide gross**
![Top runtime vs budget/worldwide gross](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Top%20runtime%20vs%20budget%3Aworldwide%20gross.png)
- `Highest Profit Margins`: Movies with runtimes of 0-90 minutes and 161-180 minutes have the highest average profit margins.

- `Lowest Profit Margin`: Movies with runtimes of 91-100 minutes have the lowest profit margin.

- `Runtime Impact`: Shorter and longer movies tend to be more profitable, while medium-length movies show lower profitability.

- `Strategic Implication`: To optimize profit margins, focus on producing either shorter or longer films and investigate factors affecting profitability in medium-length movies.

### **Average profit margin by runtime**
![Average profit margin by runtime](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Average%20profit%20margin%20by%20runtime.png)
- `Popular Runtime`: Movies with a runtime of `101-120` minutes have the highest frequency at approximately `700`, indicating strong audience preference.
- `Longer Movies Less Frequent`: Films with runtimes of `141-160, 161-180, and 181-200` minutes each have frequencies below `100.`
- `Audience Preference`: The data suggests audiences generally prefer shorter movies over extended viewing times.

### **Budget vs Worldwide Gross**
![ budget vs worldwide gross](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Budget%20vs%20Worldwide%20Gross.png)
- `General Trend`: There is a positive correlation between budget and worldwide gross. This suggests that movies with higher budgets tend to earn more revenue.

### **Top 10 Genres by Total Budget, Domestic Gross, and Worldwide Gross**
![Top 10 Genres by Total Budget, Domestic Gross, and Worldwide Gross](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Top%2010%20genres%20vs%20budget%3Aworldwide%20gross.png)
- `Highest`: Adventure ranks highest in domestic gross, worldwide gross, and budget, followed by Action in second place.

- `Lowest`: Family ranks lowest among the top 10 genres in these metrics.

- `Implication`: Prioritize investment in Adventure and Action genres for better financial returns, while exploring ways to enhance the performance of Family films.

### **Correlation Heatmap of Numeric Features**
![Correlation Heatmap of Numeric Features](https://github.com/Churabros/Moringa_phase2_project/blob/main/Visualisations/Top%2010%20Genres%20by%20Total%20Budget%2C%20Domestic%20Gross%2C%20and%20Worldwide%20Gross.png)
- `Budget and worldwide_gross` has correlation of `0.802889` This indicates a strong positive correlation, meaning higher budgets tend to be associated with higher worldwide gross.
- `Domestic_gross and worldwide_gross` also has strong corrleation of `0.947102` which shows very high correlation suggests that movies that perform well domestically also perform well worldwide.
- `num_votes and popularity` also has moderate correlation of `0.584154` indicating a strong positive correlation, suggesting that movies with more votes tend to be more popular.

- `Budget and domestic_gross`  has a high corrleation of `0.739963`
- Finally `budget and popularity` has moderate correlation of `0.591660` showcasing a higher-budget movies tend to be more popular.
- On the other side `average_rating` has lower correlations with most other variables, indicating that the average rating is less influenced by budget, gross, etc.
- From here the best potential predictors for the model are
1. `budget`
2. `num_votes`
2. `runtime_minutes`
4. `popularity`  

# Conclusions

# Reccomendations


### Tableau Dashboard Link - https://public.tableau.com/views/phase_2_project_Dashboard/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link







