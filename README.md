# Spotify Streaming Analytics & Revenue Optimization Platform

An end-to-end product data analytics solution that transforms raw user sentiment and contextual streaming data into an interactive, enterprise-grade, dual-page Power BI analytics dashboard. 

---

##  Project Overview
This platform explores user psychology, demographic trends, and feature interaction loops to extract actionable product insights for retention engineering and premium subscription conversion optimization.

###  Core Product Insights Discovered
* **The Generation Gap:** User satisfaction peaks heavily within the tech-literate **20–35 young adult demographic**, showing a sharp drop-off in child-centric age cohorts, indicating a major feature-optimization gap for younger profiles.
* **Passive Routine Anchoring:** The highest user volume streams primarily during passive, daily transit contexts (**Traveling** and **Leisure Time**), highlighting where algorithmic recommendation accuracy matters most.
* **The Student Friction Point:** While the *Student Plan* shows strong affinity volume, its conversion trajectory is heavily stagnated by pricing friction compared to standard *Individual Plans*.

---

##  Dashboard Architecture & Visual Design

The application utilizes a cohesive, responsive dark-mode layout designed natively to mirror the Spotify user interface, prioritizing a seamless user experience (UX) and data clarity at a glance.

### Page 1: User Persona & Behavioral Triggers
*Focuses on user demographics, daily lifestyle contexts, and psychological mood triggers.*
 <img width="1203" height="738" alt="Screenshot 2026-05-26 125055" src="https://github.com/user-attachments/assets/377be685-acde-4a26-b288-346689463a61" />


### Page 2: Feature Engagement & Revenue Optimization
*Focuses on product feature retention tracking, subscription intent, and the monetization funnel.*
 <img width="1203" height="731" alt="Screenshot 2026-05-26 125120" src="https://github.com/user-attachments/assets/296ab7bb-fe4c-41e2-8746-fa094d049cd7" />


---

##  Data Engineering & Architectural Challenges

### 📐 The Data Schema (Star Schema)
To ensure optimal performance and dynamic cross-filtering capacity, the dataset was normalized into a structured relational model consisting of fact tables, dimension tables, and a dedicated bridge table.



###  Overcoming the Bidirectional Cross-Filtering Roadblock
* **The Problem:** When compiling average algorithmic rating scores across distinct user emotional moods, the visual matrix displayed a flat, non-filtering global average rating of `3.56` for every single category row.
* **The Root Cause:** The initial relationship path restricted filtering strictly downstream from the User Dimension table to the Mood Bridge table. Because the metric values lived in the core Fact table, the filter direction was physically blocked from traveling back upstream to isolate the data.
* **The Engineering Fix:** Double-clicked the relationship line between the user profile dimensions and the many-to-many mood bridge table, explicitly switching the **Cross Filter Direction** setting from *Single* to **Both**. This opened a two-way data highway, enabling flawless, real-time contextual calculation integrity across all visuals.

---

##  Technologies Used
* **Power BI Desktop** (Data Modeling, DAX, UI/UX Interface Design)
* **Power Query** (ETL Pipeline, Data Cleaning, and Attribute Schema Mapping)
* **Markdown / GitHub** (Project Documentation & Repository Management)
