# MSCS_634_ProjectDeliverable_1
Deliverable 1 for Advanced Big Data and Data Mining Project

## Summary
After cleaning and exploring the student performance dataset, several clear patterns emerged that will guide the next modeling stages. Below are the most relevant insights and how they connect to regression, classification, clustering, and association rule mining.

1. Grade progression is highly predictive (Regression)
- The correlation between G1, G2, and G3 is very strong (above 0.85).
- Linear regression using G1 and G2 can accurately estimate G3, making them primary predictors.
- Adding variables like studytime, failures, and absences can slightly refine accuracy and explain variance beyond raw grades.

2. Academic risk factors are clear (Classification)
- Features such as failures, studytime, and absences show distinct separation between high and low achievers.
- Students with more than one failure or above-average absences have significantly lower G3 values.
- A classification model (Decision Tree or Logistic Regression) can be built to predict pass/fail or high/low performance categories.

3. Behavioral and lifestyle clusters (Clustering)
- Using variables like goout, freetime, Dalc, Walc, and studytime, students naturally form 3–4 clusters:
- Focused/Academic — high studytime, low social activity.
- Balanced — moderate across all behaviors.
- Social/At-risk — low studytime, high social/alcohol levels.
- These clusters can be compared with average grades to identify which behavioral patterns lead to better outcomes.

4. Socioeconomic and parental influence (Regression + Association Rules)
- Parental education (Medu, Fedu) correlates modestly with student performance (r ≈ 0.25).
- Association rules can uncover combinations like {Medu ≥ 3, studytime ≥ 2} → G3 ≥ 15, showing joint effects of family and study factors.
- Such rules help interpret socio-educational impacts beyond numeric models.

5. Engagement and attendance patterns (All models)
- Absences and alcohol consumption (Dalc/Walc) are inversely related to performance.
- They provide early-warning indicators useful in both regression (negative coefficients) and classification (predicting low grades).
- Clustering and association rule mining can highlight recurring risky combinations, such as absences ≥ 10, Walc ≥ 3 → low performance

## Data Cleaning and Exploration
- During the data preparation phase, my main goal was to make the dataset consistent, structured, and ready for analysis. I started by loading the student performance dataset and carefully inspecting its structure, data types, and overall completeness. From there, I performed the following steps:

### Duplicate Removal:
- I began by checking for and removing duplicate rows to ensure that each record represented a unique student. Althoug there were no duplicates, it was important to verify and clean this before any exploration

### Outlier Detection and Cleaning:
- Using the Interquartile Range (IQR) method, I identified extreme outliers across numeric features such as failures, absences, and studytime.
- Instead of deleting them, I applied clipping to keep all records while limiting the effect of extreme values on later models.

### Exploratory Data Analysis (EDA):
- Once cleaned, I visualized distributions with histograms and boxplots, then examined relationships through correlation heatmaps and scatter plots.
- This helped me uncover trends — for example, the strong link between earlier grades (G1, G2) and the final grade (G3), as well as behavioral influences like absences and study time.

## Challenges

### Handling outliers
- The main challenge really was to handle outliers. Removing all outliers would have reduced the dataset size too much. To avoid this, I clipped extreme values to stay within realistic ranges while preserving overall data balance.
