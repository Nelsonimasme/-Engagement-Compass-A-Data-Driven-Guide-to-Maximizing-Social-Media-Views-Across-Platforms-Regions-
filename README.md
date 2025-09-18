# -Engagement-Compass-A-Data-Driven-Guide-to-Maximizing-Social-Media-Views-Across-Platforms-Regions-
This project focuses on understanding how content creators, brands, and social media managers can **optimize their strategies to maximize engagement and reach** across platforms, regions, and audience segments.



---

## Table of Contents

1. **Introduction**
   1.1 Background & Context
   1.2 Project Objectives
   1.3 Scope of Work

2. **Dataset Overview**
   2.1 Data Sources
   2.2 Key Variables & Metrics
   2.3 Data Limitations

3. **Data Preparation & Cleaning**
   3.1 Handling Missing or Duplicate Values
   3.2 Standardizing Formats (Dates, Regions, Platforms)
   3.3 Creating Derived Metrics (Engagement Ratios, Averages)

4. **Methodology**
   4.1 SQL Queries & Data Exploration
   4.2 Analytical Framework (KPIs, Engagement Metrics)
   4.3 Visualization Approach (**Tableau**)

5. **Analysis & Findings**
   5.1 Platforms with Highest Average Engagement per Post
   5.2 Content Types Driving Views, Likes, & Shares
   5.3 Regional Engagement Patterns
   5.4 Impact of Hashtags on Views
   5.5 Temporal Trends: Months & Days with Highest Engagement
   5.6 Common Traits of Top-Performing Posts

6. **Discussion & Insights**
   6.1 Key Observations
   6.2 Interpretation of Results
   6.3 Limitations of the Study

7. **Recommendations**
   7.1 Platform Strategy
   7.2 Content Optimization
   7.3 Regional Targeting
   7.4 Hashtag & Timing Strategy

8. **Conclusion**
   8.1 Summary of Findings
   8.2 Final Takeaways

9. **Appendices**
   9.1 SQL Queries Used
   9.2 Data Cleaning Logs
   9.3 Additional Charts & Tables

---



---

### **Background**

* Social media is a **key driver of brand growth, audience reach, and engagement**.
* Success depends on **understanding audience behavior, platform dynamics, and content performance**.
* Engagement metrics (views, likes, shares, hashtags) are **critical for visibility and campaign success**.
* With huge volumes of data, a **data-driven approach** is essential to uncover trends in **platforms, regions, content types, and timing**.
* This project analyzes real data to provide **actionable insights for optimizing social media strategy**.

---

---

### **Scope of Work**

This project focuses on analyzing social media engagement data to uncover patterns and provide actionable recommendations for improving content strategy. The scope includes:

1. **Data Collection & Understanding**

   * Reviewing the provided dataset and identifying key variables (e.g., **platform, content type, views, likes, shares, Comments, hashtags, regions, dates**).

2. **Data Cleaning & Preparation**

   * Handling missing or duplicate values.
   * Standardizing formats for dates, regions, and platforms.
   * Creating derived fields (e.g., engagement ratios, averages).

3. **Exploratory Data Analysis (EDA)**

   * Analyzing engagement trends across **platforms, content types, regions, hashtags, and time periods**.
   * Identifying **correlations and patterns** in audience interactions.

4. **SQL Queries & Insights Generation**

   * Writing and documenting SQL queries for data extraction and aggregation.
   * Summarizing findings based on analytical questions (**platforms, regions, content, hashtags, timing, top-performing posts**).

5. **Data Visualization**

   * Using **Tableau** to create intuitive visualizations (**bar charts, and line charts**).
   * Highlighting comparisons, trends, and patterns for better interpretation.

6. **Reporting & Presentation**

   * Documenting methodology, queries, and cleaning steps.
   * Preparing a Github presentation summarizing overview, findings, insights, and recommendations.

---

Here’s a clean **Data Source** section you can use in your project report or slides 👇

---

### **Data Source**

* The dataset used in this project comes from **`nelson-1-project.social_media_trend.Vira_social_media_trend`** (BigQuery table).
* It contains structured records of **social media activity** across multiple platforms.

* **Key fields include**:

  * **Post\_Date** – date of content posting
  * **Platform** – social media platform (e.g., Instagram, Twitter, TikTok, etc.)
  * **Region** –  location of audience engagement
  * **Content\_Type** – type of content posted (Livestreams, video, Shorts, Post,Tweets etc.)
  * **Hashtags** – hashtags used in the post
  * **Views, Likes, Shares, Comments** – engagement metrics
  * **Engagement\_Level** – classification of engagement intensity

* Data was analyzed using **SQL (BigQuery)** for extraction and aggregation, and **Tableau** for visualization and reporting.

---


---

### **Data Limitations**

While the dataset provides valuable insights, there are some limitations to consider:

1. **Data Completeness**

   * Some records were having **missing values** (e.g., incomplete hashtags, regions not specified,Date Not Specify as well).
   * Not all engagement metrics may be consistently available across platforms.

2. **Platform Representation**

   * Some platforms were having **more data points** than others, leading to possible bias in comparisons.

---


---

### **Project Objectives**

The main objective of this project is to **analyze social media engagement data** and provide actionable insights to help content creators, brands, and social media managers optimize their strategies for **maximum reach and engagement**.

Specifically, the project aims to:

1. **Identify top-performing platforms** in terms of average engagement per post.
2. **Examine content types** (e.g., Livestreams, videos, Shorts, Post e.t.c) that generate the highest views, likes, shares and Comments.
3. **Analyze regional engagement patterns** to determine where content resonates most strongly.
4. **Evaluate the impact of hashtags** on driving higher visibility and engagement.
5. **Discover time-based trends**, including months and specific days that yield higher engagement.
6. **Uncover common characteristics of top-performing posts**, such as themes, formats, or timing.
7. **Provide data-driven recommendations** for improving social media strategies across platforms.

---


### **DATA AGGREGATION**


 **PLATFORM WITH THE HIGHEST AVG ENGAGEMENT VIEW**

SELECT Platform, 
ROUND(AVG(Views)) As Avg_Highest_views,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend` 

GROUP BY Platform
ORDER BY Avg_Highest_views DESC

```SQL

SELECT Platform, 
ROUND(AVG(Views)) As Avg_Highest_views,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend` 

GROUP BY Platform
ORDER BY Avg_Highest_views DESC


```

<img width="315" height="149" alt="platform_with_high_engagement_view" src="https://github.com/user-attachments/assets/446ada0e-d7e8-492e-b7d1-995fe4aaf6e1" />




**PLATFORM WITH THE HIGHEST AVG ENGAGEMENT LIKES**

```SQL

SELECT Platform, 
ROUND(AVG(Likes)) As Avg_Highest_likes,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend` 

GROUP BY Platform
ORDER BY Avg_Highest_likes DESC

```

<img width="339" height="188" alt="platform_with_high_eng_likes" src="https://github.com/user-attachments/assets/a8c9a864-851a-4102-8ee1-68f1e53c7546" />



 **PLATFORM WITH THE HIGHEST AVG ENGAGEMENT SHARES**

```SQL

SELECT Platform, 
ROUND(AVG(Shares)) As Avg_Highest_shares,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend` 

GROUP BY Platform
ORDER BY Avg_Highest_shares DESC

```
<img width="324" height="193" alt="platform_with_high_eng_shares" src="https://github.com/user-attachments/assets/4ffe7611-546d-431a-b496-78c25b76c7fc" />


 **PLATFORM WITH THE HIGHEST AVG ENGAGEMENT COMMENTS**

```SQL

SELECT Platform, 
ROUND(AVG(Comments)) As Avg_Highest_comments,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend` 

GROUP BY Platform
ORDER BY Avg_Highest_comments DESC

```
<img width="312" height="175" alt="platform_with_high_eng_comments" src="https://github.com/user-attachments/assets/c4afaf4c-4702-4c4a-adfb-8fa4fbffacd5" />



 **CONTENT_TYPE WITH THE MOST VIEWS**

```SQL

SELECT Content_Type, 
      SUM(Views)  AS Most_views,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`  

GROUP BY Content_Type
ORDER BY  Most_views DESC

```
<img width="287" height="207" alt="Content_most_views" src="https://github.com/user-attachments/assets/3633c2b3-1a6f-4288-ab98-db984ab59bb8" />



 **CONTENT_TYPE WITH THE MOST LIKES**

```SQL

SELECT Content_Type, 
      SUM(Likes)  AS Most_likes,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`  

GROUP BY Content_Type
ORDER BY  Most_likes DESC

```
<img width="293" height="171" alt="Content_most_likes" src="https://github.com/user-attachments/assets/a6b97456-a365-4e18-95f0-68b023afd0a7" />



 **CONTENT_TYPE WITH THE MOST SHARES**

```SQL

SELECT Content_Type, 
      SUM(Shares)  AS Most_shares,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`  

GROUP BY Content_Type
ORDER BY  Most_shares DESC

```
<img width="256" height="196" alt="content_most_shares" src="https://github.com/user-attachments/assets/5f3203db-185d-4239-abe9-e7bfd07dc6df" />



 **REGION WITH THE MOST ENGAGEGING LEVEL ON VIEWS**

```SQL

SELECT Region,
      SUM(Views) AS Region_views
      

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`  

GROUP BY Region
ORDER BY  Region_views DESC

```
<img width="254" height="220" alt="Region_most_view" src="https://github.com/user-attachments/assets/4dcd0acc-0ba9-4083-8855-ccf96a22c888" />




 **SPECIFIC HASHTAGS THAT HAS THE MOST ENGAGEMENT LEVEL ON VIEWS**

```SQL

SELECT Hashtag,
      SUM(Views) AS Hashtag_views
      

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`  

GROUP BY Hashtag
ORDER BY  Hashtag_views DESC

```
<img width="259" height="236" alt="HASHTAG_VIEWS" src="https://github.com/user-attachments/assets/f14b0bdd-d15b-46d4-977d-2766cfb8b90f" />



 **THE MONTH WITH THE MOST ENGAGEMENT LEVEL ON VIEWS**

```SQL

SELECT FORMAT_DATE("%B", DATE(Post_Date)) AS Month_Name,
  COUNT(Engagement_Level) AS High_engagement

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`

GROUP BY Month_Name
ORDER BY High_engagement DESC

```
<img width="272" height="236" alt="mont_with_most_engaging_level" src="https://github.com/user-attachments/assets/790a9db1-e7c6-4511-bd1a-f3048e122c37" />



 **THE DAY WITH THE MOST ENGAGEMENT LEVEL ON VIEWS**

```SQL

SELECT FORMAT_DATETIME("%A",Post_date) AS Day_of_d_week,  SUM(Views) AS Engagement_level_views, 

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend`

GROUP BY Day_of_d_week
ORDER BY Engagement_level_views DESC

```


 **SIMILARITIES OF TOP PERFORMING POST**

```SQL

SELECT 
    Platform,
    Region, 
    Content_Type, 
    Hashtag, 
    COUNT(*) AS Post_Count,
    ROUND(AVG(Views)) AS Avg_Views,
    ROUND(AVG(Likes)) AS Avg_Likes,
    ROUND(AVG(Shares)) AS Avg_Shares,
    ROUND(AVG(Comments)) AS Avg_Comments
FROM 
    `nelson-1-project.social_media_trend.Vira_social_media_trend`
WHERE 
    Likes > 300000 
    OR Shares > 90000 
    OR Views > 400000 
    OR Comments > 40000
GROUP BY 
    Platform, Region, Content_Type, Hashtag
ORDER BY 
    Avg_Views DESC, 
    Avg_Likes DESC, 
    Avg_Shares DESC, 
    Avg_Comments DESC

```

<img width="520" height="217" alt="SIMI" src="https://github.com/user-attachments/assets/ed6becff-cfd4-44ac-8eff-8c509f246ea1" />

<img width="505" height="192" alt="SIMI 2" src="https://github.com/user-attachments/assets/47128f40-837c-4212-a32f-54435ec46d1c" />


### **DATA VISUALIZATION**


**Platform With Highest Average Engagement On Views**

<img width="960" height="356" alt="view_platform" src="https://github.com/user-attachments/assets/18232248-9a4b-4b07-9ae1-65e20190b172" />


**Platform With Highest Average Engagement On Likes**

<img width="960" height="358" alt="Like_platform" src="https://github.com/user-attachments/assets/a32c4c5b-1389-4835-a01a-5e4e1b8ccb8b" />


**Platform With Highest Average Engagement On Shares**

<img width="960" height="358" alt="shares_plaform" src="https://github.com/user-attachments/assets/657679da-f688-4159-a194-92c827c23e77" />


**Platform With Highest Average Engagement On Comments**

<img width="960" height="349" alt="Comments_platform" src="https://github.com/user-attachments/assets/73c9937d-c938-43f9-9541-4932c805fa67" />



**Content Type With The Highest Engagement On Views**

<img width="960" height="356" alt="Content_type_Views" src="https://github.com/user-attachments/assets/d2ab5f12-26b0-4db3-ad1a-5192590d3b5c" />

**Content Type With The Highest Engagement On Likes**
<img width="960" height="359" alt="content_type_likes" src="https://github.com/user-attachments/assets/b551f37f-664e-4ae1-afba-dbdc1e11538f" />


**Content Type With The Highest Engagement On Shares**
<img width="959" height="364" alt="Content_type_shares" src="https://github.com/user-attachments/assets/19622529-3a76-49c0-9ab9-9eb0566defd1" />


**Region With The Most Engagement Level Views**
<img width="960" height="351" alt="Region_views" src="https://github.com/user-attachments/assets/753ef2b9-3b26-4492-89a3-53251605119c" />


**THE SPECIFIC HASHTAGS THAT LEADS THE HIGHEST ENGAGEMENT (VIEWS)**
<img width="960" height="353" alt="#Hashtag_view" src="https://github.com/user-attachments/assets/18a3746d-f68c-4c52-8c67-74d931fad519" />



**Visualizing The Month With The Most Engagement Level On Views**
<img width="960" height="356" alt="months" src="https://github.com/user-attachments/assets/6ecf21de-beef-45cf-8903-d3ba27d8ffb4" />


**Visualizing The DAY With The Most Engagement Level On Views**
<img width="959" height="354" alt="Days" src="https://github.com/user-attachments/assets/3dc6ecbf-a8ea-48f3-8b97-56ec663ef086" />


**Visualizinf Similarities Between Top Performing Post**
<img width="957" height="370" alt="simlarities 1" src="https://github.com/user-attachments/assets/09f74eb5-917e-4a63-bc1a-a2265ea20b5d" />
<img width="956" height="363" alt="similarities 2" src="https://github.com/user-attachments/assets/1ce84732-2910-42ba-94a1-e61f2a9db857" />
<img width="956" height="366" alt="similarities 3" src="https://github.com/user-attachments/assets/1c6ea79d-3a64-405d-a681-4ff9a6651cfb" />




