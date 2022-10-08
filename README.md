# Labor-Classification



# Use Case Summary
This use case is trying to explore and analyze labor data in one geographical area. Every analysis in this use case are NOT represents any organization's perspective, and only for personal exploration.

## Data and Data Source
This use case is using data from National Labour Force Survey (SAKERNAS) data in Northen Maluku Province held by Statistics Indonesia that taken at the second semester of 2020 (2020 - II).
The questionnaire can be accessed at: https://sirusa.bps.go.id/sirusa/index.php/kuesioner/2620

## Objective Statement
- Get insight about labour force in North Mollucas
- Get insight about unemployment in North Mollucas
- Get insight aboun non-labour force in North Mollucas

## Challenges
- Large size of data, and too many variables (hundreds of columns)
- Data is very raw, consist of redundant variable such as code of region and name of region
- Data is generated from a survey. Therefore, caution is needed in interpreting the results.

## Methodologies
- Descriptive Analysis
- Exploratory Data Analysis
- Classification Modelling

## Benefit
- As a basis for formulating general policies related to labor in North Mollucas.
- Helping local policy maker to map out any programs for overcoming unemployment in the regions.

## Expected Outcomes
- Know the employment characteristic in Northen Maluku
- Know the unemployment and underemployment characteristic in Northen Maluku
- Know the charactristic of working age population not in the labor force who are in schools, doing housekeeping, others, exclude personal activity.


# Business Understanding
The provision of labor force data is carried out through The National Labor Force Survey (NLFS) in all regency/municipality of Indonesia. The other sources of labor force data are from among others National Socio-Economic Survey, Population Census, and Intercensal Population Survey. The concepts and definitions used for the labor
force data are similar for all surveys and censuses since 1976, except for the unemployment rate and employment status, which have been extended since 2001.

# Data Understanding
Total number of household samples of the NLFS August 2020 in Maluku Utara Province were 4.386 with a response rate of 96,08
percent. The main information collected in The National Labor Force Survey are data on individual household members covering persons aged 5
years and older. However tabulated data covers household members aged 15 years and older.

# Data Preparation
(coming soon)

# Data Cleansing
(coming soon)

# Exploratory Data Analysis
## Labor Force Insight
- In general labor force in Northern Maluku labor force in Northern Maluku dominated by age group between 35-39 yo, followed by age group between 40-44 yo.
- The Unemployment rate consider small
- Labor force in Norten Maluku spread balance (proportional to it polulation) all over regions
- Labor force dominated by man than woman
- Most of the labor force are married
- Only small part of them graduated in pandemic period
- Small part of them are now preparing a business
- Age of labour force are spread balance in all of the group age, with highest numbers in range 35 yo - 44 yo
- Education level of labor dominated by high school Graduate (middle school, high school, and vocational high school)

![image](https://user-images.githubusercontent.com/45409844/194706882-9ccddb9d-159c-47ef-92f2-33f8797639cb.png)


## Unemployment Insight

- Unemployment in Northen Maluku consist of more man than woman (allign with the gender proportion in labor force)
- Small part of them are graduated in the pandemic period
- Most of the unemployment are in the adjacent age group, dominant by the age between 20 yo - 25 yo.
- Some of the unemployment are not looking for job either. The reasons are vary: already had a job but not start yet; currently preparing a business; but mostly because they feel hopeless that they can get a job
- Surprisingly, unemployment in Northen Maluku dominated by they who had Vocational Highschool education level
- Another surprise: Unemployment numbers between middle highschool, highschool and Higher Education level are same.

![image](https://user-images.githubusercontent.com/45409844/194707193-126a9ce9-19d6-4da3-981e-8967f8a15eba.png)


## Non Labor Insight

There is a widely known assumption that non-labor-force must be dominated by woman. The data shown below tell us that even in every level of education, woman dominate the non-labor force.
![image](https://user-images.githubusercontent.com/45409844/194706445-c33926ed-aa75-4845-8106-ea07f8103c81.png)

Another criteria of non-labor-force beside woman (who do housekeeping), is young people (15 - 19 yo) who currently suspected still continue their school.
![image](https://user-images.githubusercontent.com/45409844/194706409-96c5a762-9814-4152-9165-d12fef3ec3e3.png)



# Modelling : Random Forest Classification
## Random Forest Modelling
- Untuk mengetahui metode terbaik pemodelan Random Forest, maka akan dibandingkan antara 3 metode : Original Data, Undersampling, dan Oversampling.
- Untuk setiap metode akan dilihat berapa akurasi, presisi, recall dan F1 score nya
- True Positif: Yang diklasifikasi pekerja adalah pekerja
- True Negatif: yang diklasifikasi pengangguran adalah pengangguran
- False positif: Yang diklasifikasi pengangguran adalah pekerja
- False negatif: Yang diklasifikasi pekerja adalah pengangguran
- Tujuan model: mengurangi false negatif, maka perlu yang recall nya tinggi

## Modelling Evaluation
Metode terbaik dari evaluasi di atas adalah **Random Forest Undersampling** dengan pertimbangan:
- F1 nya paling besar diantara 3 metode
- Recall nya paling tinggi (1) sesuai dengan tujuan, yaitu ingin mengurangi false negatif (diklasifikasi pekerja ternyata pengangguran)


# Summary

