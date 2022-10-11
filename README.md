# Labor-Classification



# Use Case Summary
This use case is trying to explore and analyze labor data in one geographical area. Every analysis in this use case are NOT represents any organization's perspective, and only for personal exploration.

## Data and Data Source
This use case is using data from National Labour Force Survey  (NLFS) or SAKERNAS data in Northen Maluku Province held by Statistics Indonesia that taken at the second semester of 2020 (2020 - II).
The questionnaire can be accessed at: https://sirusa.bps.go.id/sirusa/index.php/kuesioner/2620

## Objective Statement
- Get insight about labour force in Northen Maluku Province
- Get insight about unemployment in Northen Maluku Province
- Get insight aboun non-labour force inNorthen Maluku Province

## Challenges
- Large size of data, and too many variables (hundreds of columns)
- Data is very raw, consist of redundant variable such as code of region and name of region
- Data is generated from a survey. Therefore, caution is needed in interpreting the results.

## Methodologies
- Descriptive Analysis
- Exploratory Data Analysis
- Classification Modelling

## Benefit
- As a basis for formulating general policies related to labor in Northen Maluku Province.
- Helping local policy maker to map out any programs for overcoming unemployment in the regions.

## Expected Outcomes
- Know the employment characteristic in Northen Maluku Province.
- Know the unemployment and underemployment characteristic in Northen Maluku Province.
- Know the charactristic of working age population not in the labor force who are in schools, doing housekeeping, others, exclude personal activity.


# Business Understanding
The provision of labor force data is carried out through The National Labor Force Survey (NLFS) in all regency/municipality of Indonesia. The other sources of labor force data are from among others National Socio-Economic Survey, Population Census, and Intercensal Population Survey. The concepts and definitions used for the labor
force data are similar for all surveys and censuses since 1976, except for the unemployment rate and employment status, which have been extended since 2001.

# Data Understanding
Total number of household samples of the NLFS August 2020 in Northen Maluku Province were 4.386 with a response rate of 96,08
percent. The main information collected in The National Labor Force Survey are data on individual household members covering persons aged 5
years and older. However tabulated data covers household members aged 15 years and older.

# Data Preparation
Because there are too many variables in dataset (hundreds of columns), the features are choosen by my subjectivity based on general understanding about the data. All the further steps are done by Python.

The coverage of features that will be used to further analysis are:
- Gender
- Marital Status
- Graduation at pandemic period status
- Looking for a job status
- preparing a business status
- Main reason why not looking for a job
- Code of region
- Educational background
- Age group


# Data Cleansing and Manipulating
Since the data is based on questionnaire, the name of each column are coded. Most of the data alsa already in numeric. So:
- All columns are renamed so it easier to be understood
- Some dictionary are prepared for interprete numerical value (it actually categoricals)
- No missing value

# Exploratory Data Analysis
![image](https://user-images.githubusercontent.com/45409844/194709072-0ba15866-dee4-4526-9745-f7bdfadc4711.png)


## Labor Force Insights
- In general labor force in Northen Maluku Province ldominated by age group between 35-39 yo, followed by age group between 40-44 yo.
- The Unemployment rate consider small
- Labor force in Northen Maluku Province spread balance (proportional to it polulation) all over regions
- Labor force dominated by man than woman
- Most of the labor force are married
- Only small part of them graduated in pandemic period
- Small part of them are now preparing a business
- Age of labour force are spread balance in all of the group age, with highest numbers in range 35 yo - 44 yo
- Education level of labor force dominated by high school Graduate (middle school, high school, and vocational high school)

![Labor Force 1](https://user-images.githubusercontent.com/45409844/195127773-9189808c-88ae-48c5-9af1-e6287f9a0505.png)


## Unemployment Insights

- Unemployment in Northen Maluku Province consist of more man than woman (allign with the gender proportion in labor force)
- Small part of them are graduated in the pandemic period
- Most of the unemployment are in the adjacent age group, dominant by the age between 20 yo - 25 yo.
- Some of the unemployment are not looking for job either. The reasons are vary: already had a job but not start yet; currently preparing a business; but mostly because they feel hopeless that they can get a job
- Surprisingly, unemployment in Northen Maluku Province dominated by they who had Vocational Highschool education level
- Another surprise: Unemployment numbers between middle highschool, highschool and Higher Education level are same.

![Unem1](https://user-images.githubusercontent.com/45409844/195127903-34c5d4ad-2d5d-4e26-9a67-0f7c2930b6c5.png))


## Non Labor Insight

There is a widely known assumption that non-labor-force must be dominated by woman. The data shown below tell us that even in every level of education, woman dominate the non-labor force.
![Non Lab1](https://user-images.githubusercontent.com/45409844/195128007-0290fcb8-76eb-44c4-ba41-19c0e92a2c9e.png)

Another criteria of non-labor-force beside woman (who do housekeeping), is young people (15 - 19 yo) who currently (suspected) still continue their school.
![NonLab2](https://user-images.githubusercontent.com/45409844/195128108-5f0b61ba-4ab0-42af-996d-899c91d0300b.png)


# Modelling : Random Forest Classification
## Random Forest Modelling
- To know which sampling method is best used in Random Forest modelling for this data, it will compared 3 types of sampling : Undersampling, Oversampling, and Combined Method
- For each sampling method,  Accuracy, Precision, Recall, and F1 score will be checked.
- True Positive: Classiefied as a worker, is a worker.
- True Negative: Classified as an unemployment, is an unemployment.
- False positive: Classified as unemployment, is a worker.
- False negative: Classified as a worker, is an unemployment.
- The objective of the model is to decrease false negative, means need it needs a model with high Recall score.

## Modelling Evaluation
Based on the modelling trial on 3 sampling methods, the best methode is **Random Forest Combine Method** with consideration as follows:
- Highest F1 score between 3 sampling methods (0.655)
- High Recall score (0.74), allign with the objective: minimize false negative (Classified as a worker, is an unemployment)


# Summary
- Age of labour force in Northen Maluku Province are spread balance in all of the group age, with highest numbers in range 35 yo - 44 yo
- Education level of labor force dominated by high school Graduate (middle school, high school, and vocational high school)
- The Unemployment rate consider small.
- Most of the unemployment are in the adjacent age group, dominant by the age between 20 yo - 25 yo.
- Some of the unemployment are not looking for job either. The reasons are vary: already had a job but not start yet; currently preparing a business; but mostly because they feel hopeless that they can get a job.
- Unemployment in Northen Maluku Province dominated by they who had Vocational Highschool education level.
- Unemployment numbers between middle highschool, highschool and Higher Education level are same.
- Non Labor force dominated by woman and younger population (15-19) yo.
- Random Forest Classification used to modelling the employment and unemployment in Northen Maluku Province's Labor Force. Combine method shows best evaluation score.
