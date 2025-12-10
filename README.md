# team-project
# Data-Driven Exploration of Survival Patterns on the Titanic

**Fall 2025 Data Science Project**  
**Johann Kuruvilla & Raghavendra Pavan Sunkara**

---

## Contributions

**Johann Kuruvilla**  
Johann was primarily responsible for acquiring and preparing the Titanic Passenger and Crew dataset. He led the data cleaning and preprocessing process, including handling missing or inconsistent values and standardizing key variables such as gender, class, and fare. Johann conducted exploratory data analysis to examine patterns in survival outcomes, including relationships with gender, class, and fare, using statistical tests, and created visualizations to highlight these trends. He also interpreted the results, explaining how differences in demographics and economic status affected survival odds. Finally, he helped compile and format the final report and tutorial, integrating all sections into a cohesive document.

**Raghavendra Pavan Sunkara**  
Pavan worked on machine learning algorithm design and development, as well as training and testing the model, analyzing results, and visualizing insights. He selected logistic regression to determine how each feature impacted a passenger's odds of survival. He trained the dataset and created a visualization illustrating each feature's effect on survival probabilities.  

**Collaboration**  
Johann and Pavan worked together on various parts of the tutorial to ensure consistency and clarity in the final document.

---

## Introduction

The sinking of the RMS Titanic in 1912 remains one of the most infamous maritime disasters in modern history. The records of who survived and who passed away in the tragedy provide an opportunity to investigate how social, economic, and demographic factors shaped each person’s chances of survival. In this project, we used the Titanic Passenger and Crew dataset from Kaggle to explore whether characteristics such as gender, socioeconomic class, and ticket cost correlated with survival outcomes.

Our analysis centers around three guiding research questions:

1. Did survival likelihood differ between men and women aboard the Titanic?  
2. Was passenger class associated with the probability of survival?  
3. Were passengers who paid higher fares more likely to survive?  

These questions are important because they connect the historical event to broader issues of inequality, resource allocation, and structural privilege. Disasters often magnify existing social hierarchies, and examining Titanic survival patterns helps us understand how demographics and economic factors influenced outcomes in crisis.

We constructed a complete data science pipeline. The dataset was acquired directly through KaggleHub, cleaned extensively to resolve missing or inconsistent values, and preprocessed to standardize key variables. Statistical methods included:  

- **Chi-square test** for comparing survival rates between men and women  
- **One-way ANOVA** for comparing survival rates across first, second, and third class passengers  
- **Mann-Whitney U test** to examine differences in fare prices between survivors and victims  

These analyses allowed us to evaluate the role of gender, socioeconomic status, and wealth in determining a passenger’s odds of survival. The results revealed distinct patterns reflecting the social context of 1912.

---

## Data Curation

Before any analysis, the Titanic dataset required extensive cleaning and preprocessing to ensure accuracy, consistency, and interpretability. The raw dataset contained over two thousand entries with varying completeness, mixed numeric and text fields, and inconsistent formatting. Data curation standardized the dataset and resolved malformed data.

Key steps included:  

- Loading the **PassengerCrew.csv** file into a pandas DataFrame  
- Stripping whitespace from column names  
- Removing duplicates and rows missing essential variables (Status, Crew/Passenger, Gender, Fare Price)  
- Dropping the "Profile on Encyclopedia Titanica" column  
- Converting fare prices from historical British currency (pounds, shillings, pence) into decimal pounds  
- Imputing missing fare values using hierarchical median-based strategies  
- Inferring missing passenger class based on job or nearest fare  
- Standardizing gender labels to "male" or "female"  
- Encoding survival as a binary variable (1 = survived, 0 = victim)  
- Filtering data appropriately for specific analyses (ANOVA, Mann-Whitney U)

**Dataset citations:**  
- [Johann's Kaggle Dataset](https://www.kaggle.com/datasets/johannkay/titanic-passenger-and-crew-data)  
- [Pavan's Kaggle Dataset](https://www.kaggle.com/datasets/pavansunkara082/titanic-passengers-and-crew-data/data)

---

## Exploratory Data Analysis

Exploratory data analysis (EDA) helped understand the dataset structure, identify patterns, and justify the statistical tests. Highlights from EDA:

- The majority of individuals aboard did not survive  
- Women had a much higher survival rate than men, motivating a Chi-square test  
- Passenger class distribution: 3rd class had the most individuals, followed by 1st and 2nd class  
- Survival rates by class showed a gradient: highest in 1st class, moderate in 2nd, lowest in 3rd class, supporting one-way ANOVA  
- Fare distribution was right-skewed; survivors tended to pay higher fares, supporting Mann-Whitney U testing  
- Pairwise visualizations (survival vs gender, class, fare) confirmed patterns and data consistency

EDA also verified that fare conversion and inferred class assignments were reasonable and consistent.

---

## Primary Analysis

We used **logistic regression** to model survival probability. This technique allowed us to estimate **odds ratios** for each feature, showing how a passenger’s survival chances changed based on characteristics like:  

- Class (1st, 2nd, 3rd)  
- Gender (male, female)

An odds ratio of **1** indicates no effect on survival odds. Values above 1 indicate increased survival probability, and values below 1 indicate decreased survival probability.

---

## Visualization

Key findings from logistic regression:

- Female and 1st class passengers were set as baseline (odds ratio = 1)  
- 2nd class passengers had an odds ratio slightly above 0.4 (lower survival probability than 1st class)  
- 3rd class passengers had an odds ratio just above 0.2 (even lower survival probability)  
- Male passengers had the lowest odds (<0.1), representing the highest risk

---

## Insights and Conclusions

This analysis shows that survival rates were uneven across gender, class, and fare price:  

- Females had higher survival odds than males  
- Higher-class passengers had higher survival rates than lower-class passengers  
- Passengers who paid more for tickets generally had better survival outcomes  

Even readers with little prior knowledge can learn how demographics and economic factors affected Titanic survival. Those familiar with the disaster will gain a quantitative understanding of how features like class, fare, and gender influenced survival odds.

