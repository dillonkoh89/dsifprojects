# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Dillon Koh, DSIF-2 Singapore

### Problem Statement

The SAT test administered by College Board is a standardized assessment to allow prospective students to evaluate their writing, reading and mathematical skills and use this information as part of their colleague application process. Being widely established and acknowledged, the SAT has supported large numbers of students and universities in the admission process. While being widely used, critique on the test has become more vocal, with main concerns challenging the adequateness of standardized tests to predict success of prospective students, methodological critic on recent test structure revisions and the accusation of it facilitating social injustices.

For the course of this project, DSIF2-Group1 has decided to support the College Board with an analytical consulting project tackling three major concerns:

(1) How can SAT acceptance be strengthened?<br />(2) How can the College Board tap into auxiliary revenue streams to support proactive tackling of big challenges<br />(3) Which measures can be taken to support its long-term license to operate?

DSIF2-Group1 understands that the College Board is a mission-driven not-for-profit organization that connects students to college success and opportunity. Therefore, the College Board does not have much budget for this project.

This subset of the overarching project focuses on (1) and (2), investigating ways to grow SAT participation rate in states with maximized return on investment (ROI). To ensure maximized ROI, the research objective of this notebook is to investigate the latest trend and development of SAT participation in the various states and look to grow SAT participation in the selected states. 

The proposal will include the selected states of interest, justification for our selections and recommendations for the following:
- Primary focus of growing SAT participation
- Other aspects such as improvement of SAT scores (consider the 2 different sections of SAT), supporting the household and students in terms of subsidized cost where possible

### Initial thought process on the analysis to tackle the problem statement

- Analyze the SAT participation rates across the states, median household income and the SAT performance between the period of 2017 and 2019,
- Identify a list of states with low SAT participation rates based on a filtering criteria and trend of the participation rates across 2017 to 2019 
- Analyze the selected list of states for the median household income and SAT performance based on the scores provided
- Provide a list of recommendations and conclusion to grow SAT participation rates across the final selected states

### Executive Summary

This main objective of this project is to tackle the problem statement of growing SAT participation in US with the constrain of limited budget. Therefore, the recommendations are required to maximize the return on investment as stated in the above problem statement. 

The data are organized at state level within US and contain SAT participation rates, number of SAT takers, median household income and SAT scores achieved from 2017 to 2019. This allows for a state by state comparison of the participations, scores and household income and at the same time explore relationships between these 3 variables/factors.

The initial analysis shows that there are some states which have already mandated SAT or ACT tests. The data set is consistent with the observation that many states mandate one of the two tests as a requirement for high school graduation and the notion that students are likely to take only one of the two tests.
This compulsory requirement of their students requiring to take SAT or ACT results in driving SAT participation in 2 difference ways:

- Mandated SAT results in 100%  SAT participation rate
- Mandated ACT results in extremely low SAT particiption rate.

Considering the above, states which mandate ACT or SAT shall be excluded in the selection of states to focus College Board's efforts on certain states which have potential for significant SAT growth rate. However, there will be some high level analysis carried out using the data from SAT or ACT mandated states.
The analysis done suggest that there are 3 states of interest namely **Iowa, South Dakota** and **Missouri** which register relatively low SAT participation rate. Based on the latest data of 2019, these 3 states have participation rates of less than 5%.

In addition to considering SAT participation rate, there is also another factor which is crucial if maximized ROI is desired and that is the growth in terms of the number of SAT takers. This consideration led me to identify 2 states which have moderate participation rate but large number of SAT participations and population of high school graduates.  They are **California** and **Texas**. These 2 states have participation rate of 63% and 68% which consists of 272,892 and 236,665 SAT takers in 2019. Increasing the participation rate of 5% mean an increase of approximately 20,000 SAT takers which is strongly justifiable to also focus on these 2 states due to the growth in terms of SAT takers.

The proposal from DSIF2-Group1 is to focus on the growth of SAT participation rate in the following 5 states:
- **Iowa**
- **South Dakota**
- **Missouri**
- **California**
-  **Texas**

by setting up educational institutes in these selected states. Setting up education institutes will promote SAT and provide another avenue (outside of their high school) for students to better prepare for SAT and building confidence. The educational institutes will teach both the sections Evidence-Based Reading and Writing as well as Math but can help students focus on their weaker section. With better preparation and confidence, it can be expected that the SAT scores will likely be improved too.

Understanding the College Board's tight resources and the observation of median household income in these 5 states, the educational institutes fees can be a higher subsidized rate for Iowa, South Dakota, Missouri and Texas but a much lower subsized rate for California.

To evaluate the effectiveness of the proposal, it is suggested to study the results of the proposal after 2 years.

---

### Datasets used

* [`sat_2017.csv`](../data/sat_2017.csv): 2017 SAT Scores by State
* [`sat_2018.csv`](../data/sat_2018.csv): 2018 SAT Scores by State
* [`sat_2019.csv`](../data/sat_2019.csv): 2019 SAT Scores by State
* [`2017_19_SAT_Participation_Numbers.csv`](../data/2017_19_SAT_Participation_Numbers.csv): Participation Numbers for SAT 2017 - 2019
* [`household_income_2017-2018.csv`](../data/household_income_2017-2018.csv): Median Household Income of US states for 2017 to 2018
* [`household_income_2019.csv`](../data/household_income_2019.csv): Median Household Income of US states for 2019

---

### References

The links shown below are references which were used in the analysis
- https://blog.prepscholar.com/which-states-require-the-sat
- https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice
- https://reports.collegeboard.org/archive/sat-suite-program-results/2019/state-results
- https://reports.collegeboard.org/archive/sat-suite-program-results/2018/state-results
- https://reports.collegeboard.org/archive/sat-suite-program-results/2017/class-2017-results
- https://en.wikipedia.org/wiki/List_of_U.S._states_and_territories_by_income
- https://www.statista.com/statistics/233170/median-household-income-in-the-united-states-by-state/
- https://en.wikipedia.org/wiki/SAT
- https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/
- https://blog.prepscholar.com/which-states-require-the-sat 
- https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice
- https://data.worldbank.org/indicator/NY.GDP.MKTP.KD.ZG?end=2020&locations=US&start=2016 

---

### Conclusion and Recommendations

Based on the analysis done, it is clear that the SAT participation rate is heavily influenced by the state policy towards testing. The following is observed:

- States which mandate SAT test result in 100% participation rate (which is intuitive)
- States which mandate ACT test result in extremely low SAT participation rate

With this observation above, one key takeaway is that the easiest way to grow SAT participation rate with the maximum growth is for the state to mandate SAT testing as a mandatory high school graduation requirement. However, we do recognize that it is not straightforward to get a state to mandate SAT testing as part of their policy.

The exploratory data analysis conducted above suggests the following:
- SAT participation rate has a negative correlation with SAT scores
- SAT participation rate is on the extreme when the state has mandated either SAT or ACT
- There is a moderate positive correlation between SAT participation rate and median household income
- The median household income hasincreased from 2017 to 2019.

From the above, we have removed the states which mandate ACT or SAT and conduct futher analysis as the main objective is to increase SAT participation and excluding these states allow us to focus on the states which have more potential for growth in SAT participation. Based on the criteria rate of low SAT participation rate, 3 states were identified and they are **Iowa**, **South Dakota** and **Missouri**. The SAT participation rate of the 3 states in 2019 is less than 5% as compared to the other 17 states (after removing the states which mandate SAT or ACT) which has more than 15% participation rate. Hence, if there are efforts to promote and grow SAT participation in these states, the growth would be exponential.

In addition to these 3 states, I have also identified 2 more states to focus the efforts and they are **California** and **Texas**. These 2 states have moderate participation rate but large number of SAT participations and population of high school graduates. Increasing the participation rate of 5% mean an increase of approximately 20,000 SAT takers which is strongly justifiable to also focus on these 2 states due to the growth in terms of the number of SAT takers.

Our proposal to increase SAT participation rate is to set up educational institutes in these 5 states. The education institutes will teach both sections of the SAT as there are no data to substantiate that the student in the individual states are weaker in a particular section. There are a few rationales behind our proposal and they are:
- Setting up educational institutes is a way to promote SAT and also reaches out to the high school student population that the institutes are there to help them
- This additional educational support will allow them to be more prepared and confident to take the SAT - result in growth in SAT participation
- This might help mititgate the observation where SAT participation rate has a negative correlation with SAT scores - likely to result in improved scores even with higher SAT participation rate by focusing on the weaker section for a particular group of students.

Understanding that the College Board has tight resources and coupled with the observation of increasing median household income across 2017-2019, I believed that the institute fees for the students can be at a subsized rate. Based on the median household income of the indvidual state, the institutes fees can be a higher subsidized rate for Iowa, South Dakota, Missouri and Texas but a much lower subsized rate for California. The actual details of the subsidies will be provided at a later stage.

Finally, it is suggested to study the results of the proposal after 2 years to evaluate the effectiveness of the proposal. 

In conclusion, our proposal is to set up education institutes in Iowa, South Dakota, Missouri, California and Texas with subisized institute fees for interested students.

---

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|SAT 2017-2019 Details|State Name| 
|**participation_rate_2017**|*float*|SAT 2017-2019 Details|State's SAT Participation Rate for 2017| 
|**sat_takers_2017**|*integer*|SAT 2017-2019 Details|State's Number of SAT Participaints for 2017| 
|**ebrw_2017**|*integer*|SAT 2017-2019 Details|State's SAT Average Score for Evidence-Based Reading and Writing Section for 2017| 
|**math_2017**|*integer*|SAT 2017-2019 Details|State's SAT Average Score for Mathematics Section for 2017|
|**total_2017**|*integer*|SAT 2017-2019 Details|State's SAT Average Total Score for both Evidence-Based Reading and Writing and Mathematics Sections for 2017|
|**participation_rate_2018**|*float*|SAT 2017-2019 Details|State's SAT Participation Rate for 2018| 
|**sat_takers_2018**|*integer*|SAT 2017-2019 Details|State's Number of SAT Participaints for 2018| 
|**ebrw_2018**|*integer*|SAT 2017-2019 Details|State's SAT Average Score for Evidence-Based Reading and Writing Section for 2018| 
|**math_2018**|*integer*|SAT 2017-2019 Details|State's SAT Average Score for Mathematics Section for 2018|
|**total_2018**|*integer*|SAT 2017-2019 Details|State's SAT Average Total Score for both Evidence-Based Reading and Writing and Mathematics Sections for 2018|
|**participation_rate_2019**|*float*|SAT 2017-2019 Details|State's SAT Participation Rate for 2019| 
|**sat_takers_2019**|*integer*|SAT 2017-2019 Details|State's Number of SAT Participaints for 2019| 
|**ebrw_2019**|*integer*|SAT 2017-2019 Details|State's SAT Average Score for Evidence-Based Reading and Writing Section for 2019| 
|**math_2019**|*integer*|SAT 2017-2019 Details|State's SAT Average Score for Mathematics Section for 2019|
|**total_2019**|*integer*|SAT 2017-2019 Details|State's SAT Average Total Score for both Evidence-Based Reading and Writing and Mathematics Sections for 2019|
|**change_part_rate_2017_to_2018**|*float*|Overall_Final|State's growth in SAT Participation Rate from 2017 to 2018|
|**change_part_rate_2018_to_2019**|*float*|Overall_Final|State's growth in SAT Participation Rate from 2018 to 2019|
|**state**|*object*|Median Household Income 2017-2019|State Name|  
|**income_2017**|*integer*|Median Household Income 2017-2019|State's Median Household Income for 2017| 
|**income_2018**|*integer*|Median Household Income 2017-2019|State's Median Household Income for 2018| 
|**income_2019**|*integer*|Median Household Income 2017-2019|State's Median Household Income for 2019| 

---

