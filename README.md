# Labor-Classification



# Use Case Summary
This use case is trying to explore and analyze labor data in one geographical area. Every analysis in this use case does NOT represent any organization's perspective and is only for personal exploration.

## Data and Data Source
This use case uses data from the National Labour Force Survey  (NLFS) or SAKERNAS data in North Maluku Province held by Statistics Indonesia, taken in the second semester of 2020 (2020 - II).
The questionnaire can be accessed at: https://sirusa.bps.go.id/sirusa/index.php/kuesioner/2620

## Objective Statement
- Get insights about the labor force in North Maluku Province.
- Get insights about unemployment in North Maluku Province.
- Get insights about non-labor force in North Maluku Province

## Challenges
- The large size of data, and too many variables (hundreds of columns)
- Data is very raw, and consist of redundant variable such as the code of the region and name of the region
-  Data is generated from a survey. Therefore, caution is needed in interpreting the results.

## Methodologies
- Descriptive Analysis
- Exploratory Data Analysis
- Classification Modelling

## Benefit
- As a basis data for formulating general policies related to labor in North Maluku Province.
- Helping local policy maker to map out any programs for overcoming unemployment in the regions.

## Expected Outcomes
- Know the employment characteristic in North Maluku Province.
- Know the unemployment and employment characteristics in North Maluku Province.
- Know the characteristics of the working age population not in the labor force who are in schools, doing housekeeping, and others, excluding personal activity.


# Business Understanding
The provision of labor force data is carried out through The National Labor Force Survey (NLFS) in all regencies/municipalities of Indonesia. The other sources of labor force data are among others National Socio-Economic Survey, Population Census, and Intercensal Population Survey. The concepts and definitions used for the labor
force data are similar for all surveys and censuses since 1976, except for the unemployment rate and employment status, which have been extended since 2001..

# Data Understanding
The total number of household samples of the NLFS August 2020 in Northen Maluku Province was 4.386 with a response rate of 96,08
percent. The main information collected in The National Labor Force Survey is data on individual household members covering persons aged 5
years and older. However, tabulated data covers household members aged 15 years and older.

# Data Preparation
Because there are too many variables in the dataset (hundreds of columns), the features are chosen by my subjectivity based on a general understanding of the data. All the further steps are done in Python.

The coverage of features that will be used for further analysis are:
- Gender (Sex)
- Marital Status
- Graduation at pandemic period status
- Looking for a job status
- preparing a business status
- Main reason why not looking for a job
- Code of region
- Educational background
- Age group


# Data Cleansing and Manipulating
Since the data is based on a questionnaire, the name of each column is coded. Most of the data is already in numeric. So:
- All columns are renamed so it easier to be understood
- Some dictionaries are prepared to interpret numerical values (it is originally categorical)
- No missing value

# Exploratory Data Analysis
![image](https://user-images.githubusercontent.com/45409844/194709072-0ba15866-dee4-4526-9745-f7bdfadc4711.png)


## Labor Force Insights
- In general labor force in North Maluku Province is dominated by the age group between 35-39 yo, followed by the age group between 40-44 yo.
- The Unemployment rate consider small
- Labor force in Northen Maluku Province spread balance (proportional to its population) all over regions
- Labor force dominated by men than woman
- Most of the labor force are married
- Only a small part of them graduated during pandemic period
- Small part of them are now preparing a business
- The age of labour force is spread balance in all of the group age, with the highest numbers in the range 35 yo - 44 yo
- Education level of labor force dominated by high school Graduates (middle school, high school, and vocational high school)

![Labor Force 1](https://user-images.githubusercontent.com/45409844/195127773-9189808c-88ae-48c5-9af1-e6287f9a0505.png)


## Unemployment Insights

- Unemployment in North Maluku Province consists of more men than the woman (align with the gender proportion in the labor force)
- Small part of them graduated during the pandemic period
- Most of the unemployed are in the adjacent age group, dominant by the age between 20 yo - 25 yo.
- Some of the unemployed are not looking for a job either. The reasons vary: already had a job but not started yet; currently preparing a business, but mostly because they feel hopeless that they can get a job
- Surprisingly, unemployment in North Maluku Province was dominated by those who had a Vocational Highschool education level
- Another surprise: Unemployment numbers between the middle high school, high school, and Higher Education levels are the same.

![Unem1](https://user-images.githubusercontent.com/45409844/195127903-34c5d4ad-2d5d-4e26-9a67-0f7c2930b6c5.png))


## Non Labor Insight

There is a widely known assumption that non-labor-force must be dominated by woman. The data shown below tell us that even in every level of education, woman dominate the non-labor force.
![Non Lab1](https://user-images.githubusercontent.com/45409844/195128007-0290fcb8-76eb-44c4-ba41-19c0e92a2c9e.png)

Other criteria of non-labor-force besides women (who do housekeeping) is young people (15 - 19 yo) who currently (suspected) continue their school.
![NonLab2](https://user-images.githubusercontent.com/45409844/195128108-5f0b61ba-4ab0-42af-996d-899c91d0300b.png)


# Modelling : Random Forest Classification
## Random Forest Modelling
- To know which sampling method is best used in Random Forest modeling for this data, it will compare 3 types of sampling: Undersampling, Oversampling, and Combined Method
- For each sampling method,  Accuracy, Precision, Recall, and F1 score will be checked.
- True Positive: Classified as a worker, is a worker.
- True Negative: Classified as unemployment, is unemployment.
- False positive: Classified as unemployment, is a worker.
- False negative: Classified as a worker, is unemployment.
- The objective of the model is to decrease false negatives, which means it needs a model with a high Recall score.

## Modelling Evaluation
Based on the modeling trial on 3 (three) sampling methods, the best method is **Random Forest Combine Method** with consideration as follows:
- Highest F1 score between 3 sampling methods (0.655)
- High Recall score (0.74), align with the objective: minimize false negative (Classified as a worker, is unemployment)

# Summary
- The age of the labor force in North Maluku Province are spread balance in all of the group age, with the highest numbers in the range 35 yo - 44 yo
- Education level of labor force dominated by high school Graduates (middle school, high school, and vocational high school)
- The Unemployment rate consider small.
- Most of the unemployed are in the adjacent age group, dominant by the age between 20 yo - 25 yo.
- Some of the unemployed are not looking for a job either. The reasons vary: already had a job but not started yet; currently preparing a business; but mostly because they feel hopeless that they can get a job.
- Unemployment in North Maluku Province was dominated by those who had a Vocational Highschool education level.
- Unemployment numbers between the middle high school, high school, and Higher Education levels are the same.
- Non Labor force dominated by a woman and younger population (15-19) yo.
- Random Forest Classification was used to model the employment and unemployment in North Maluku Province's Labor Force. The combined method shows the best evaluation score.
