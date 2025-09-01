# NAME:T.KAVINAJAI
# REGISTER NO:212223100020

**#Experiment 1: EDA in IPL Dataset**
**Aim:**
To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

**Algorithm / Procedure:**

**1.Import Libraries**
  Import pandas for data handling.
  Import matplotlib and seaborn for visualization.
**2.Load Dataset**
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().
**3.Matches per Season (Univariate Analysis)**
  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.
**4.Top Winning Teams (Univariate Analysis)**
  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.
**5.Toss Decisions (Univariate Analysis)**
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
**6.Top Venues (Univariate Analysis)**
  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.
**7.Draw Insights**
  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.
  
  **Program**
```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
matches = pd.read_csv("matches.csv")
print("Dataset Shape:", matches.shape)
print(matches.head()) 
```
<img width="833" height="458" alt="image" src="https://github.com/user-attachments/assets/6a275212-b04a-464d-a4a2-887e311f277a" />

```
season_counts = matches['season'].value_counts().sort_index()
print("\nMatches per season:\n", season_counts)
```
<img width="452" height="183" alt="image" src="https://github.com/user-attachments/assets/ebd7311e-f077-4960-bf75-48b7418ac8ab" />

```
plt.figure(figsize=(8,4)) 
sns.barplot(x=season_counts.index, y=season_counts.values, palette="viridis")
plt.title("Number of Matches per Season")
plt.xlabel("Season") 
plt.ylabel("Matches")
plt.show()
```
<img width="737" height="312" alt="image" src="https://github.com/user-attachments/assets/c3ad88cd-7220-42eb-9302-259bab575a44" />
```
toss_decision = matches['toss_decision'].value_counts()
print("\nToss Decisions:\n", toss_decision)
plt.figure(figsize=(6,4)) 
sns.barplot(x=toss_decision.index, y=toss_decision.values, palette="Set2") 
plt.title("Toss Decisions (Bat or Field)") 
plt.show()
```
<img width="627" height="369" alt="image" src="https://github.com/user-attachments/assets/af3564c8-4fc8-44fb-9295-bbef773aee3a" />

```
venue_counts = matches['venue'].value_counts().head(5) 
print("\nTop Venues:\n", venue_counts)
plt.figure(figsize=(8,4))
sns.barplot(y=venue_counts.index, x=venue_counts.values, palette="coolwarm")
plt.title("Top 5 Venues by Matches Hosted") 
plt.xlabel("Matches Hosted") 
plt.ylabel("Venue") 
plt.show()
```
<img width="821" height="425" alt="image" src="https://github.com/user-attachments/assets/a58d18d7-7df0-429b-872d-35130daa95a2" />

 **Result**
This experiment is executed successfully
