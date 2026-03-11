# European Soccer Database Analysis

Statistical analysis of 25,979 matches across 11 European leagues (2008-2016) examining home advantage, team performance patterns, and betting market efficiency.

## Key Results

| Metric | Value |
|--------|-------|
| Total Matches Analyzed | 25,979 |
| Leagues Covered | 11 |
| Overall Home Win Rate | 45.9% |
| Home Advantage Range | 41.67% (Scotland) - 48.85% (Spain) |
| Average Goals per Match | 2.6 - 2.8 |
| Top Team Win Rates | 65-72% |
| Betting Market Calibration | High (implied prob ≈ actual outcomes) |
| Predictive Model Accuracy | 53-54% |

## Highlights

**Home advantage is league-dependent, not universal.** Spain shows 48.85% home win rate while Scotland sits at 41.67% — a 7.2 percentage point gap that matters for performance benchmarking and betting strategies. Elite clubs maintain high win rates regardless of venue, while mid-table teams depend heavily on crowd support.

**Scoring patterns remained structurally stable across eight seasons.** Goals per match cluster tightly at 2.6-2.8 across all leagues with no temporal drift, confirming that tactical evolution during 2008-2016 did not fundamentally alter offensive output. Home teams consistently score ≈1.5 goals vs ≈1.1 for away teams.

**Elite teams form a distinct performance tier.** The top 20 teams achieve 65-72% win rates, far above league averages. Barcelona, Real Madrid, and Bayern Munich dominate both home and away, while other teams show extreme venue-dependent performance splits (30+ percentage point gaps).

**Betting markets efficiently incorporate available information.** Calibration analysis reveals that when bookmakers price a team at 60% to win, those teams win approximately 60% of the time. Simple models using odds as features achieve 53-54% accuracy but fail to generate consistent value — historical data alone is insufficient to beat the market.

**Predictive edge requires non-priced signals.** Models trained solely on betting odds confirm that markets have already incorporated team quality, home advantage, and historical performance. Generating alpha requires access to game-specific factors not yet reflected in odds: lineup changes, injuries, motivation, or weather conditions.

## Context

This analysis uses the European Soccer Database, a comprehensive SQLite dataset covering professional football matches from 11 leagues across eight seasons. The database combines match results (home/away goals, dates, stages) with betting market data (multiple bookmaker odds) and player attributes (FIFA ratings, physical characteristics, work rates). Data was originally compiled for sports analytics and predictive modeling research.

## Objectives

1. Quantify home advantage across European leagues and identify structural patterns
2. Analyze team performance consistency and competitive balance
3. Examine player quality distribution and evolution over time
4. Assess betting market efficiency through calibration analysis
5. Build baseline predictive models to test market informativeness

## Notebook Structure

| Section | Description |
|---------|-------------|
| Data Exploration | Database schema overview, match coverage by league and season |
| Match Outcomes | Win/draw/loss distribution analysis, home advantage quantification |
| Goals Analysis | Scoring patterns, home vs away goal differentials |
| Temporal Evolution | Eight-season trends in outcomes and scoring rates |
| Team Performance | Top team identification, win rate rankings, home/away splits |
| Player Attributes | Rating distributions, quality evolution, top player identification |
| Betting Odds | Market calibration analysis, implied probability validation |
| Predictive Modeling | Logistic regression and random forest baseline models |
| Conclusion | Key findings synthesis and stakeholder recommendations |

## Stack

Python 3.8 · pandas · NumPy · SQLite3 · Matplotlib · Seaborn · scikit-learn · SciPy

## How to Run

1. Open [Kaggle Notebooks](https://www.kaggle.com/code) and upload `european-soccer-analysis-final.ipynb`
2. Attach the dataset: Search for "European Soccer Database" by Hugo Mathien and add to notebook
3. Verify input path is `/kaggle/input/datasets/hugomathien/soccer/database.sqlite`
4. Run all cells (execution time: ~2-3 minutes)

## Data Source

**Dataset:** [European Soccer Database](https://www.kaggle.com/datasets/hugomathien/soccer)  
**Author:** Hugo Mathien  
**Coverage:** 25,979 matches, 11 leagues, 2008-2016 seasons  
**Format:** SQLite database with 8 tables (Match, Team, Player, Player_Attributes, Team_Attributes, Country, League)
