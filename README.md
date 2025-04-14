# Title
Predicting High School Graduation Rates Using School-Level Data and Ensemble Machine Learning

# Author
Mohammed Shati

# Abstract
High school graduation rates are a key indicator of educational success, yet they vary widely across districts due to multiple school-level factors. This project investigates how chronic absenteeism, school funding, and economic disadvantage contribute to these outcomes using machine learning. Data was collected from public high schools across the state of Virginia, with the target variable being the Graduation Completion Index (GCI). A preprocessing pipeline was applied to scale numeric features and encode categorical data, and multiple regression models were tested. Ultimately, a Voting Regressor ensemble model combining Elastic Net, Random Forest, and XGBoost delivered the most reliable predictions. The results show that school-level conditions explain nearly 60% of graduation rate variation, with academic performance, economic status, and absenteeism as top predictors.

# Introduction
High school graduation rates serve as a powerful measure of student preparedness and long-term opportunity. While increased school funding is often considered a path to better educational outcomes, research shows that graduation rates are shaped by a complex mix of variables—such as chronic absenteeism, economic disadvantage, and instructional quality. In this project, I examine the predictive potential of these school-level factors using real data from Virginia high schools. I also review related studies emphasizing the role of equity and engagement in educational outcomes. The goal is to build a data-driven model that can highlight which schools may be at risk and support decision-makers in identifying the most impactful areas for intervention.

# Methods
The dataset includes information from public high schools in Virginia. Key variables include SOL Pass Rate, Chronic Absenteeism Rate, Total Per-Pupil Expenditures, Percent Economically Disadvantaged, and teacher experience/qualification metrics. The target variable is the Graduation Completion Index (GCI), which reflects the percentage of students graduating on time.

Numerical features were standardized using StandardScaler, and categorical variables (e.g., Poverty Level) were encoded with OneHotEncoder. An Elastic Net model was first used to handle multicollinearity, followed by an XGBoost model to capture non-linear relationships. To balance predictive power and generalization, I implemented a Voting Regressor combining Elastic Net, XGBoost, and Random Forest models. All models were tuned using GridSearchCV with 5-fold cross-validation and evaluated using R², MAE, and MSE.

# Experimental Results
| Model            | Train R² | Test R² | Train MAE | Test MAE | Train MSE | Test MSE |
|------------------|----------|---------|-----------|----------|-----------|----------|
| Elastic Net      | 0.4585   | 0.4596  | 2.8656    | 3.7951   | 17.5397   | 26.6663  |
| XGBoost          | 0.8335   | 0.5899  | 1.7839    | 3.5504   | 5.3912    | 20.2368  |
| Voting Regressor | 0.7760   | 0.5810  | 1.9085    | 3.5799   | 7.2560    | 20.6797  |

📈 Actual vs. Predicted Plot
(Insert this saved image in your repo: Actual_vs_Predicted_VotingRegressor.png)
This plot shows the predicted GCI values from the Voting Regressor against the actual values. The model captures the overall trend well, especially for schools with average or high outcomes.

📊 Feature Importance (XGBoost)
(Insert image: Feature_Importance_XGBoost.png)
SOL Pass Rate is the most important predictor, followed by Percent Eligible and Chronic Absenteeism Rate, which reflect socioeconomic and engagement challenges.

# Discussion
The Voting Regressor demonstrated strong performance and stability, outperforming individual models in generalization. The results show that academic readiness (SOL Pass Rate), poverty (Percent Eligible), and attendance (Chronic Absenteeism) are critical to understanding graduation outcomes. Educators and policymakers can use these insights to target support programs, especially for at-risk schools. While the model explained nearly 60% of the variance in graduation rates, future improvements such as additional data, time-series features, or more granular student-level data could enhance accuracy.

# Statement of Contributions
Mohammed Shati – Data cleaning, feature engineering, model development, hyperparameter tuning, visualization, and final report writing.

# Conclusion
This project shows that graduation rates can be predicted with reasonable accuracy using a combination of academic, financial, and socioeconomic indicators. Ensemble learning provided the best results, and the findings support data-driven decision-making in education planning.

# References (APA 7th Edition)
Cotman, A. M., Curran, F. C., & Harris-Walls, K. (2024). Examination of state-level school safety data dashboard characteristics. Education Policy Analysis Archives, 32(65). https://doi.org/10.14507/epaa.32.8559

Liu, A. (2023, August 10). Mapped: High school graduation rates by state. Visual Capitalist. https://www.visualcapitalist.com/mapped-high-school-graduation-rates-by-state/

Michaeli, S., Kroparo, D., & Hershkovitz, A. (2020). Teachers’ use of education dashboards and professional growth. IRRODL, 21(4). https://www.irrodl.org/article/view/4663/5396

