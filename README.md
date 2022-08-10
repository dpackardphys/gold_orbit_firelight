# Gold_Orbit_Firelight Group Project
## Title: Socio-Economic Factors for Mental Health in Chicago

*Group members: Karina Alvarez, Douglas Packard, Karan Shah*

## Introduction
Understanding mental health has continued to have a greater importance in society. Our mental health determines the way we think, feel, and act. So why wouldn’t we study it?

As residents of Chicago, we felt inclined to see what the we could discover about in what way, if any, has our socio-economic environment shaped our mental health, which in turn, shapes our lives. 


## Questions
* How has the level of hardship changed over time in Chicago? 
* Is there a correlation between the suicide mortality rates and vacant neighborhoods?
* What can data tell us about school safety in Chicago?
* What can data tell us about community safety in Chicago?
* What correlations are there between various youth health indicators (diet, exercise, drinking)?
* How has overall data coverage changed over time?
* What other factors are strongly correlated?

## Discussion
Discuss how we got from the initial idea of the project and questions to what we ended up with. How we explored the data from Chicago Health Atlas to address 
the questions we settled on.

We initially set out to explore what the data said about mental health and socio-economic factors in Chicago in general, by examining this topic from various different angles. We chose to focus in particular on the factors of school and community safety, suicide mortality, a composite measure called the Hardship Index, and physical health in relation to mental health. From the Chicago Health Atlas web-broswer interface (https://chicagohealthatlas.org/indicators) we were able to easily view individual health data indicators pertaining to these topics along with many others, visualized geographically across the many neighborhoods of Chicago, and plotted over time. There was also an easily accessible feature for downloading an individual indicator's data as a csv file.

The difficulty of this initial phase was narrowing our broad factors of interest down to indivudal indicators in the Atlas on which we could then perform our own data exploration and analysis. There are 284 different indicators in the Atlas, spread across seven main Categories which are then each divided into several subcategories. From the perspective of our interest in studying the relations between socio-economic and mental health factors, it was very easy to imagine that many more indicators could be relevant to us than we would have time to feasibly analyze. At this stage, we chose the particular indicators and possible correlations we would eventually analyze, still sticking as closely as possible to our initial questions, and split up the remaining work according to these choices and what questions we thought they we enable us to address. We will now discuss how we explored each of these questions in further depth, before describing how we analyzed each of these questions.

Karina studied the Hardship Index, and also correlations between suicide mortality and vacancy in neighborhoods. The Hardship Index is a composite score reflecting hardship in the community (higher values indicate greater hardship). It incorporates unemployment, age dependency, education, per capita income, crowded housing, and poverty into a single score that allows comparison between geographies. The available data assigns such a score to each neighborhood of the city for two different date ranges (2011-2015 and 2015-2019). The Atlas' web visualization tools allow one to view the Hardship data geographically for individual years, so we decided to instead see how the score had changed between the two date ranges for each neighborhood, with the goal of producing a geographic heatmap of the differences in Hardship score.

From the initial thought of trying to explore the data on suicide, we first discovered that there were indicators on both youth suicide attempts as well as overall suicide mortality. We decided to focus on the latter indicator, as that represented a "worst-case scenario" endpoint for an individual's mental healthcare process. We wanted to see whether that was correlated with some other indicator, but tried to avoid choosing something that we should obviously be expected to be either correlated *or* independent. To this end, we chose the housing vacancy data as a second indicator to be possibly correlated with suicide mortality, as it is plausible that it would be relavent to negative mental health outcomes, but not something so close to suicide mortality that discovering a correlation would tell us nothing new.

Karan studied the factors of school and community safety. 

## Analysis
Describe how we analyzed the data in order to create visualizations and answer questions. Final visualizations go here.

## Results
Present answers to our questions based on visualizations and statistical analysis.

## Conclusion
Wrap things up.
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

