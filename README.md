# Udemy Courses Data Analysis & Pricing Strategy (Power BI)

## Project Overview
An end-to-end data analysis and business intelligence project built using **Power BI** to explore **3,676 Udemy courses** across four major domains (*Web Development*, *Business Finance*, *Musical Instruments*, and *Graphic Design*). 

The dashboard uncovers key trends in course popularity, student enrollment behavior, pricing dynamics, and content duration to provide actionable recommendations for **instructors**, **training companies**, and **e-learning platforms**.

---

## Key Business Questions Answered
1. **Market Demand:** Which course subjects and skill levels attract the highest number of subscribers?
2. **Pricing vs. Enrollment:** Does a higher price tag discourage students from enrolling, or does course value drive demand?
3. **Duration vs. Price:** Does increasing the total hours or lectures of a course guarantee a higher price?
4. **Paid vs. Free Dynamics:** How do paid and free courses compare in terms of total subscribers, reviews, and lecture counts?
5. **Growth Trend:** How has the volume of published courses evolved over the years?

---

## Data Cleaning & Transformation (Power Query)
Before building the data model, the raw dataset (`3,682` rows x `11` columns) underwent thorough preprocessing in **Power Query**:
* **Deduplication:** Removed duplicate `course_id` entries (`6` exact duplicates removed), while preserving courses with identical titles that differed in price, level, or duration.
* **Text Standardization:** Applied `Trim`, `Clean`, and `Capitalize Each Word` formatting, and used `Text.Remove` to strip unwanted special characters (`!`, `@`, `#`, `$`, brackets) from course titles.
* **Feature Engineering:**
  * Converted boolean `is_paid` values into user-friendly `Paid` and `Free` labels.
  * Standardized `content_duration` by splitting text units (`hours` vs. `mins`) and converting all durations into a unified numeric metric (**minutes**).
  * Created a **Price Category** segmentation (`Free`: $0, `Cheap`: <= $50, `Average`: $51-$130, `Expensive`: > $130).
* **Data Modeling & DAX:** Built custom DAX measures (`Total Courses`, `Total Subscribers`, `Total Reviews`, `Total Lectures`, `Max Price`, `Min Price`, `Average Price`) organized inside a dedicated Measures folder.

---

## Dashboard Architecture
The interactive Power BI report consists of **4 main pages**:
1. **Home Page:** Clean navigation hub with custom page navigator buttons.
2. **Overview Page:** High-level KPIs, subscribers by subject, course distribution by subject and skill level (Treemap with Drill-Down), publishing trend over time, and Top 10 most popular courses.
3. **Price Analysis Page:** Average price by subject, scatter plots analyzing *Price vs. Subscribers* and *Duration vs. Average Price*, subscriber share by price tier, and Paid vs. Free breakdowns (Donut charts).
4. **Course Details (Drill-Through):** Detailed granular table accessible via drill-through from any subject or level, complete with dynamic `Paid/Free` slicers.

---

## Key Insights & Recommendations
* **
