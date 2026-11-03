# ADULT INCOME DATA ANALYSIS
## Exploratory Data Analysis (EDA) Project Report

### 1. Abstract

The Adult Income Data Analysis project focuses on exploring and understanding the relationship between demographic, educational, employment, and financial attributes and individual income levels.

The project uses the Adult Income Dataset, which contains information about individuals, including age, workclass, education, marital status, occupation, relationship, race, sex, capital gain, capital loss, working hours per week, and native country.

The primary objective is to analyze the dataset using Python, perform data preparation, examine distributions, identify patterns, and understand the factors associated with income levels.

The analysis combines the original training and testing datasets into a single dataset containing 48,842 records. Exploratory data analysis is performed using Pandas, NumPy, Matplotlib, and Seaborn.

The project also creates additional analytical features, such as high-income classification, working-hour groups, and net capital, to support further analysis.

### 2. Introduction

Income is an important socioeconomic indicator that is influenced by several factors, including education, occupation, employment conditions, age, and working hours.

Understanding the relationship between these factors and income can provide valuable insights into economic and social patterns.

This project uses the Adult Income Dataset to investigate the characteristics of individuals earning more than $50,000 annually compared with those earning $50,000 or less.

The project emphasizes data cleaning, feature engineering, statistical analysis, and visualization to extract meaningful information from the dataset.

### 3. Problem Statement

The project aims to explore the relationship between individual characteristics and annual income.

The main problem is to identify patterns and differences in income distribution based on demographic and employment-related attributes.

The analysis focuses on understanding:

- How education levels relate to income.
- How occupation and workclass relate to income.
- How age varies across income categories.
- Whether working hours show meaningful patterns.
- How capital gains and capital losses are distributed.
- How demographic characteristics are distributed across income groups.

### 4. Objectives

The major objectives of the project are:

1. To collect and load the Adult Income Dataset.
2. To combine the training and testing datasets.
3. To inspect the structure and characteristics of the data.
4. To identify missing values and understand data quality.
5. To prepare the dataset for analysis.
6. To perform exploratory data analysis.
7. To analyze numerical and categorical variables.
8. To create additional features for better analysis.
9. To investigate relationships between different variables and income.
10. To create meaningful visualizations.
11. To summarize the findings and identify limitations.

### 5. Dataset Description

The project uses the Adult Income Dataset obtained from the UCI Machine Learning Repository.

The dataset is loaded from the following sources:

- Training dataset: adult.data
- Testing dataset: adult.test

The training dataset contains 32,561 records, while the testing dataset contains 16,281 records.

After combining both datasets, the final dataset contains:

- Total records: 48,842
- Total original attributes: 15
- Additional source-identification column: 1

#### 5.1 Dataset Attributes

| Attribute | Description |
|---|---|
| age | Age of an individual |
| workclass | Type of employment |
| fnlwgt | Final sampling weight |
| education | Educational qualification |
| education_num | Numerical representation of education |
| marital_status | Marital status |
| occupation | Type of occupation |
| relationship | Relationship category |
| race | Race category |
| sex | Gender |
| capital_gain | Capital gain amount |
| capital_loss | Capital loss amount |
| hours_per_week | Weekly working hours |
| native_country | Country of origin |
| income | Annual income category |

The target variable is income, which contains two categories:

- <=50K
- >50K

### 6. Tools and Technologies Used

The following technologies are used in the project:

**Python:** Main programming language.

**Jupyter Notebook:** Environment used to execute code and document the analysis.

**Pandas:** Data loading, cleaning, manipulation, and statistical analysis.

**NumPy:** Numerical operations and feature engineering.

**Matplotlib:** Data visualization.

**Seaborn:** Statistical visualization and graphical analysis.

**Requests and BeautifulSoup:** Imported in the notebook, although their specific use in the completed analysis requires verification.

### 7. Data Collection and Loading

The training and testing datasets are imported directly from the UCI Machine Learning Repository.

Pandas' `read_csv()` function is used to load both datasets.

Since the datasets do not initially contain column names, the 15 attribute names are assigned manually.

A new column called `source_split` is added to identify whether each record originated from the training or testing dataset.

Both datasets are combined using Pandas' `concat()` function.

The resulting dataset contains 48,842 records and 16 columns.

The combined raw dataset is also exported as a CSV file for further use.

### 8. Data Preparation and Feature Engineering

Data preparation is an important step in ensuring that the dataset is suitable for analysis.

The project introduces additional features to improve the analytical capabilities of the dataset.

#### 8.1 Income Classification

A binary target variable named `high_income` is created.

The classification is:

- 0 represents income of $50,000 or less.
- 1 represents income greater than $50,000.

The notebook initially produced an incorrect classification because the income values needed to be stripped of surrounding whitespace before comparison.

The income column was subsequently cleaned using the string `strip()` operation, and the binary target was recreated correctly.

The final distribution is:

| Income category | Records | Percentage |
|---|---:|---:|
| <=50K | 37,155 | 76.07% |
| >50K | 11,687 | 23.93% |
| Total | 48,842 | 100% |

This correction is important because the earlier version of the binary variable contained only zeros and produced invalid analytical results.

#### 8.2 Working Hours Group

A new feature named `hours_group` is created to categorize individuals according to weekly working hours.

The categories include:

- Less than 20 hours
- 20–34 hours
- 35–39 hours
- 40 hours
- 41–49 hours
- 50 hours or more

This feature makes it easier to analyze working patterns.

#### 8.3 Net Capital

A new feature named `net_capital` is introduced to represent the difference between capital gain and capital loss.

It is calculated as:

Net Capital = Capital Gain − Capital Loss

This feature provides an additional way to examine the financial characteristics of individuals.

### 9. Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand the structure, distribution, and relationships within the dataset.

Both numerical and categorical variables are examined using statistical summaries and graphical representations.

#### 9.1 Education Distribution

The education variable is analyzed to understand the educational qualifications represented in the dataset.

A count plot is created to visualize the number of individuals in each education category.

The analysis also includes a comparison between education levels and income categories.

The objective is to investigate whether educational qualifications show differences in income distribution.

#### 9.2 Education vs Income

A count plot is used to compare the number of individuals earning <=50K and >50K across education categories.

A percentage-based cross-tabulation is also created to compare income distribution within each education category.

This analysis helps examine the relationship between educational qualifications and income.

#### 9.3 Occupation vs Income

Occupation is analyzed to investigate income distribution across different job categories.

A horizontal percentage-based bar chart is generated to compare the proportion of income categories within occupations.

This analysis helps identify differences in income distribution across employment types.

#### 9.4 Workclass vs Income

The workclass variable is examined to understand the relationship between employment categories and income.

Count plots and percentage-based bar charts are created.

These visualizations allow comparisons between workclass categories and the two income groups.

#### 9.5 Age Distribution

A histogram with a Kernel Density Estimate (KDE) is created to understand the distribution of age.

The statistical analysis shows:

- Mean age: 38.64 years
- Median age: 37 years
- Minimum age: 17 years
- Maximum age: 90 years
- Standard deviation: 13.71 years

The dataset includes individuals from different age groups, allowing the examination of age-related income patterns.

#### 9.6 Age vs Income

A box plot is created to compare age distributions across income categories.

The objective is to examine whether age distributions differ between individuals earning <=50K and those earning >50K.

#### 9.7 Sex vs Income

The relationship between sex and income is examined using count plots and percentage-based visualizations.

The analysis compares income-category distributions across the sex variable.

#### 9.8 Working Hours vs Income

Weekly working hours are examined using box plots and histograms.

The analysis includes:

- Distribution of weekly working hours.
- Comparison of working hours across income categories.
- Distribution of working hours using the engineered hours_group feature.

The overall statistical results are:

- Mean working hours: 40.42 hours per week.
- Median working hours: 40 hours.
- Minimum working hours: 1 hour.
- Maximum working hours: 99 hours.
- Standard deviation: 12.39 hours.

#### 9.9 Capital Gain and Capital Loss Analysis

Capital gain, capital loss, and net capital are examined to understand the financial distribution of the dataset.

The overall numerical results are:

- Average capital gain: 1,079.07.
- Median capital gain: 0.
- Average capital loss: 87.50.
- Median capital loss: 0.
- Average net capital: 991.57.
- Median net capital: 0.

The results indicate that the median values of capital gain, capital loss, and net capital are all zero.

This suggests that these variables contain many observations with zero values.

#### 9.10 Correlation Analysis

A correlation matrix is calculated for numerical variables.

A heatmap is created to visualize the correlations between:

- Age
- Final weight
- Education number
- Capital gain
- Capital loss
- Working hours per week
- Net capital

The notebook also attempts to calculate the correlation between numerical features and the high_income variable.

However, the initial binary target variable was incorrectly generated, resulting in invalid correlation values.

The target variable was corrected later in the notebook. The correlation analysis should therefore be rerun after the correction before reporting any final income-related correlation values.

### 10. Statistical Summary

The notebook produces descriptive statistics for the numerical variables.

| Variable | Mean | Median | Standard Deviation |
|---|---:|---:|---:|
| Age | 38.64 | 37.00 | 13.71 |
| fnlwgt | 189,664.13 | 178,144.50 | 105,604.03 |
| Education number | 10.08 | 10.00 | 2.57 |
| Capital gain | 1,079.07 | 0.00 | 7,452.02 |
| Capital loss | 87.50 | 0.00 | 403.00 |
| Hours per week | 40.42 | 40.00 | 12.39 |
| Net capital | 991.57 | 0.00 | 7,475.55 |

These statistics provide an overview of the central tendency and variability of the numerical variables.

### 11. Outlier Detection

The Interquartile Range (IQR) method is used to identify potential outliers.

The calculation follows:

IQR = Q3 − Q1

Lower Bound = Q1 − 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR

The notebook identifies the following potential outlier counts:

| Variable | Potential outliers |
|---|---:|
| Age | 216 |
| fnlwgt | 1,453 |
| Education number | 1,794 |
| Capital gain | 4,035 |
| Capital loss | 2,282 |
| Hours per week | 13,496 |
| Net capital | 6,317 |

These observations are identified using the IQR method.

Potential outliers are not necessarily incorrect values. They may represent genuine differences between individuals.

### 12. Data Visualization

The project generates multiple visualizations to support the exploratory analysis.

The charts include:

1. Income distribution.
2. Education distribution.
3. Education level vs income.
4. Income percentage by education.
5. Occupation vs income.
6. Workclass vs income.
7. Age distribution.
8. Age distribution by income.
9. Sex vs income.
10. Working hours vs income.
11. Working hours distribution by income.
12. Correlation heatmap.
13. Working hours group vs income.
14. Net capital vs income.

These visualizations help communicate the distribution of the dataset and the relationships between different attributes.

### 13. Key Findings

Based on the successfully inspected notebook outputs, the following findings can be reported:

1. The combined dataset contains 48,842 records.
2. The income category <=50K contains 37,155 records, representing approximately 76.07% of the dataset.
3. The income category >50K contains 11,687 records, representing approximately 23.93% of the dataset.
4. The average age of individuals is approximately 38.64 years.
5. The median age is 37 years.
6. Individuals work an average of approximately 40.42 hours per week.
7. The median working time is 40 hours per week.
8. Capital gain and capital loss have median values of zero.
9. The IQR method identifies potential outliers in several numerical variables.
10. Additional features such as high_income, hours_group, and net_capital are introduced to support further analysis.

The notebook also demonstrates the importance of correctly preparing the target variable before performing statistical analysis.

### 14. Limitations of the Project

The following limitations should be considered:

- The dataset contains more observations in the <=50K category than in the >50K category.
- Some numerical features contain many zero values.
- Several variables have potential outliers.
- The analysis is based on the available attributes and does not establish causation.
- Some income-related statistical outputs were generated before correcting the binary target variable and need to be recalculated.
- The notebook contains exploratory analysis, but a completed and evaluated machine learning model is not established by the inspected results.
- The visual analysis alone cannot establish whether one variable directly causes higher income.

### 15. Conclusion

The Adult Income Data Analysis project provides an exploratory understanding of the relationship between demographic, educational, employment, and financial attributes and income categories.

The project successfully combines the original training and testing datasets into a dataset containing 48,842 observations.

Data preparation and feature engineering are used to create additional variables, including binary income classification, working-hour groups, and net capital.

The exploratory analysis examines age, education, occupation, workclass, sex, working hours, capital gain, and capital loss through statistical summaries and visualizations.

The income distribution indicates that approximately 76.07% of individuals belong to the <=50K category, while approximately 23.93% belong to the >50K category.

The project also highlights the importance of correct data cleaning and target-variable preparation, as an incorrect target encoding can affect statistical summaries and analytical conclusions.

Overall, the project demonstrates the use of Python-based data analysis techniques to explore a real-world socioeconomic dataset and extract meaningful descriptive insights.

### 16. Future Scope

The project can be extended in the following ways:

1. Perform more detailed categorical and numerical analysis.
2. Recalculate all income-related statistics after correcting the target variable.
3. Apply appropriate encoding techniques to categorical variables.
4. Perform feature selection.
5. Train machine learning classification algorithms.
6. Compare Logistic Regression, Decision Tree, Random Forest, and other suitable models.
7. Evaluate models using accuracy, precision, recall, F1-score, and ROC-AUC.
8. Address class imbalance where appropriate.
9. Build an interactive dashboard to present the results.
10. Investigate model fairness across demographic groups.

### 17. References

1. UCI Machine Learning Repository – Adult Dataset.
2. Python Documentation.
3. Pandas Documentation.
4. NumPy Documentation.
5. Matplotlib Documentation.
6. Seaborn Documentation.

**Project Title:** Adult Income Data Analysis

**Project Type:** Data Analysis / Exploratory Data Analysis

**Programming Language:** Python

**Development Environment:** Jupyter Notebook