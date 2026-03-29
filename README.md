AirBnB Melbourne — Predictive Analytics
Tool: RapidMiner | Course: MIS272 Predictive Analytics | Institution: Deakin University | Year: 2023

Project Overview
This project analyses AirBnB property listings across Melbourne to help the platform make data-driven decisions that improve host performance and guest satisfaction. Three analytical tasks were completed across the full data science workflow — from data preparation and exploratory analysis through to predictive modelling, clustering, and business recommendations.

Business Problem
AirBnB sought to better understand their domestic tourism offerings in Melbourne by addressing three core questions:

Does property distance from the Melbourne CBD meaningfully impact review scores?
Can review score ratings be predicted using property attributes?
Which properties with low review scores are most concerning and require intervention?


Dataset

Source: AirBnB Melbourne listings dataset
Key attributes: review_scores_rating, review_scores_cleanliness, review_scores_location, review_scores_checkin, review_scores_communication, review_scores_value, price_per_night, accommodates, bedrooms, latitude, longitude


Tasks & Methodology
Task A — Correlation Analysis (Distance vs Review Score)

Generated a new attribute Distance_to_CBD using latitude and longitude via the Haversine formula
Conducted regression analysis to assess the relationship between distance from Melbourne CBD and review score rating
Result: R² of 0.048 — a weak linear relationship, indicating that distance from the CBD has minimal impact on review scores

Task B — Predictive Modelling (Review Score Estimation)

Built a linear regression model to estimate review score ratings using statistically significant predictors
Applied cross-validation to reduce overfitting and improve model generalisability
Used a correlation matrix to detect multicollinearity — identified a strong correlation (0.847) between accommodates and bedrooms
Resolved multicollinearity by removing bedrooms, confirming all remaining predictors had p-values < 0.05
Key finding: Cleanliness (review_scores_cleanliness) was the strongest positive predictor of overall review score rating

Task C — Clustering (Identifying Underperforming Properties)

Filtered dataset to properties with review scores below 10 across all six review score attributes
Applied normalisation to ensure attributes on different scales were comparable
Used k-Means clustering (k=3) to segment underperforming properties
Evaluated clusters using Davies-Bouldin index (0.729) confirming well-separated clusters
Result: cluster_1 (2 properties) was identified as most concerning with the highest average centroid distance of 0.356, indicating the greatest deviation from the cluster centre


Key Results
TaskMethodKey OutcomeTask ARegressionR² = 0.048 — distance has weak effect on review scoresTask BLinear Regression + Cross ValidationCleanliness and location are strongest review predictorsTask CK-Means Clustering (k=3)cluster_1 identified as highest concern (centroid distance: 0.356)

Business Recommendations

Hosts should prioritise cleanliness improvements as the single highest-impact driver of review score ratings
AirBnB should not rely on proximity to Melbourne CBD as a quality indicator — low-scoring properties exist across all distances
Flagged properties in cluster_1 require direct outreach and support — their review scores deviate most significantly from the standard
Properties with strong review scores (score = 10) should be studied to identify best practices that can be shared across the platform


Tools & Techniques

RapidMiner Studio
Linear Regression
Cross Validation
K-Means Clustering
Correlation Matrix (multicollinearity detection)
Geospatial attribute generation (Haversine formula)
Data normalisation and filtering


Files in This Repository
FileDescriptionpredictive-analytics-melbourne.pdfFull assignment report including all process models, figures, and results

Author
Dion Weerapperuma
Bachelor of Business Analytics — Deakin University
[LinkedIn](http://www.linkedin.com/in/dion-weerapperuma-21a22b254) | [GitHub](https://github.com/dion-weerapperuma)
