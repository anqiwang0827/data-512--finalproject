# How Big is the Gap
## Anqi (Angel) Wang
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
     * |- Data
        * |- inc_occ_gender.csv

In the following sections I will examine these elements one by one. First, let's consider the core of the project which is the Pay-Gap-Analysis.ipynb.   

## Pay-Gap-Analysis.ipynb   
In this Jupiter notebook, detailed steps are documented and presented to 
1) read data for Wikipedia articles dataset and population dataset.   
2) predict quality score for each article using ORES.   
3) combine Wikipedia articles dataset and population dataset.      
4) calculate the proportion of articles per capita and high-quality ("FA" or "GA") articles for each country.
5) create visulizations

#### How to use the Jupyter Notebook
After the Jupyter Notebook is downloaded, run through the notebook.
The module will then output:     
1) 1 final data file in CSV format.     
3) 4 .png images of the visualizations.     

### Visualization
4 .png images of the visualization will be saved after executing hcds-a2-bias.ipynb . The visualization will show    
10 countries with the highest proportion of politician articles per capita.   
10 countries with the lowest proportion of politician articles per capita.   
10 countries with the highest proportion of high-quality politician articles of all politician articles.   
10 countries with the lowest proportion of high-quality politician articles of all politician articles.   

## Data
The Wikipedia article dataset is from Figshare. https://figshare.com/articles/Untitled_Item/5513449. The Wikipedia article dataset can be downloaded as 'page_data.csv' and used in latter analysis.The dataset has 47198 rows and 3 variables: country, page and last_edit. 'country' is the country where the politician is from. 'page' is the article title. And 'last_edit' is the edit ID of the last user who edits the page.  

License of the source data:         
Data is generated under CC-BY-SA 4.0 license.        
Wikimedia Foundation terms of use:    
https://wikimediafoundation.org/wiki/Terms_of_Use/en   

The population data is from Population Research Bureau website.http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14. The population dataset can be downloaded as 'Population Mid-2015.csv' and used in latter analysis. The dataset has 21 rows (210 countries in total) and 5 variables: Location,  Location Type, TimeFrame, DataType and Data.
'Location' is the country name. 'Location Type' is always 'Country'.' TimeFrame' is 'Mid-2015'. Data Type is 'Number'. And 'Data' is the country population. We will extract only country name sand population variables for analysis.   

License of the source data:  
Population Reserach Bureau copyright

And for Wikipedia articles, I used a machine learning algorithm 'ORES' (Objective revision Evaluation service) to evaluate the quality of each article. ORES reads article revision id as an input and it will output a quality score  and probabilities the the article's predicted quality for each article.  I extracted only the predicted quality score for analysis. 

There are 6 score categories here:  
FA - Featured article  
GA - Good article   
B - B-class article     
C - C-class article   
Start - Start-class article   
Stub - Stub-class article   
Documentation on what each score category means can be found at https://en.wikipedia.org/wiki/Wikipedia:WikiProject_assessment#Grades  

ORES relevant API documentation:  
https://www.mediawiki.org/wiki/ORES     
ORES API endpoints:      
https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model    


### Final Data  
After generating a new column of ORES prediction score for each article, inner join the Wikipedia article dataset and population dataset together by country name (remove rows with null values). The data frame has following columns:   

| Column         | 
| ------------------|
| country          | 
| article_name |
| revision_id.    | 
| article_quality |
| population      |

A final data file will be saved as wikipedia_article_population.csv.  

## Important Notes
1) ORES API documentation: https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model  
2) After taking rev_id for each article into ORES API, it will return a prediction value and a prediction probability for the score. We use only prediction value in this assignment.   
3) The countries in Wikipedia article dataset and population dataset are different. We only keep the common countries for analysis.  
4) For unavailable revision ID, an error will be generated and no quality score can be predicted from ORES. I skipped those rows for analysis.
