# 🎾 Tennis Data Analysis

## About the Project

This project explores tennis match data collected from **SofaScore between February 1 and March 31, 2024**.

We worked on the project as a three-person team, from cleaning the raw data to answering analytical questions and building visualizations around the results.

Before working with the data, we had to learn enough about **tennis scoring and match structure** to understand what the numbers actually meant. Concepts such as sets, tiebreaks, service breaks, aces, double faults, rankings, court surfaces, and best-of-three match formats affected several of our cleaning and analysis decisions.

That domain knowledge turned out to be just as important as the Python code.

---

## 🧹 Data Preparation

The raw data came as many Parquet files collected through daily snapshots. The same match could therefore appear several times as its information changed over time.

A few of the main challenges we dealt with were:

- **Repeated match snapshots:** We used `snapshot_date` to distinguish updates from real duplicates.
- **Different schemas and data types:** We standardized columns before combining files.
- **Missing values:** We checked whether a missing value was actually a problem before removing or replacing it.
- **Invalid match durations:** Some timing records contained negative or extremely large values, so we used statistical outlier detection to clean them.
- **Tennis-specific structures:** Missing third sets, tiebreaks, and partial matches could all be valid, so we avoided treating them as errors automatically.

This gave us a cleaner and more reliable base for the analysis.

---

## 📊 Analysis

The main part of the project focused on using the cleaned datasets to answer questions about players, matches, tournaments, scoring, and performance.

We worked with **Pandas, Polars, NumPy, and Matplotlib** to aggregate the data, compare groups, calculate statistics, study relationships, and visualize our findings.

Some of the questions we explored included:

- How long does a typical tennis match last?
- What was the longest match in the dataset?
- Which countries recorded the most match wins?
- What is the most common court surface?
- How many aces occur in a match on average?
- Do male and female players differ in double faults?
- Is player height related to ranking?
- Does serving more aces relate to winning?
- Does handedness affect match results?
- How often are break points converted?
- How many countries are represented by the players?
- How many service breaks happen during a match?

---

## 📈 Visualizing the Results

We used graphs throughout the analysis because many of the patterns were easier to understand visually than through summary tables alone.

Our visualizations included:

- **Bar charts** for comparing countries, court surfaces, players, and other categories
- **Distribution plots** for values such as match duration and player characteristics
- **Scatter plots** for relationships such as player height vs. ranking and ace rate vs. winning
- **Comparison charts** for differences between groups, including male and female players
- **Ranked charts** for showing the highest-performing categories and players

The graphs helped us spot weak relationships, unusual values, dominant categories, and differences between groups that were not always obvious from the raw numbers.

---

## 🔍 Five Interesting Findings

### 1. The average match lasted about 1 hour and 43 minutes

After cleaning invalid timing records, the average match duration was:

**102.92 minutes**

The longest valid match in our cleaned data lasted:

**3 hours and 40 minutes**

---

### 2. Outdoor hard courts dominated the dataset

The most frequently recorded surface was:

**Outdoor Hard Court — 16,959 records**

Red clay came next, showing a clear difference in surface representation across the dataset.

---

### 3. France recorded the highest number of match wins

When we grouped match victories by player country, **France** appeared at the top with:

**1,115 recorded wins**

This analysis gave us a simple way to compare country representation through match results.

---

### 4. More aces did not guarantee a win

Players averaged approximately:

**5.39 aces per match**

We also compared ace rate with match outcomes.

The correlation was:

**r = 0.163**

This suggests only a **weak positive relationship** between serving more aces and winning. A powerful serve helps, but the data shows that match results depend on much more than aces alone.

---

### 5. Player height had very little relationship with ranking

We compared player height with ranking and found a correlation of:

**r = 0.103**

The relationship was very weak.

This was one of the useful cases where the scatter plot told the story clearly: taller players were not automatically better ranked.

---

## 📌 A Few More Results

| Analysis | Result |
|---|---:|
| Average player height | **1.82 m** |
| Typical match length | **2 sets** |
| Average aces per match | **5.39** |
| Average match duration | **102.92 min** |
| Longest cleaned match | **3 h 40 min** |
| France match wins | **1,115** |
| Female average double faults | **3.48** |
| Male average double faults | **2.67** |
| Break-point conversion rate | **35.76%** |
| Height vs. ranking correlation | **0.103** |
| Ace rate vs. winning correlation | **0.163** |
| Distinct player countries | **101** |

---

## 🛠️ Tools

- **Python**
- **Pandas**
- **Polars**
- **NumPy**
- **Matplotlib**
- **Jupyter Notebook**
- **Parquet**
- **Git**
- **GitHub**

---

## 📂 Repository Structure

```text
tennis_data_analysis/
│
├── preprocessing/
│   └── Data cleaning and preparation notebooks
│
├── questions/
│   └── Analysis and visualization notebooks
│
├── .gitignore
└── README.md
