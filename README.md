# UFC Betting Model

## [Visit the OctaStats site](https://OctaStats.github.io)

A comprehensive machine learning model for predicting UFC fight outcomes based on fighting styles and key statistics.

## Overview

This project implements a multi-stage machine learning approach to predict UFC fight outcomes:

1. **Fighting Style Classification**: Categorizes fighters into distinct fighting styles based on their historical performance metrics
2. **Style Matchup Prediction**: Analyzes how different fighting styles perform against each other
3. **Fight Outcome Prediction**: Combines fighting style matchups with additional fighter statistics to generate win probability predictions

All data used in this model is sourced from [UFCStats.com](https://www.ufcstats.com/), providing official UFC fight statistics.

## How It Works

### Stage 1: Fighting Style Classification
The model analyzes historical fighter data to identify and classify distinct fighting styles (e.g., striker, grappler, well-rounded, etc.). This classification is based on key performance indicators such as:
- Strike accuracy
- Takedown success rate
- Submission attempts
- Ground control time
- And more...

### Stage 2: Style Matchup Analysis
Using historical fight data, the model learns which fighting styles tend to perform better against others (e.g., wrestlers vs. strikers, grapplers vs. counter-strikers).

### Stage 3: Fight Prediction
The final prediction model combines:
- Fighting style matchup analysis
- Fighter-specific statistics
- Recent performance trends
- Additional fight context

to generate win probability predictions for upcoming UFC bouts.

## How V1 runs today

V1 is fully automated from the [OctaStats_UFC_Model_V2](https://github.com/zwinship/OctaStats_UFC_Model_V2) GitHub Actions workflows, which read and write this repository:

| Step | Script (in OctaStats_UFC_Model_V2/scripts) | Writes here |
|---|---|---|
| Wednesday retrain | `v1_train_model.py` | `data/v1_model_bundle.pkl`, `data/career_styled_v1.csv` |
| Friday predictions | `v1_predict.py` | `predictions/v1_predictions_{event}.csv`, `predictions/v1_predictions_latest.csv` |
| Sunday results | `v1_scrape_results.py` | `results/v1_results_{event}.csv`, `results/all_betting_results.csv` |
| Sunday statistics | `v1_statistics.py` | `statistics/ufc_statistical_analysis.json` / `.md` |

`model_code/` holds the original Google Colab notebooks (exported to `.py`) that ran V1 manually before the automation. They are kept for reference and are not run by any workflow.

Fixes in October 2026 (made in the V2 repository's scripts):
- UFCStats now requires a real browser; the V1 predictor and results recorder were silently finding "no event" every week since May 2026. Both now load UFCStats in headless Chromium.
- Training matchups were built by pairing adjacent rows, so only ~9% paired a fighter with their actual opponent. They are now paired by fight.
- The control-time column name was wrong, so the Wrestler and BJJ styles could never be assigned. All six styles are assigned again.
- Predictions use each fighter's career averages including their most recent fight.
- Odds come from real sportsbooks (DraftKings preferred) matched by bout.
- Cancelled bouts, draws and no contests are recorded as pushes (`result` = `VOID` / `D` / `NC`) instead of losses.
- The results recorder only grades the predictions file for that exact event. It previously fell back to `v1_predictions_latest.csv`, which could belong to an older card.

## Performance Tracking

The repository includes code that tracks model predictions against actual fight outcomes to evaluate:
- Prediction accuracy
- Return on investment for betting scenarios
- Performance across different weight classes and fight types

## Results Dashboard

All model predictions, historical performance metrics, and betting returns can be found on the live site:

[OctaStats](https://OctaStats.github.io)

The dashboard includes:
- Current prediction accuracy statistics
- Historical betting returns
- Analysis of model performance by weight class and fighting style
- Upcoming fight predictions

## Contributors

- **Zach Winship** - Primary developer

## Data Sources
- [UFCStats.com](https://www.ufcstats.com/)
- Kaggle user [ustice](https://www.kaggle.com/ustice) - Career statistics compilation

## AI Contribution Disclaimer
Most of the data scraping and website creation for this project was assisted by AI tools including:
- ChatGPT
- Meta AI
- Claude

## License

MIT License

Copyright (c) 2025 Zach Winship

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
