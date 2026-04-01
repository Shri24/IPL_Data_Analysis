# 🏏 IPL Match Data Analysis

## 📌 Overview
This project analyzes historical Indian Premier League (IPL) match data (2008–2016) to uncover insights related to team performance, match outcomes, and key influencing factors such as toss decisions and venues.

The dataset contains **577 matches** with detailed attributes including teams, winners, venues, toss results, and umpires.

---

## 📂 Dataset Information
- **Total Matches:** 577  
- **Seasons Covered:** 2008 – 2016  
- **Cities:** 30+ unique locations  
- **Columns:** 18 features  

### 🔑 Key Columns:
- `season` – IPL season year  
- `city` – Match location  
- `team1`, `team2` – Competing teams  
- `toss_winner` – Team that won the toss  
- `toss_decision` – Bat or field decision  
- `winner` – Match winner  
- `result` – Match result type (normal/tie/no result)  
- `player_of_match` – Best performer  
- `venue` – Stadium name  

---

## 🎯 Objectives
- Analyze team performance across seasons  
- Evaluate the impact of toss decisions on match outcomes  
- Identify top-performing teams and players  
- Explore venue-based advantages  
- Generate actionable insights using data analysis  

---

## 📊 Key Insights
- 📈 Cities like **Mumbai** hosted the highest number of matches  
- 🏆 Toss decisions influenced match outcomes significantly  
- ⚡ Certain players consistently won *Player of the Match* awards  
- 🏟️ Venue plays a key role in match results  

---

## 🛠️ Tools & Technologies
- Python (Pandas, NumPy)  
- SQL  
- Data Visualization (Matplotlib / Power BI / Tableau)  

---

## 📌 Sample Analysis (Python)

```python
import pandas as pd

# Load dataset
df = pd.read_csv('data.csv')

# Display basic info
print(df.info())

# Top 5 teams by wins
top_teams = df['winner'].value_counts().head(5)
print(top_teams)

# Toss impact analysis
toss_win_match_win = (df['toss_winner'] == df['winner']).sum()
total_matches = len(df)

print("Toss win -> Match win %:", (toss_win_match_win / total_matches) * 100)

# Most Player of the Match awards
top_players = df['player_of_match'].value_counts().head(5)
print(top_players)
