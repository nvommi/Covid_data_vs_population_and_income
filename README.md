# Covid_data_vs_population_and_income
#Background
The covid pandemic has been affecting the world socially and economically. Cases continue to rise even amidst the vaccine with over 124 million infections and 2.7 million deaths, the virus has had a catastrophic impact. The United States has 2.6 million cases by itself with over 100,000 cases. Mutations are constantly evovling, for example with the New York pathogen, making 22 distinguishing mutations in total.

[Covid-Statistics](https://www.medicalnewstoday.com/articles/live-updates-coronavirus-covid-19#1)

[More statistics](https://www.nature.com/articles/d41586-020-00502-w)

While examining the United States,  cases have been rising exponentially for larger and high population density areas. This led me to examine the top 50 most populated cities, but excluding the cities that are in the same state/county. 

In the beginning of the outbreak, the U.S. government had a very hands off policy issuing legislation regarding the virus and led the responsibility up to smaller governments. Due to this, the pandemic has had various effects across the country and caused the virus to be attracted to the most populous U.S. cities.

# Business Question
Does the wealth of citizens affect covid outcomes in major American cities?
# Compiling Data
Using the Politifact list of 50 largest US cities we searched in google and to find what county we felt best represented that city. This mostly came down to a judgement call using the map and population of counties to determine what county best represents each city. This was the same data as the previous project so I utilized the same compiled excel data.
Using this list of counties we extracted the line of COVID data from the JHU Center for Systems Science and Engineering (CSSE) entry from March 24th, 2021. This was combined with median household income data taken from opportunity Atlas, and population data from Data Commons.
# Regression
I began by organizing the data that I needed to perform my multiple linear regression. I used the politifact list of 50 largest U.S. cities to find the population of each of the cities while elminating the few that overlap counties. Using the list of counties, I used the Opportunity Atlas database to find the Household Incomes that corresponded with each part. Using the compiled COVID data from before, I utilized Google colaboratory in order to organize the csv data. By importing the csv into the python using a pd.read method, I was able to organize my data into rows and columns similar to excel. I was getting an error with Unnamed: 0 so I had to delete/drop that column and other columns containing data that I did not need for my analysis. I also only wanted the first 46 values so I renamed my data set as df_covid to df_covid.head(47).

After organizing my data properly, I was able to find the measures of central tendency as well as other statistics using the describe function which helped to organize my data and get a proper understanding of it.

# Data Visualizations and Results
I was able to make data visualizations using the plotly function and similar to my midterm project I used Covid Cases, Incident Rate, and Fatality Rate as the Y, with two graphs for each since each had an x variable of Population and Household Income. 

# Covid Cases as Y
![image](https://user-images.githubusercontent.com/78445017/114911429-fd278380-9dec-11eb-8941-1964550a0c5e.png)
![image](https://user-images.githubusercontent.com/78445017/114911460-07e21880-9ded-11eb-9811-4a39ebd5e8bd.png)
For the first analysis with Covid cases as the Y, there was a strong positive correlation between population and covid cases with an R^2 value of 0.9345. The value was significant as well since the P value was around 2.1E-28. On the other hand, Household income seemed to have no correlation with an insignificant p-value along with an R^2 value of 0.0025 showing almost no correlation. 
**Covid cases = 129763 + 0.10968 (population)-3.66152(Household Income)** 
When we control for the Household Income, a one-unit difference in Population is associated with a 0.10968 unit difference in Covid Cases.
# Incident Rate as Y
![image](https://user-images.githubusercontent.com/78445017/114911506-16303480-9ded-11eb-8ea9-c6b8f5d1d369.png)
![image](https://user-images.githubusercontent.com/78445017/114911532-1c261580-9ded-11eb-93d5-0d33031d75c8.png)
For the second analysis with Incident rate as the Y, there was not much correlation between the Population and incident rate as the R^2 value was 0.0567 and insignicant P value of above 0.05. However, the Household Income versus Incident Rate was significant with a P-value of 0.02, showing a slight negative correlation. The R^2 value was 0.085 showing that the data did not follow the prediicted line that closely. 
**Incident Rate = 17013.6 + 0.00038(population)-0.20476(Household Income)**
When we control for the Household Income, a one unit difference in population is associated with a 0.00038 unit difference in Incident Rate. 

# Fatality Rate as Y
![image](https://user-images.githubusercontent.com/78445017/114911590-2a743180-9ded-11eb-98ce-267bb4287ce7.png)
![image](https://user-images.githubusercontent.com/78445017/114911619-3233d600-9ded-11eb-89bd-baee61a6faec.png)
For the third analysis with the Fatality Rate as the Y, the population had a slight positive correlation with a R^2 value 0f 0.1208 and a significant P value of 0.0076. The household income was insignicant as the P-value of >0.05 but the R^2 was 0.0491 with low correlation regardless.
**Fatality Rate = 3.13714 + 1.2E-07(population)-4E-05(Household Income)**
When we control for the Household Income, a one unit difference in population is associated with a 1.2E-07 difference in fatality rate percentage.
# Regression Conclusions 
Data points such as New York, Philadelphia, Chigcago, and Los Angeles stood out since their fatality, incident, and case numbers were much higher than average. This could be the explanation for why some of the best-fit lines were pulled slightly up. Overall, it seemed that Population had a much stronger effect on the dependent variable than Household income did. 

The multiple linear regression providing an effective way to understand the relationship between variables in the city by city analysis. Overall it seems as though Population has a much stronger effect than household as seen with the covid cases analysis. Although for the other studies, the population was not significant, the Covid Case study was the only one that revealed a strong positive correlation for population with a high R^2 value. Household Income was only significant for the Incident rate analysis which revealed there to be a slight negative correlation between the Household Income and Incident Rate. There was a stronger negative correlation for the Incident Rate versus the Fatality Rate. As an overall conclusion, there cannot be any significant claims to be made about the effect of Household Income on Covid Cases. To improve the containment of the disease, governments could push for re-instating masking laws and to spread more awareness regarding the virus. As vaccinations are distributed further, the mortality rates will decreases, and hopefully with more awarenesss, the cases can see a decrease over time. It is not very feasible to spend more money on policies for the virus since the country is already very much in debt, but non-profit organizations and informational programs can help to convey the message and limit cases as seen in the past. This analysis can be used to get an overall visualization and apperance of the relationship between variables, but not many significant claims can be used for this. Companies and government can use this analysis to illustrate to a broad body of of citizens who do not have a high level of analytical understanding, and can be used to educate those who are trying to get a mere understanding of the correlation between different possible factors to foster further understanding and questioning..[Article explaining](https://www.brookings.edu/blog/up-front/2020/03/25/where-is-the-u-s-government-getting-all-the-money-its-spending-in-the-coronavirus-crisis/)

Python was useful in this project in order to get a better visualization of data. There was much quicker efficiency and speed with creating data visualizations than excel and it was successful in giving me results quickly and efficiently more so than excel. The results were almost the exact same as excel so no new conclusions can be made, but python was definitely helpful for handling bigger data sets. Analysis for linear regression happened almost instantly and there was no lag or delay like in Excel. It helped me handle all the data values and statistics with greater ease as compared to excel.

# Data 
[JHU CSSE CSV March 24, 2021](https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_daily_reports_us/03-24-2021.csv)

[Data Commons](https://datacommons.org/place/geoId/06037)

[Politifact 50 Largest US Cities](https://www.politifact.com/largestcities/)

[Opportunity Atlas](https://www.opportunityatlas.org/)

[Cluster Analysis](https://github.com/cmclane1/Covid-in-Americas-Largest-Cities/blob/main/Covid_Cities_Cluster.xlsx)

[Multiple Regression Analysis.xlsx](https://github.com/cmclane1/Covid-in-Americas-Largest-Cities/files/6218152/Multiple.Regression.Analysis.xlsx)



