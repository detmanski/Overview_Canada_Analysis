<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.556 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β34
* Tue Feb 14 2023 17:36:07 GMT-0800 (PST)
* Source doc: README file
----->


If you were to choose a new city within Canada to live in, which city would you pick? Our aim is to give you some insights to help you decide.

<span style="text-decoration:underline;">Introduction:</span> 

With the massive influx of immigrants and the ever changing conditions of the housing market … The big question we aim to answer is: Where are the most ideal cities within Canada to live?

We first brainstormed what governs one’s decision of moving from one city to another and settled on a few factors - affordability in terms of shelter costs, population, weather, crime rate, cultural activities, employment prospects and income levels.

The research questions that help guide the analysis include:



1. Does the weather in each city affect the median income?
2. Which cities are the most affordable to live in?
3. Which city has the highest employment rate? 
4. Which city is most rich in cultural activities? 
5. Which cities have the lowest crime?
6. Which cities have the most ideal weather conditions?

The data was obtained from publicly available datasets on Statistics Canada and OpenweatherAPI. After collecting this data, we decided to pick the top 15 most populous cities in Canada to narrow down our analysis and answer our research questions. 

The project files require the installation of certain libraries and modules as follows: Pandas, Pyplot from Matplotlib, Scipy from Stats, Seaborn and NumPy

Below is a description of all folders on this GitHub project repository

**Resources**: this folder contains all the raw data files obtained from Statistics Canada and OpenweatherAPI

**Output**: this folder contains all the clean csv files that were created to narrow down the datasets

**Visualisations**: this folder contains all visualisations relevant to answering our research questions 

**Analysis:**

The analysis has been broken down into 6 sections pertaining to each sub-research question



1. Does the weather in each city affect the median income?
    * Wilcoxon rank-sum test of the median income in the top 15 most populous cities against all cities in Canada returned a p-value of 0.02.  This indicates that population does have some effect on median income.
    * We looked into a relationship between max temperature and median income which identified a weak negative correlation(r-value -0.14). The linear regression formula, y= -133.77x +39672.18, indicated that for every 1°C increase, median income should decrease by $133.77.
    * St. Catherine’s - Niagara is 15th in median income of the most populous cities  but 148/160 for Canada overall.
2. Which cities are the most affordable to live in?
    * Quebec has the lowest average monthly rent of $905 and Vancouver has the highest average monthly rent of $1624. In Quebec, only 26.11% of the median monthly income is spent on rent whereas in both Vancouver and Toronto, this value climbs to almost 50%
    * In terms of owned dwellings, Quebec again has the lowest average monthly cost of $1201 and Toronto has the highest average monthly cost of $2108. Similar to rented dwellings, the average percentage of income spent on owned dwellings in Quebec is 34.6% whereas in cities like Vancouver and Toronto, this value is an alarming 60% and 65.2% respectively.
    * In order to test if there really is a difference between monthly renting cost and owning cost/mortgage, an Independent samples t-test was run. The assumptions underlying the t-test were that data from both samples is normally distributed, independent and homogenous. The null hypothesis for this t-test stated that there is no difference between average monthly costs for rented dwellings and owned dwellings. The alternative hypothesis stated that there is a significant difference between average monthly costs for rented dwellings and owned dwellings. 
    * A t-statistic of 3.37 and a significant p-value of 0.0023 was obtained for a 95% confidence interval. Hence the null hypothesis can be rejected, indicating that there in fact is a significant difference between renting costs and owning costs across the 15 cities where the mean monthly cost of owning a house ($1564.33) is greater than the cost of renting a house ($1272.53), with a difference of $291.8 between both.
3. Which city has the highest employment rate? Is there a correlation between employment rate and median income?
    * The city with the highest employment rate is Québec with an employment rate of 62%
    * To test the relationship between employment rate and median income, both variables were plotted against each other using a scatter plot. A linear regression determined that there is a significant and moderate positive correlation between employment rate and median income (p-value = 0.002 and r-value = 0.73). This implies that cities with higher employment rates are also likely to have higher median income. The regression equation highlights that with every one percent increase in the employment rate, the median income increases by $865.7
4. Which city is most rich in cultural activities?
    * We first looked at the overall participation in cultural activities. We used overall participation as a metric to decide which area had the most community involved in cultural activities and where cultural activities were most readily available. The information was based by province, as the participation in cultural activities would not be based solely within one’s city (ie. One can travel within the province to participate). For consistency with the data we did break it down to the 15 cities on the bar graph ‘cities_overall_participation.png’, however the values are the same based on the province within. It’s also notable that the overall participation was measured by using 100 – “% that did not participate.”
    * We used the stacked bar graph ‘stacked_bar_culture.png’ to gain insight into the specific cultural activities available in each province. Crafting has the highest participation rate overall with music as a close second. In this way you could look at which form of culture is most important to you and choose where to live based on that availability. For example, the only province with notable Theatre activity was Ontario. Nova Scotia has overall the highest participation in cultural activities and Quebec has the lowest. If participation or exposure to cultural activities is important to you then within our 15 cities, Halifax would be the most ideal and Quebec City or Montreal the least.
    * The pie chart takes a closer look at our top cultural city, Halifax. Over 60% of the population participated in cultural activities and this looks at the break down of participation in each activity. The top 3 are crafting, making music and visual arts. For someone looking for a rich and diverse cultural experience, living in Halifax would be ideal.
5. Which cities have the lowest crime?
    * The crime severity index value for each city was considered in evaluating the 15 cities.  This value takes into account both volume and seriousness of crimes reported to police.  The more serious offences have a greater impact on changes in the index.  The most desirable city to live in based on the crime severity index value in 2021 is Quebec City, followed by Toronto and Ottawa respectively.  
6. Which cities have the most ideal weather conditions?
    * Using the openweather api, current weather conditions for Feb 11 were used to evaluate which city is desirable, with the assumption that the higher the temperature, the more desirable the city. Vancouver ranks highest, followed by St Catherines and Toronto respectively.

<span style="text-decoration:underline;">Conclusion and implications of findings:</span>

Summary of project findings:



* Highest employment rate - Quebec City
* Lowest percentage of income spent on shelter (rent & owned) - Quebec City
* Lowest crime severity index value - Quebec City
* Highest max temperature on Feb 11 - Vancouver
* Highest participation in cultural activities - Halifax
* Highest median income - Ottawa

This information can be highly relevant to anyone moving to Canada or relocating to a different city within Canada and who has similar considerations in mind. This data can help individuals know what to expect from each of the 15 cities

The small sample size of 15 cities is one of the limitations of this project. There were certain other factors that weren’t incorporated into the analysis since the scope of this project was such for example health services, demographics, taxes, education availability, ease of transportation etc.

Resources:



* https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E
* https://openweathermap.org/api
* https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3510018901
* https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1310010801
