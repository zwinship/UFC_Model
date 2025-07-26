# UFC Betting Model Return to Player Analysis

*Analysis Date: 2025-07-26 18:03:00*

## Overview
This analysis evaluates the Return to Player (RTP) performance of our UFC betting model. The RTP metric represents the percentage of wagered money returned to bettors, where values greater than 96% indicate profitable bets after accounting for typical sportsbook margins (e.g., a value of 120% means a 20% profit on investment).

## Basic Statistics on Model RTP

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Count | 81 | Number of bets analyzed |
| Mean | 1.0953 | Average RTP multiple (>0.96 means profitable) |
| Median | 1.2000 | Middle RTP value (less affected by outliers) |
| Standard Deviation | 1.1655 | Measure of RTP volatility |
| Minimum | 0.0000 | Lowest RTP (biggest loss) |
| Maximum | 6.0000 | Highest RTP (biggest win) |
| Range | 6.0000 | Difference between highest and lowest RTP |
| Interquartile Range | 1.5710 | Range of the middle 50% of RTP values |

## Statistical Significance Testing

### One-sample t-test
- **Null Hypothesis (H₀)**: The model's average RTP is equal to 0.96 (break-even after sportsbook margin)
- **Alternative Hypothesis (H₁)**: The model's average RTP is greater than 0.96 (profitable after sportsbook margin)

### Results
- **t-statistic**: 1.0450
- **p-value (one-sided)**: 0.1496
- **Conclusion**: Fail to reject H₀

### What This Means
**The results are inconclusive.** While the model may show some profitability, we don't have enough statistical evidence to conclude that it performs better than the 96% threshold needed to overcome typical bookmaker margins. The observed RTP might be due to random chance rather than genuine predictive power.

## RTP Distribution
The mean RTP of 1.0953x indicates that on average, each 1 unit bet returns 1.10 units. For comparison, a random selection strategy would be expected to return approximately $0.96 per $1 bet in the long run (due to bookmaker margins).

## Dataset Information
This analysis was performed on the UFC Model betting results dataset, which includes 81 bets. The model's predictions were compared against actual fight outcomes to evaluate RTP performance.

## Conclusion
While showing promise, we need more data to determine if this betting model truly outperforms bookmaker odds and random selection in terms of Return to Player.