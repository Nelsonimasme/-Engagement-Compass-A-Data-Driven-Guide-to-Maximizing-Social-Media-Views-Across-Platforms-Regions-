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

```SQL

    -- PLATFORM WITH THE HIGHEST AVG ENGAGEMENT VIEW

SELECT Platform, 
ROUND(AVG(Views)) As Avg_Highest_views,

FROM `nelson-1-project.social_media_trend.Vira_social_media_trend` 

GROUP BY Platform
ORDER BY Avg_Highest_views DESC


```

<img width="315" height="149" alt="platform_with_high_engagement_view" src="https://github.com/user-attachments/assets/446ada0e-d7e8-492e-b7d1-995fe4aaf6e1" />



