Predicting High School Graduation Rates Using Ensemble Machine Learning

Author

Mohammed Shati

Abstract

High school graduation rates are key indicators of student success, yet they vary significantly across schools. This project investigates how school-level factors—such as chronic absenteeism, per-pupil expenditures, and economic disadvantage—can be used to predict graduation rates using machine learning. The dataset includes public high school data from Virginia, and the target variable is the Graduation Completion Index (GCI). After preprocessing and model experimentation, the Voting Regressor ensemble model (combining Elastic Net, XGBoost, and Random Forest) was selected for its strong performance and generalization. The final model achieved an R² of ~0.58 on the test set. This project demonstrates the utility of ensemble learning in identifying key educational predictors and generating reliable forecasts of student outcomes.

Introduction

Graduation rates reflect both academic achievement and broader systemic challenges within school districts. Factors such as absenteeism, resource allocation, and poverty levels are well-documented predictors of student success. While increased funding is often expected to improve outcomes, the relationship between school-level factors and graduation rates is complex. This project explores whether a data-driven approach can predict graduation outcomes by analyzing publicly available data from Virginia high schools. Related research has used regression and decision tree models to assess educational performance; this project extends that work by using ensemble learning to improve prediction stability and interpretability.

Methods

The dataset contains school-level information including SOL Pass Rate, Chronic Absenteeism Rate, Total Per-Pupil Expenditures, Percent Economically Disadvantaged, and teacher experience indicators. The target variable is the Graduation Completion Index (GCI).

Preprocessing involved standardizing numerical features using StandardScaler and encoding categorical variables like Poverty Level using OneHotEncoder. An initial Elastic Net regression model was used to address multicollinearity and provide baseline performance. This was followed by an XGBoost model, which improved predictive accuracy but displayed some overfitting. To balance performance and generalizability, a Voting Regressor ensemble was constructed using Elastic Net, XGBoost, and Random Forest. Hyperparameters for each model were tuned using GridSearchCV with 5-fold cross-validation. Evaluation metrics included R², Mean Absolute Error (MAE), and Mean Squared Error (MSE).

Experimental Results (Evaluation)

The Voting Regressor ensemble achieved the highest overall performance:

Model

Train R²

Test R²

Train MAE

Test MAE

Train MSE

Test MSE

Elastic Net

0.4585

0.4596

2.8656

3.7951

17.5397

26.6663

XGBoost

0.8335

0.5899

1.7839

3.5504

5.3912

20.2368

Voting Regressor

0.776

0.581

1.9085

3.5799

7.256

20.6797

Actual vs. Predicted Values (Voting Regressor):



Feature Importance:



The ensemble model consistently captured trends, especially for schools with average or higher graduation rates.

Discussion

These results highlight the predictive value of key school-level factors. The SOL Pass Rate emerged as the most important feature, reinforcing the role of academic achievement in graduation outcomes. Economic disadvantage and chronic absenteeism also contributed significantly, reflecting broader socioeconomic and engagement-related challenges. By combining multiple modeling approaches, the Voting Regressor reduced model variance and delivered the most balanced performance. This model can help educational leaders identify high-risk schools and prioritize interventions. Future work could improve accuracy by including longitudinal data, more granular student-level metrics, or additional contextual variables.

Statement of Contributions

Mohammed Shati: Data preprocessing, feature engineering, model development (Elastic Net, XGBoost, Voting Regressor), evaluation, visualization, and documentation.

Conclusion

This project shows that graduation outcomes can be reasonably predicted using machine learning and school-level indicators. Ensemble learning outperformed individual models, explaining nearly 60% of the variation in graduation rates. These findings provide insight into the systemic factors shaping student success and offer a foundation for future data-informed educational strategies.

References

Cotman, A. M., Curran, F. C., & Harris-Walls, K. (2024). Examination of state-level school safety data dashboard characteristics. Education Policy Analysis Archives, 32(65). https://doi.org/10.14507/epaa.32.8559

Liu, A. (2023, August 10). Mapped: High school graduation rates by state. Visual Capitalist. https://www.visualcapitalist.com/mapped-high-school-graduation-rates-by-state/

Michaeli, S., Kroparo, D., & Hershkovitz, A. (2020). Teachers’ use of education dashboards and professional growth. International Review of Research in Open and Distributed Learning, 21(4). https://www.irrodl.org/article/view/4663/5396


