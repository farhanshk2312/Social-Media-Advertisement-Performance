# Digital Marketing Analytics Project

Data Source: https://www.kaggle.com/datasets/alperenmyung/social-media-advertisement-performance

# Objective

This project was undertaken to gain a deeper understanding of marketing analytics by working with a synthetic but realistic relational dataset. The goal was to design and implement a complete data pipeline (ELT), perform data transformations, and build a Power BI dashboard with key marketing performance metrics such as revenue, conversions, ROAS, and AOV.
________________________________________
# Dataset Overview

  The dataset simulates a digital advertising ecosystem inspired by platforms like Meta Ads Manager. It consists of four interconnected entities:
  
   •	Users – Demographic and interest data (user_id, gender, age, country, location, interests).
  
   •	Campaigns – Budget and timeline information (campaign_id, name, start_date, end_date, total_budget).
   
   •	Ads – Creative assets with targeting parameters (ad_id, campaign_id, ad_platform, ad_type, target_gender, target_age_group, target_interests).
   
   •	Ad Events – User engagement logs (event_id, ad_id, user_id, timestamp, event_type such as Impression, Click, Purchase).
  
  This relational structure allowed complex joins, segmentation, and funnel analysis.
________________________________________
# Data Pipeline (ELT Approach)

1. Extract
  
    •	Ingested raw CSV files (users.csv, campaigns.csv, ads.csv, ad_events.csv) into SQLite as staging tables (raw_users, raw_campaigns, raw_ads, raw_ad_events).

 2. Load

    •	Loaded the raw tables into Python & Power BI.

    •	Checked for duplicate user IDs and removed them before inserting into the database.
  
3. Transform
  
    •	Date Standardization – Converted text dates into proper DATE fields.
  
    •	User Interests Normalization – Split multiple interests into separate rows (exploded into a normalized tag table).

    •	Joins – Connected fact (ad_events) to dimensions (ads, campaigns, users).
  
    •	Cost Allocation – Campaign budgets distributed across impressions to calculate cost at ad and user levels.
________________________________________

# Metrics & Calculations
  
  Core Metrics
  
  •	Impressions = COUNT of event_type = "Impression".
  
  •	Clicks = COUNT of event_type = "Click".
  
  •	Purchases = COUNT of event_type = "Purchase".
  
  •	Distinct Users = DISTINCTCOUNT(user_id).

# Funnel KPIs
  
  •	Conversion Rate (CVR) = Purchases ÷ Clicks (or Purchases ÷ Impressions).
  
  •	Average Order Value (AOV) = Revenue ÷ Purchases.
  
  •	Return on Ad Spend (ROAS) = Revenue ÷ Cost.

# Cost & Revenue
  
  •	Total Budget = SUM(campaigns[total_budget]).
  
  •	Total Cost = Budget distributed over impressions → at campaign level, equal to budget; at ad/user level, allocated proportionally.
  
  •	Revenue = SUM(fact_ad_events[revenue], from purchases).

# Time-based Metrics

  •	Daily Events = COUNTROWS of events by day.
  
  •	Daily Revenue = SUM of revenue per day using DATESINPERIOD.
________________________________________
# Key Learnings
  
  1.	Marketing Analytics Foundations – Understood how impressions, clicks, conversions, and spend tie together in performance marketing.
  
  2.	Data Engineering – Built an ELT pipeline from CSV → SQLite → Power BI, with cleaning, transformations, and schema design.
  
  3.	KPI Definitions – Learned to define and calculate industry-standard metrics like CVR, ROAS, and AOV.
  
  4.	Visualization – Designed a structured dashboard for campaign and user insights.
  
  5.	Cost Allocation Logic – Implemented impression-based budget allocation to analyze spend at a granular level.
________________________________________
Conclusion
This project successfully simulates a real-world marketing analytics workflow, starting from raw ad event data to a decision-ready Power BI dashboard. By building this, I gained practical experience in SQL, Python, ELT processes, and DAX, while also improving my understanding of digital advertising metrics and their strategic importance.
This exercise was done to develop foundational knowledge in marketing analytics and demonstrate data engineering, modeling, and visualization skills in a portfolio-ready project.
