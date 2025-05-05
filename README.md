# 🧭 User Journey Analysis – 365 Data Science Platform

In this project, I explored real-world data from 365 Data Science’s subscription-based learning platform and analyzed how users interact with the site. A **user journey** refers to the path a user takes while navigating through different pages on the site, and understanding this behavior is key to improving user experience and increasing subscriptions.

---

## 🚀 Project Overview

The main objective of this project is to **clean and organize raw data** on user journeys and then extract meaningful insights to guide business decisions.

Raw data is often messy—before I can analyze it, I need to **preprocess** it. Think of it like sorting a messy drawer so I can find what I’m looking for more easily.

---

## 🧹 Why Preprocess the Data?

Preprocessing involves cleaning and structuring the data to reveal patterns and improve interpretability. For example, by removing unnecessary or repetitive information, I can better understand what users are actually doing and how their actions lead (or don’t lead) to purchases.

---

## 🛠️ Preprocessing Functions

To prepare the dataset for analysis, I used three key functions:

### 1. `group_by()`

- **Purpose**: Consolidate all page visits from a single user into one journey.
- **How It Works**:
  - Creates a new table with a single row per user.
  - Combines session data based on filters (e.g. first N sessions, last N sessions).
  - Sorts and returns a unified view of each user’s journey.

---

### 2. `remove_pages()`

- **Purpose**: Remove specific pages (e.g. login, sign-up) that are not relevant to behavior analysis.
- **How It Works**:
  - Makes a copy of the original dataset.
  - Splits each journey into a list of visited pages.
  - Removes specified pages.
  - Joins the remaining pages back into a cleaned journey string.

---

### 3. `remove_duplicates()`

- **Purpose**: Eliminate repeated consecutive pages to reduce noise.
- **How It Works**:
  - Splits each user journey into a list of pages.
  - Filters out consecutive duplicates.
  - Returns the deduplicated journey string.

---

## 🧩 Workflow

1. **Import the Raw Data**
2. **Run Preprocessing Functions** (`group_by()`, `remove_pages()`, `remove_duplicates()`)
3. **Export Cleaned Data** for further analysis

---

## 🔍 Analytical Insights

Once I cleaned the data, I explored differences between **monthly** and **annual** subscribers:

### 📊 Resource Center Usage

- Higher total visits to the **Resource Center** were seen among annual plan users.
- However, when comparing **presence** (i.e., how often the Resource Center appears in journeys), the difference is small:  
  - ~12% for monthly users  
  - ~14% for annual users  

This suggests that the higher usage may be due to **longer session lengths** rather than broader interest.

---

### 💳 Pricing Page Patterns

- **Monthly Users**: Pricing is the 5th most visited page (~102 clicks).
- **Annual Users**: Pricing is the 2nd most visited page (~329 clicks).

This implies annual subscribers are more **purchase-ready** early in their journey. These users are prime targets for marketing efforts.

---

### 🎯 Career Tracks Page

- Monthly users frequently visit the **Career Tracks** page, which offers structured learning paths.
- This might appeal to users with **short-term goals**, though it’s unclear if this increases or limits their likelihood of purchasing longer plans.

---

## 🔁 Preprocessing Strategy Notes

- **First Sessions**: Reveal initial impressions and user intent.
- **Last Sessions**: May contain clutter but could show the **tipping point** before a conversion.
- Pages like `Login`, `Checkout`, and `Sign up` were removed as they didn’t add behavioral insight.

---

## ⚠️ Limitations

Currently, I can only analyze **users who converted** (purchased a plan). This restricts my ability to identify what actually **drives** conversions.

To truly understand conversion behavior, I need:

- Data from **users who didn’t purchase**
- **Marketing information** (e.g. ad exposure, campaign sources)
- **User engagement data** post-purchase (e.g. retention, activity levels)

---

## 💡 Final Thoughts

This project provides a flexible and efficient toolkit for analyzing user journeys. With preprocessing handled, I can dive into deeper insights to support data-driven decisions.

To improve this analysis further, integrating **non-converting user data** and **post-purchase engagement metrics** would be essential.

---

### 📁 Files in this Repository

- `user_journey_analysis.ipynb` – Main notebook with preprocessing and analysis code
- `raw_data.csv` – Input dataset
- `cleaned_data.csv` – Cleaned user journey dataset after preprocessing
- `README.md` – Project overview (this file)

---

## 📈 Next Steps

- Incorporate non-purchasing users into the analysis
- Merge marketing attribution and demographic data
- Analyze post-purchase behavior for long-term engagement patterns

---
