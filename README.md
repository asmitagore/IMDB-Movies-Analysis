# **🎬 IMDB Movies Analysis – Power BI Dashboard**  

![Dashboard Preview](https://github.com/asmitagore/IMDB-Movies-Analysis/blob/main/IMDBOVERVIEW.png?raw=true) 
![Dashboard Preview](https://github.com/asmitagore/IMDB-Movies-Analysis/blob/main/GENREANDDIRECTOR.png?raw=true) 

## **📌 Project Overview**  
This **Power BI dashboard** provides a deep analysis of **IMDB movie data**, highlighting trends in **director performance, genre revenue, IMDb ratings, and social media impact**. The insights help understand factors influencing movie success.  

## **🎯 Key Features & Insights**  
- **Top Directors by IMDb Ratings**: Identifies the best-rated directors.  
- **Top 10 Genres by Revenue**: Analyzes high-performing movie genres.  
- **Revenue & Budget by Director**: Tracks financial success.  
- **Social Media Impact**: Correlation between Facebook likes & IMDb scores.  

## **📊 Tools & Technologies Used**  
- **Power BI** – Data visualization & insights  
- **Excel** – Data preprocessing & cleaning  
- **DAX (Data Analysis Expressions)** – Custom calculations & measures  

## **📂 Project Files**  
- `IMDB_Movies_Cleaned.xlsx` - Preprocessed dataset  
- `IMDB_Movies.pbix` - Power BI file with dashboard  
- `README.md` - Project documentation  

## **📈 Power BI Visuals Used**  
- **Line Chart** – Top-rated directors by IMDb score  
- **Treemap** – Top 10 genres by revenue  
- **Bubble Chart** – Social media impact on IMDb ratings  
- **KPI Cards** – Total Directors, Revenue, Avg. IMDb Score  

## **📢 How to Use the Dashboard**  
1. **Download the Power BI file (`.pbix`)** from this repository.  
2. Open it in **Power BI Desktop**.  
3. Explore interactive visuals, filter data, and gain insights!  

## **💡 Key DAX Measures Used**
### **1️⃣ Top 10 Directors by IMDb Rating**
```DAX
Top_10_Directors = 
VAR RankedDirectors = 
    ADDCOLUMNS(
        SUMMARIZE(
            IMDB_Movies, 
            IMDB_Movies[director_name]
        ), 
        "Avg_IMDb", CALCULATE(AVERAGE(IMDB_Movies[imdb_score]))
    )
RETURN 
    TOPN(10, RankedDirectors, [Avg_IMDb], DESC)
```

### **2️⃣ Revenue by Genre**
```DAX
Total_Revenue_By_Genre = 
SUMMARIZE(
    IMDB_Movies,
    IMDB_Movies[genres],
    "Total Revenue", SUM(IMDB_Movies[gross])
)
```

### **3️⃣ Social Media Impact on IMDb Ratings**
```DAX
Social_Media_Impact = 
CORR(IMDB_Movies[movie_facebook_likes], IMDB_Movies[imdb_score])
```

### **4️⃣ Budget vs. Gross Revenue by Director**
```DAX
Budget_vs_Revenue = 
SUMMARIZE(
    IMDB_Movies,
    IMDB_Movies[director_name],
    "Total Budget", SUM(IMDB_Movies[budget]),
    "Total Gross", SUM(IMDB_Movies[gross])
)
```
I'm always looking to improve! Feel free to **connect with me on LinkedIn** and share your thoughts. 🚀  
📌 **LinkedIn:** [https://www.linkedin.com/in/asmita-gore-147405350/]  

## **📎 Additional Enhancements**  
- **Interactive filters** for Year, Genre, and Director.  
- **Custom color themes** for better UI.  
- **Optimized data model** for fast loading.  

### ⭐ If you find this project useful, don’t forget to **star this repository** on GitHub! 🚀
