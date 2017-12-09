# How Big is the Gap
### Anqi (Angel) Wang
The goal of this project is to explore gender pay gap betweem women and men in US labor market. 

The dataset used for analysis is the income information for different occupations from Kaggle, retrieved from Bureau of Labor Statistics. It is available here: https://www.kaggle.com/jonavery/incomes-by-career-and-gender/data. The dataset has been downloaded and saved as inc_occ_gender.csv. It has median weekly income for 557 different occupations for male and female workers separately, as well as the count of male and female workers. The data was captured as of January 2015.

The objectives of the project are:     
1) What occupations are most gender dominated (highest percentage of women and lowest percentage of women)?  
2) What is the percentage of female workers in the most paying occupations?  
3) What occupations have the biggest and smallest pay gap between male and female workers?  

Project report with analysis steps are documented in the Pay-Gap-Analysis.ipynb. 

To reproduce the result of the project, you will need to clone this repository into your computer.

## Organization of the  project

The project has the following structure:  
   * data-512--finalproject
     * |- README.md  
     * |- LICENSE  
     * |- Pay-Gap-Analysis.ipynb  
     * |- Abstract  
     * |- Data
        * |- inc_occ_gender.csv

In the following sections I will examine these elements one by one. First, let's consider the core of the project which is the Pay-Gap-Analysis.ipynb.   

## Pay-Gap-Analysis.ipynb 
### Project Report
In this jupyter notebook, first there is'How Big it the Gap' project report with following content:  
* Introduction  
* Related Work  
* Methods   
* Findings  
* Discussion   
* Conclusion  
* References  

### Code
And detailed steps are documented and presented to 
1) Read data occupation and income information from inc_occ_gender.csv. And calculate 'pay gap' and 'women/men share' for each occupation.
2) Show occupations that have highest-lowest percentage of women workers in bar graph.
3) Show the percentage of women workers in the 10 most paid occupations in bar graph.
4) Show the cccupations that have the biggest/smallest wage gap between men and women workers in bar graph.  

## Abstract
Summary of the 'How Big is the Gap' project.  

## Data
The dataset used for analysis is the income information for different occupations from Kaggle, retrieved from Bureau of Labor Statistics. It is available here: https://www.kaggle.com/jonavery/incomes-by-career-and-gender/data. 
The dataset has been downloaded and saved as inc_occ_gender.csv. It has median weekly income for 557 different occupations for full-time male and female workers separately, as well as the count of male and female workers. The data was captured as of January 2015. 

There are 558 rows and 7 columns with following headers: 

| Tables Columns | Meaning                                |
| -------------- | -------------------------------------- | 
| Occupation     | Job titles                             | 
| All_workers    | Number of workers                      | 
| All_weekly     | Median weekly income                   |  
| M_workders     | Number of male workers                 |
| M_weekly       | Median weekly income for male workers  |
| F_workders     | Number of female workers               |
| F_weekly       | Median weekly income for female workers| 

* All worker numbers are in thousands, and all income is in USD. There are several missing values for median income columns since there is no data available for the income information for those occupations.   

License of the source data:   
* Kaggle data terms and conditions: https://www.kaggle.com/terms  
* Bureau of Labor Statistics copyright information of the data:   https://www.bls.gov/opub/#copyright  

### Final Data  
Add 'Pay Gap' column by using difference between men and women median weekly earnings devided by men's median weekly earnings for each occupation. And 'Men_Share', 'Women_Share' columns separately for percentage of men and women for each occupation. 

| Tables Columns | 
| -------------- | 
| Occupation     | 
| All_workers    |  
| All_weekly     | 
| M_workders     | 
| M_weekly       | 
| F_workders     | 
| F_weekly       |  
| Pay Gap        |
| Men_Share      |
| Women_Share    |

## Important Notes
1) Data used in this project is collected in 2015. It is not the most current reflection of US labor market. But same process can be conducted using new data when available.  
2) There are some occupations that we do not have income information in this dataset, we excluded this occupations form analysis. 
