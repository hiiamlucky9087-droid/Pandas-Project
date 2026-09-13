# Anime Data Feature Extraction & Analysis

I built this project to practice data wrangling and feature engineering using Python and Pandas. 

The starting dataset (`anime.csv`) had a messy `Title` column where almost everything—show name, type (TV/Movie/OVA), episode count, airing dates, and member counts—was crammed together into one raw string. I wrote custom functions to pull that information out into separate, usable columns so I could run queries on scores, episode lengths, and runtimes.

---

## What I Did

* **Cleaned episode counts:** 
  * Parsed the numbers inside parentheses (like `(64 eps)` $\rightarrow$ `64`).
  * Removed string tails (`eps`) and converted the column to integers so it can be sorted numerically.
* **Extracted airing dates:** 
  * Sliced out start and end date ranges (e.g., `Apr 2009 - Jul 2010`) into a clean `TimeStamp` column.
* **Calculated airing duration:** 
  * Split the timestamps and used Pandas `pd.Period` with monthly frequency (`freq='M'`) to measure how many months each show was on the air.
* **Analyzed the dataset:**
  * Found top-rated shows using `.idxmax()` and boolean masks.
  * Sorted and filtered for the top 5 highest-rated anime and top 5 longest series by episode count.
  * Identified which anime had the longest total broadcast run.

---

## Quick Insights

* **Top-Rated Anime:** *Fullmetal Alchemist: Brotherhood* (Score: 9.10)
* **Most Episodes:** *Gintama* (201 episodes)
* **Longest Airing Span:** *Ginga Eiyuu Densetsu* (*Legend of the Galactic Heroes*) running for 110 months (~9 years between Jan 1988 and Mar 1997).

---

## How to Run It

1. **Clone the repo:**
   ```bash
   git clone [https://github.com/hiiamlucky9087-droid/Pandas-Project.git](https://github.com/hiiamlucky9087-droid/Pandas-Project.git)
   cd Pandas-Project
