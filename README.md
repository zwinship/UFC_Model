UFC Betting Model
Visit the UFC Betting Model Dashboard
A comprehensive machine learning model for predicting UFC fight outcomes based on fighting styles and key statistics.
Overview
This project implements a multi-stage machine learning approach to predict UFC fight outcomes:

Fighting Style Classification: Categorizes fighters into distinct fighting styles based on their historical performance metrics
Style Matchup Prediction: Analyzes how different fighting styles perform against each other
Fight Outcome Prediction: Combines fighting style matchups with additional fighter statistics to generate win probability predictions

All data used in this model is sourced from UFCStats.com, providing official UFC fight statistics.
How It Works
Stage 1: Fighting Style Classification
The model analyzes historical fighter data to identify and classify distinct fighting styles (e.g., striker, grappler, well-rounded, etc.). This classification is based on key performance indicators such as:

Strike accuracy
Takedown success rate
Submission attempts
Ground control time
And more...

Stage 2: Style Matchup Analysis
Using historical fight data, the model learns which fighting styles tend to perform better against others (e.g., wrestlers vs. strikers, grapplers vs. counter-strikers).
Stage 3: Fight Prediction
The final prediction model combines:

Fighting style matchup analysis
Fighter-specific statistics
Recent performance trends
Additional fight context

to generate win probability predictions for upcoming UFC bouts.
Performance Tracking
The repository includes code that tracks model predictions against actual fight outcomes to evaluate:

Prediction accuracy
Return on investment for betting scenarios
Performance across different weight classes and fight types

Results Dashboard
All model predictions, historical performance metrics, and betting returns can be found on our live dashboard:
UFC Betting Model Results Dashboard
The dashboard includes:

Current prediction accuracy statistics
Historical betting returns
Analysis of model performance by weight class and fighting style
Upcoming fight predictions

Contributors

Zach Winship - Primary developer

Data Sources

UFCStats.com
Kaggle user ustice - Career statistics compilation

AI Contribution Disclaimer
Most of the data scraping and website creation for this project was assisted by AI tools including:

ChatGPT
Meta AI
Claude

License
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
