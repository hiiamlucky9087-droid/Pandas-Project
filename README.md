# Pandas Projects & Exploratory Data Analysis

A collection of hands-on data analysis, feature engineering, and exploratory data projects built using Python and Pandas. This repository covers real-world data wrangling workflows—from parsing unstructured text fields to demographic and macroeconomic data analysis.

---

## 📁 Projects Included

1. [Project 1: Anime Data Feature Extraction & Analysis](#project-1-anime-data-feature-extraction--analysis)
2. [Project 2: Global Demographic & Governance Capstone](#project-2-global-demographic--governance-capstone)

---

## Project 1: Anime Data Feature Extraction & Analysis

### Overview
In this project, the raw dataset (`anime.csv`) contained a messy `Title` column where show names, formats (TV/Movie), episode counts, broadcast dates, and member statistics were crammed into a single string. I built custom parsing functions to isolate these into clean, structured attributes for quantitative analysis.

### What Was Done
* **Extracted Episode Counts:** Sliced out episode counts formatted inside parentheses (e.g., `(64 eps)` $\rightarrow$ `64`) and converted them to integer values.
* **Parsed Airing Timeframes:** Extracted start and end broadcast dates into a dedicated `TimeStamp` field (e.g., `Apr 2009 - Jul 2010`).
* **Calculated Broadcast Duration:** Used `pd.Period` with monthly frequency (`freq='M'`) to compute total active airing months.
* **Data Aggregation & Ranking:** 
  * Identified top-rated titles using `.idxmax()` and boolean masks.
  * Filtered top 5 series by score and episode count.
  * Located the longest-running title across the entire dataset.

### Key Takeaways
* **Highest Rated Anime:** *Fullmetal Alchemist: Brotherhood* (Score: 9.10)
* **Most Episodes:** *Gintama* (201 episodes)
* **Longest Airing Span:** *Ginga Eiyuu Densetsu* (*Legend of the Galactic Heroes*), active across 110 months (~9 years)

---

## Project 2: Global Demographic & Governance Capstone

### Overview
An exploratory data analysis (EDA) project analyzing a global dataset (`Countries.csv`) comprising 194 countries across 64 socioeconomic, geographical, and political indicators. The goal was to clean the data, inspect distributions, and answer specific geographical, demographic, and governance questions.

### What Was Done
* **Dataset Auditing & Summary:** Inspected data types, null distributions, and summary statistics across 64 indicators (`.info()`, `.describe()`).
* **Extreme Value Filtering:**
  * Identified the most populated country (*India* with ~1.41B people) and least populated nation (*Tuvalu* with 11,312 residents) alongside their respective capitals (*New Delhi* and *Funafuti*).
  * Queried political leadership for the world's second most populous nation (*Xi Jinping*, China) using `.nlargest()`.
* **Regional & Continental Slicing:**
  * Categorized countries into 22 global regions and extracted specific country lists (e.g., Eastern Europe).
  * Filtered African nations to find the most populous country on the continent (*Nigeria*).
* **Democratic & Political Governance Insights:**
  * Ranked the top 5 countries by democracy score (*Norway, Iceland, Sweden, New Zealand, Denmark*).
  * Identified nations with missing/unlisted political leadership data (`.isna()`).
  * Performed string matching on formal names (`country_long`) to find that 125 countries officially contain the word *"Republic"*.

---

## 🗂️ Repository Structure

```text
├── anime.csv                         # Raw dataset for Feature Extraction project
├── FeatureExtractionProject.ipynb    # Feature extraction & text wrangling notebook
├── Countries.csv                     # Global socioeconomic & governance dataset
├── DataCapstoneProject.ipynb         # EDA capstone notebook
└── README.md                         # Project documentation
