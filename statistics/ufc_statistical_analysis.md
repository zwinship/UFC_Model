# UFC Betting Model ROI Analysis

*Analysis Date: 2025-03-12 02:59:23*

## Overview
This analysis evaluates the Return on Investment (ROI) performance of our UFC betting model. The ROI metric represents the profit or loss as a percentage of the initial stake, where positive values indicate profitable bets (e.g., a value of 0.20 or 20% means a 20% profit on investment).

## Basic Statistics on Model ROI

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Count | 6 | Number of bets analyzed |
| Mean | -1.5000 | Average ROI (>0 means profitable) |
| Median | -1.0000 | Middle ROI value (less affected by outliers) |
| Standard Deviation | 0.8367 | Measure of ROI volatility |
| Minimum | -3.0000 | Lowest ROI (biggest loss) |
| Maximum | -1.0000 | Highest ROI (biggest win) |
| Range | 2.0000 | Difference between highest and lowest ROI |
| Interquartile Range | 0.7500 | Range of the middle 50% of ROI values |

## Statistical Significance Testing

### One-sample t-test
- **Null Hypothesis (H₀)**: The model's average ROI is equal to 0 (break-even)
- **Alternative Hypothesis (H₁)**: The model's average ROI is greater than 0 (profitable)

### Results
- **t-statistic**: -4.3916
- **p-value (one-sided)**: 0.9965
- **Conclusion**: Fail to reject H₀

### What This Means
**The results are inconclusive or indicate the model is not profitable.** We don't have enough statistical evidence to conclude that the model performs better than the break-even point. The observed ROI might be due to random chance rather than genuine predictive power, or it might indicate a losing strategy.

## ROI Distribution
The mean ROI of -1.5000 indicates that on average, each 1 unit bet returns -0.50 units, for a loss of 1.50 units. For comparison, a random selection strategy would be expected to return approximately $0.96 per $1 bet in the long run (due to bookmaker margins).

## Dataset Information
This analysis was performed on the UFC Model betting results dataset, which includes 6 bets. The model's predictions were compared against actual fight outcomes to evaluate ROI performance.

## Conclusion
The current data shows that this betting model is generating losses. We should revisit the model's approach and parameters before continuing further.