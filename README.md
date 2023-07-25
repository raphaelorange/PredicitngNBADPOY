NBA DPOY Prediction Project:

This project aims to predict the NBA's Defensive Player of the Year (DPOY) award using machine learning algorithms and extensive data analysis.

Data Collection:

The data was sourced from a dataset available online, consisting of three .csv files named "Player Award Shares.csv", "Advanced.csv", and "Team Summaries.csv". The dataset comprises various metrics, including season, player, age, experience, team, games played, and various defensive statistics.

Data Preprocessing:

The data preprocessing phase involved cleaning the data and making it ready for analysis. This included filtering out non-DPOY awards, discarding data prior to the introduction of the DPOY award in 1983, and removing irrelevant defensive information. Data from the 2023 season was also removed, as the voter share for the award had not been announced at the time of the project. Players who were traded mid-season were excluded to maintain consistency in team-based features. Entries with NaN values were either dropped or updated with a zero vote share. A minimum threshold of 1500 minutes played in a season was set to eliminate class bias.

Feature Engineering:

Two new features were engineered for the analysis. 'W/L_percent' represented the win-loss ratio of a player's team in a season. 'd_rtg_diff' signified the difference between a team's defensive rating and the average team defensive rating for that season, accounting for varying game paces and average defensive ratings across seasons.

Data Splitting:

The data was split based on seasons. Four randomly chosen seasons (2020, 1990, 2009, 2006) were used for testing, aiming to cover different eras of the NBA.

Model Tuning:

Four models (SVM, Random Forest, XGBoost, and MLP Regressor) with default parameters were initially run for the analysis. Based on R^2, MAE, and MSE metrics, XGBoost was identified as the most accurate model. Bayesian Optimization was applied to fine-tune its parameters, resulting in the best parameters as learning_rate = 0.1929, max_depth =7, and subsample = 0.982.

Performance Evaluation:

While XGBoost had the best R-Squared value (.4186) among all the models, it was still not very accurate in prediction. Its performance was further evaluated using precision, recall, F1-Score, ROC curve, and residuals, with results indicating a significant level of discrimination towards different parameters.

This project illustrates the application of various data analysis techniques and machine learning models to predict the NBA DPOY award. However, further tuning and testing with different models may be required to improve prediction accuracy.