# Project 1: Analysis of SAT and ACT Participation Rate

## Problem Statement

The new format for the SAT was released in March 2016 in a bid to increase participation rate. Since then, levels of participation in multiple states have changed with varying legislative decisions. This project aims to explore trends in the participation rates of the SAT and ACT tests for the three-year period (2017-2019) and seeks to identify regions/states that have the lowest SAT participation rates as potential high growth areas.

## Executive Summary
The new format for the SAT was released in March 2016 in a bid to increase participation rate. Since then, levels of participation in multiple states have changed with varying legislative decisions. As part of the project team, I am tasked identify potential states and provide recommendations to increase participation rate for SAT test. Using the participation data from 2017 - 2019, Midwest had recorded lowest participation rate compared to other regions. 8 of the 12 states with less than 20% participation are identified for interventions to improve the participation. The recommendations are (1) for the College Board work with the Education Board to promote SAT as the test of choice; (2) increase outreach to graduating students; (3) extend free preparation resources to paying test takers.
This presentation and report is geared toward **non-technical** executives with the College Board.

## Dataset Dictionary
For *act_stack_all_region.csv* and *sat_stack_all_region.csv*
|Feature|Type|Dataset|Description|
|:---|:---|:---|:---|
|**state**|*object*|ACT & SAT|This column contains the states where the test takers were from.| 
|**part_rate**|*float*|ACT & SAT|This column contains the participation rate for each state (proportion of graduating students who took the respective tests).| 
|**geog_location**|object|ACT & SAT|This column contains the categories of the geographical location of the states (South, West, Midwest, Northeast)|
|**year**|int|ACT & SAT|This column indicates the year of the results.| 
|**total_mean**|float|SAT|This column contains the mean total score for SAT test.| 
|**act_composite_mean**|float|ACT|This column contains the mean composite score for ACT test.| 

## Summary of Analysis

1. During the three-year period following the implementation of the new format, there is marginal increase in the mean SAT participation rate from 40% in 2017, to 49% in 2019. For the same period, the was greater increase in the mean ACT participation (from 32% in 2017 to 59% in 2019). 
2. There is strong negative correlation between the SAT and ACT participation rates. In other words, students who had taken one test would likely not take the other test as they would have fulfilled the high school graduation/ college admission requirements.
3. The states in the Midwest region recorded significantly lower SAT participation rate (averaging at less than 20%) as compared to the states in other three regions. The states identified are Iowa, Kansas, Minnesota, Missouri, Nebraska, North Dakota, South Dakota, Ohio, and Wisconsin (state's high school graduation requirement to take the ACT test). With the current low participation rates, these states have the highest potential for increasing participation rates.


## Recommendations

1. Work with the education boards of the respective states identified to promote the use of SAT as a standardise test, or make it mandatory for graduation so that students will choose to do SAT over ACT.
2. Conduct promotional talks at the high schools in the Midwest to increase brand exposure. More importantly, the talks should seek to inform students of the new format and how it would benefit them, as well as the comparison with the ACT test.
3. Extend the free preparation resources to paying test takers as well so that they could prepare well for the test. Given the choice, students would likely choose SAT if they were well-supported with resources and know that they can score well in it.