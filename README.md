# Gold_Orbit_Firelight Group Project
## Title: Socio-Economic Factors for Mental Health in Chicago

*Group members: Karina Alvarez, Douglas Packard, Karan Shah*

## Introduction
Understanding mental health has continued to have a greater importance in society. Our mental health determines the way we think, feel, and act. So why wouldn’t we study it?

As residents of Chicago, we felt inclined to see what the we could discover about in what way, if any, has our socio-economic environment shaped our mental health, which in turn, shapes our lives. 


## Questions
1. How has the level of hardship changed over time in Chicago? 
2. Is there a correlation between the suicide mortality rates and vacant neighborhoods?
3. What can data tell us about school safety in Chicago?
4. What can data tell us about community safety in Chicago?
5. What correlations are there between various youth health indicators (diet, exercise, drinking)?
6. How has overall data coverage changed over time?
7. What other factors are strongly correlated?

## Discussion
We initially set out to explore what the data said about mental health and socio-economic factors in Chicago in general, by examining this topic from various different angles. We chose to focus in particular on the factors of school and community safety, suicide mortality, a composite measure called the Hardship Index, and physical health in relation to mental health. From the Chicago Health Atlas web-broswer interface (https://chicagohealthatlas.org/indicators) we were able to easily view individual health data indicators pertaining to these topics along with many others, visualized geographically across the many neighborhoods of Chicago, and plotted over time. There was also an easily accessible feature for downloading an individual indicator's data as a csv file.

The difficulty of this initial phase was narrowing our broad factors of interest down to indivudal indicators in the Atlas on which we could then perform our own data exploration and analysis. There are 284 different indicators in the Atlas, spread across seven main Categories which are then each divided into several subcategories. From the perspective of our interest in studying the relations between socio-economic and mental health factors, it was very easy to imagine that many more indicators could be relevant to us than we would have time to feasibly analyze. At this stage, we chose the particular indicators and possible correlations we would eventually analyze, still sticking as closely as possible to our initial questions, and split up the remaining work according to these choices and what questions we thought they we enable us to address. We will now discuss how we explored each of these questions in further depth, before describing how we analyzed the data to address each question.

Karina studied the Hardship Index, and also correlations between suicide mortality and vacancy in neighborhoods. The Hardship Index is a composite score reflecting hardship in the community (higher values indicate greater hardship). It incorporates unemployment, age dependency, education, per capita income, crowded housing, and poverty into a single score that allows comparison between geographies. The available data assigns such a score to each neighborhood of the city for two different date ranges (2011-2015 and 2015-2019). The Atlas' web visualization tools allow one to view the Hardship data geographically for individual years, so she decided to instead see how the score had changed between the two date ranges for each neighborhood, with the goal of producing a geographic heatmap of the differences in Hardship score.

From the initial thought of trying to explore the data on suicide, she first discovered that there were indicators on both youth suicide attempts as well as overall suicide mortality. Karina decided to focus on the latter indicator, as that represented a "worst-case scenario" endpoint for an individual's mental healthcare process. She wanted to see whether that was correlated with some other indicator, but tried to avoid choosing something that would obviously be expected to be either correlated *or* independent. To this end, she chose the housing vacancy data as a second indicator to be possibly correlated with suicide mortality, as it is plausible that it would be relavent to negative mental health outcomes, but not something so close to suicide mortality that discovering a correlation would tell us nothing new.

Karan studied the factors of school and community safety. He initially looked at the data for eleven different indicators relevant to these factors. He then faced the challenge of narrowing these down to a final selection of indicators, and decided which to pair in order to study their correlations. To understand how household wealth might be related to educational success, he chose to analyze poverty and high school dropout rates together. To see how subjective perceptions of community are tied to possible fear of violence, he chose to pair the self-reported community belonging score with the neighborhood safety score. For getting similar insight into the school environment, he chose to look at school fights and bullying statistics along with self-reported school safety scores.

Douglas initially wanted to study the data on various physical health indicators and how they might be related to mental health factors. The first step here was narrowing things down to just studying youth health. Then he decided on youth diet and exercise data as representative of physical health, and binge drinking as an indicator for mental health. As we will see in the analysis below, the data here proved to be limited.

Faced with this limitation, Douglas decided to additionally try to study the coverage of the data as a whole. Exploring the Chicago Health Atlas data further through its API, he discovered there was a top-level division entirely devoted to Data Coverage, and investigated this more. While the data here did not provide information about the geographic coverage of different indicators (i.e. which had data for all neighborhoods and which only covered some), it did provide the opportunity to analyze the time-period coverage of all the indicators.

Finally, having learned to use the API better, Douglas saw that it would help automate the retrieval of data across as many indicators as possible, and decided to use this to study indicator correlations more broadly by generating a correlation matrix.

## Analysis
We all used pandas and matplotlib to analyze and visualize our data. Karina additionally worked with gmaps to plot her hardship data as a heatmap over the city of Chicago, after using pandas to find the change in hardship data between the two time periods for which it was given.

![Hardship Heatmap](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/hardship_heatmap_2.png)

Here yellow signifies areas with no major change in hardship between the time frames, green signifies that the hardship index has gone down, and red that it has gone up. We discovered that despite our expectations, there has *not* been a uniform increase in hardship across the city, with some areas, such as Bucktown/Wicker Park shown below, in fact seeing a decrease in hardship. 

![Bucktown and Wicker Heatmap](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/hardship_heatmap_1.png)

The data on suicide mortality and vacancy was plotted together, and a linear regression was plotted over it, for the two same year-ranges as the hardship data. As the lines show, there does appear to be some negative correlation, but it is rather weak.

![Suicide and Vacancy 2011-2015](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/suicide_vacant_2011.png)
![Suicide and Vacancy 2015-2019](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/suicide_vacant_2019.png)

Karan first plotted the household poverty and high school dropout rates from the year 2012 together across the neighborhoods of Chicago. The peaks in the line plots of the two datasets appear to be frequently lined up, suggesting these indicators are indeed correlated with one another.

![Household Poverty and HS Dropouts](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/DEEZ1.png)

He next plotted the available community belonging and neighborhood safety data together. Here we can see the slopes of the lines always have the same sign, implying a direct correlation in their changes.

![Community Belonging and Neighborhood Saftety](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/DEEZ2.png)

Karan also plotted the data on school fights, school bullying, and overall school safety together.

![School Violence and School Safety](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/DEEZ3.png)

Doug first plotted the three youth health indicators over time. While there was little data on youth binge drinking, there were some visual similarities between the lines for youth diet and exercise that prompted further analysis.

![Youth Health Indicators](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/youth_health_indicators.png)

He then did a scatter plot of just these two, and plotted a linear regression over that. However, there were only seven data points to work with, and only a weak possible correlation was observed (r-value ~ 0.4645).

![Youth Diet and Exercise](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/youthdietandexercise.png)

With the data coverage information from the API, Douglas was able to plot the total count of indicators with data for each year from 1985 to 2020.

![Indicator Coverage over Time](https://github.com/dpackardphys/gold_orbit_firelight/blob/main/Images/single_year_coverage_bars.png)

Finally, with the data gathered from all 67 (out of 284) indicators that had city-wide coverage between 2010-2020, we generated a correlation matrix. Then a list of 116 indicator-pairs with r-value in the range from 0.75 to 0.95 was generated (with the upper bound chosen to exclude the near-unity correlation between count-indicators and rate-indicators which provide essentially the same data). We did not have an opportunity to look into these results in depth, but from an abitrarily chosen pair in the list we did discover that arson and liver disease mortality are well-correlated!

## Results
1. The level of hardship has been improving, worsening, and staying the same in all neighborhoods. Contradictory to what we thought, every part of the city did not increase in the level of hardship, and some areas even improved.
2. Based on the Suicide Mortality vs Vacancy scatter plots, there is slight correlation between suicide mortality rates and vacant neighborhoods. There is not enough of a correlation that we would say vacant neighborhoods directly cause greater or lesser suicide mortality rates.
3. Poverty appears to play a role in the mental well being of students. The plot shows high poverty rates tend to line up with a high number of high school dropouts.
4. The data shows that the less safe a person feels in their neighborhood, the less belonging they feel to their community.
5. There is a very weak correlation between youth diet and exercise, and not enough data on youth binge drinking.
6. After a steady level from 2000 to 2009 (and very low coverage prior to that), there was a distinct increase in indicator coverage from 2009 to 2017, but a drop-off since then, with 2020 falling back to 2012 levels.
7. There are many well-correlated factors, but it will take more analysis to fully determine which are trivial and which are relevant or interesting.

## Conclusion
As visualized by out plors, we were able to get a lot out of the data. The website provided us with base visualizations, but we were able to go beyond that and dive deeper into the data. While the Chicago Health Atlas provided a lot of room for discovery, there were many gaps that we discovered as well. 

Mental health and socio-economics are broad factors that are important to look at through different angles, which is what we did. We looked at composite indices, mortality data, school data, and health data all regarding neighborhoods in Chicago. 

We found that bad mental health can be made worse depending on the impact school and community can have on your life. We did not find strong correlations between suicide and vacancy, or youth diet and excercise. 

It seems (based on the hardship heatmap) that many neighborhoods in Chicago are getting worse, which from our perspective, means **mental health of the individual is pivotal to quality of life.** 
___
### Introduction (old readme)
We decided to do our first data analysis project on mental health as a broad topic. We chose to study mental health due to its importance in society overall, and for  people as individuals. As residents of the Chicago area, we were particularly interested in seeing what the data says about the socio-economic environment which has shaped our lives. 

### Research Questions to Answer
1. What can the data tell us mental health in Chicago?
2. What does the data tell us about school and community safety in Chicago?
3. Is there correlation between suicide/mortality rates and Hardship Index (composite score of unemployment, age dependency, education, per capita income, crowded housing, and poverty)?
4. How are physical health factors (lead poisoning, pollution, diet & exercise) related to mental health factors (Behavioral health treatment, drug/alcohol rates)?

### Initial Data Sources
* https://chicagohealthatlas.org/indicators
* https://chicagohealthatlas.org/indicators/HDX?topic=hardship-index
* https://chicagohealthatlas.org/indicators/YRSAFP?topic=school-safety-rate

### Task Breakdown
* Karina: matplotlib, data visualizations, presentations
* Douglas: github, pandas
* Karan: API,  project management
* All: Statistical analysis

