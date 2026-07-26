# IPL Performance Analysis (2008–2025)

An end-to-end data analytics project analyzing 18 seasons of IPL data — from raw, messy datasets to a fully interactive 6-page Power BI dashboard.

## Project Overview

This project explores team performance, batting and bowling trends, and historical records across every IPL season from 2008 to 2025. It combines Python for data cleaning and exploratory analysis with Power BI for building the final interactive dashboard.

## Data

Four datasets covering all 18 seasons:
- `ipl_matches_clean.csv` — match-level data (teams, toss, results, venues)
- `ipl_deliveries_clean.zip` — ball-by-ball delivery data (extract before use)
- `ipl_players_clean.csv` — player details (batting/bowling style, images)
- `ipl_teams_clean.csv` — team details (names, logos)

## Data Cleaning

Before analysis, the raw data required several corrections:
- Standardized inconsistent team names across all tables (e.g., a franchise appearing under two different spellings in different files)
- Mapped historical team changes accurately (Deccan Chargers → Sunrisers Hyderabad, 2008–2012)
- Identified a data quality gap where the "stage" column (League/Final) was only reliably populated for the most recent season, and built a verified reference table of IPL champions (2008–2025) to correct it

## Key Findings

- Teams batting second (chasing) have won 54% of completed matches
- Winning the toss provides only a marginal edge — a 52% win rate
- Average first-innings scores have risen from ~150 runs (2008) to ~190 runs (2025)
- Only 8 of 15 franchises have ever won the title; Mumbai Indians and Chennai Super Kings lead with 5 titles each
- Very few bowlers maintain a strong economy rate in the final overs of an innings, historically the toughest phase to bowl in

## Dashboard Structure

**1. Overview** — Key stats, all-time top performers, team-level filtering

![Overview Page](images/Overview%20Page.png)

**2. Team Performance** — Wins by team, toss impact, chasing vs. defending, season trends

![Team Performance Page](images/Team%20Performance%20Page.png)

**3. Batting Insights** — Top run scorers, best batting venues, powerplay analysis

![Batting Page](images/Batting%20Page.png)

**4. Bowling Insights** — Top wicket-takers, bowling style split, death-overs economy

![Bowling Page](images/Bowling%20Page.png)

**5. Records & Awards** — Player of the Match leaders, IPL champions, all-time records

![Records Page](images/Records%20Page.png)

**6. Player Profile** — Drill-through page with full career stats for any selected player

![Player Profile Page](images/Player%20Profile%20Page.png)

## Technical Highlights

- **Data modeling**: Built relationships across four tables, including cases requiring multiple relationship paths between the same two tables (e.g., linking both batter and bowler to the players table). Used `USERELATIONSHIP()` in DAX to manage these within individual measures.
- **DAX measures**: 20+ measures, including conditional logic such as correctly excluding run-outs when calculating a bowler's wicket count.
- **Data verification**: Cross-checked key statistics (highest team score, most sixes in a match, highest individual score) against raw data before including them.
- **Interactivity**: Drill-through player profile page, synced filters, and custom tooltips across all report pages.

## Tools Used

Python (Pandas, Matplotlib, Seaborn) · Google Colab · Power BI · DAX

## Repository Structure

```
├── data/                # Cleaned datasets (CSV)
├── notebook/             # Python EDA notebook (Google Colab)
├── powerbi/               # Power BI report file (.pbix)
├── images/                 # Dashboard page screenshots
└── README.md
```

## Contact

Feel free to reach out if you have questions, feedback, or suggestions.
