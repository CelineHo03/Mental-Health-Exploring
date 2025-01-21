# Mental-Health-Exploring

1. Project Background
2. Data Structure Overview
3. EDA
4. Model Evaluation
5. Recommendations

# Project Background
I have always been so fascinating about psychology field and exploring human's mind. This project is naturally thus drawn to me. The dataset is provided by a competition on Kaggle, exploring mental health using 1 target Depression based on different factors. This project thoroughly analyzes and synthesizes this data in order to uncover insights into the dataset and apply machine learning to build model predict Depression.
Insights and recommendations are provided on the following key areas. While the data is synthetic, the process is structured to highlight key patterns, model performance, and methodological rigor. Insights and scenario-based recommendations are presented across several critical areas:

**1. Feature Importance and Patterns:**
identifying the most influential factors on depression, such as work pressure, academic satisfaction, sleep duration, and financial stress.

**2. Predictive Modeling and Evaluation:**
By applying a range of machine learning models, I assessed their predictive performance using metrics like accuracy, precision, and F1 score. 

**3. Scenario Analysis and Interpretations:**
Even with synthetic data, hypothetical scenarios are explored to understand the potential impact of changes in variables—such as reduced sleep duration or increased financial stress—on depression risk.

**4. Methodological Lessons and Future Directions:**
This project outlines the lessons learned from working with synthetic data and suggests next steps, including applying these methods to real-world datasets or refining the existing approach for greater interpretability and robustness.

Through these areas, the project not only showcases technical proficiency in data analysis and machine learning but also provides a framework for understanding and addressing mental health-related questions through structured, data-driven methods.

# Data Structure & Initial Checks
The train dataset consists of 140700 entries and 19 columns. The database structures are as below:

<img width="594" alt="Screenshot 2025-01-21 at 8 23 08 AM" src="https://github.com/user-attachments/assets/7777a4ab-bbe0-4fea-baa5-f93b88759d72" />

Prior to beginning the analysis, a variety of checks were conducted for quality control and familiarization with the datasets.

**1. Duplicates and Noises:**

The dataset does not contain duplicate entries, but I did find a significant amount of noise, as many variables include unrelated or illogical values. For example, in the “City” column, some entries were labeled as “3,” which is clearly not a valid city name. To address these issues, I implemented several cleaning steps, replacing these unrelated values with NaN so that they could be appropriately handled during preprocessing.

![image](https://github.com/user-attachments/assets/42bc5855-d6f4-440a-be79-d1d01fb4c8c4)
![image](https://github.com/user-attachments/assets/46a83f3d-a834-4691-91c4-464cb18ef5cf)

The graphs compare the count of unique values in each column before and after cleaning, revealing a significant drop—approximately 30% to 50% fewer distinct values—after the process.

**2. Missing Values:**

![image](https://github.com/user-attachments/assets/57fd8231-e346-4e51-b9df-fce6d73ea9e1)

The missing-value heatmap shows that many features in the dataset contain a large amount of missing datas. Columns like Academic Pressure, Work Pressure, Study Satisfaction,and CGPA in the training set appear to have many missing entries, while others (like Name, Gender, Age, etc.) are fully populated.
Most of the models applied in this project are capable of handling categorical variables and missing values inherently. Therefore, I opted to leave these missing values as-is, relying on the models’ built-in mechanisms to manage them effectively.

# EDA

![image](https://github.com/user-attachments/assets/9515d4c7-4a4f-41b3-91cc-3046541b0827)

Observing the distribution plot, features like: "Have you ever had suicidal thoughts", " Study Satisfaction". "Work Pressure", "Study Pressure" "Financial Stress" and "Age" show significant distinction in distribution between individuals with and without depression. These features are likely strong predictors of depression in the modeling phase.

Variables like Gender, Have you ever had suicidal thoughts?, and Family History of Mental Illness reveal potential associations with depression (e.g., higher proportion of “Yes” responses among depressed individuals)

Some distributions (e.g., Name, City, or Profession) show many unique categories or noisy patterns, which might be less informative.

However, again, it's a synthetic dataset, I would not change the structure of data by too much. 

# Model Evaluation
