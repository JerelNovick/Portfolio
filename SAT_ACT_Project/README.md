<!-- #region -->
# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Analysis of SAT & ACT Partcipation Rates

## Project Author
[Jerel Novick](https://github.com/JerelNovick)

## Contents of Repo
<!--ts-->
* [Code](https://github.com/JerelNovick/Portfolio/tree/master/SAT_ACT_Project/code)
* [Data](https://github.com/JerelNovick/Portfolio/tree/master/SAT_ACT_Project/data)


**Summary**

This is a statistical analysis of scores and participation rates for the SAT and ACT tests.  The data from 2017 and 2018 was used for the analysis.

**Problem**

Where is the best money best spent to improve SAT partcipation rates?

**Data**

The data was provided by the College Board, who conduct the SAT, and the ACT.  The data covered all 50 states plus the District of Columbia.  The SAT data included participation rates along with scores for the reading section, math section and total scores for both 2017 and 2018.  The ACT data contained participation rates and composite scores for both years.  Scores for the English, math and science sections was only provided for 2017.

Upon importing the data, it was analyzed to check for irregularities, formatting issues and extraneous or duplicate information.  Where appropriate the data was corrected.  Data dictionary below gives an additional breakdown of the data makeup.
<!-- #endregion -->

**Data Dictionary**

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|ACT/SAT|US State where the exam was given| 
|**sat_participation_2017**|*int*|SAT|Percent of high school seniors in the state who took the exam in 2017|
|**sat_reading_2017**|*int*|SAT|Average reading score in the state for 2017.  The values of score can between 200 and 800.|
|**sat_math_2017**|*int*|SAT|Average math score in the state for 2017.  The values of score can between 200 and 800.|
|**sat_total_2017**|*int*|SAT|Average total score in the state for 2017.  The values of score can between 400 and 1600.|
|**sat_participation_2018**|*int*|SAT|Percent of high school seniors in the state who took the exam in 2018|
|**sat_reading_2018**|*int*|SAT|Average reading score in the state for 2018.  The values of score can between 200 and 800.|
|**sat_math_2018**|*int*|SAT|Average math score in the state for 2018.  The values of score can between 200 and 800.|
|**sat_total_2018**|*int*|SAT|Average total score in the state for 2018.  The values of score can between 400 and 1600.|
|**act_participation_2017**|*int*|ACT|Percent of high school seniors in the state who took the exam in 2017|
|**act_english_2017**|*float*|ACT|Average English score in the state for 2017.  The values of score can between 1 and 36.|
|**act_math_2017**|*float*|ACT|Average math score in the state for 2017.  The values of score can between 1 and 36.|
|**act_reading_2017**|*float*|ACT|Average reading score in the state for 2017.  The values of score can between 1 and 36.|
|**act_science_2017**|*float*|ACT|Average science score in the state for 2017.  The values of score can between 1 and 36.|
|**act_composite_2017**|*float*|ACT|Average composite or total score in the state for 2017.  The values of score can between 1 and 36.|
|**act_participation_2018**|*int*|ACT|Percent of high school seniors in the state who took the exam in 2018|
|**act_composite_2018**|*float*|ACT|Average composite or total score in the state for 2018.  The values of score can between 1 and 36.|

**Methodology**

Multiple visualization, including boxplots, distribution curves and histograms, were performed and analyzed to look for trends.  Additionally, the data was sorted to identify top and bottom values.  Additional research was also conducted outside of the datasets.

**Conclusions**

The difference in participation rates is mainly a regional issue.  The ACT's have higher participations in the Midwest and South.  This is in large part due to more states that require students to take the ACT as a condition of graduation (source: https://www.testive.com/state-sat-act/).  The SAT's are more dominant in the Northeast.  While the SAT's may have lower state participation rates more students took their test in 2018 (source: https://www.washingtonpost.com/education/2018/10/23/sat-reclaims-title-most-widely-used-college-admission-test/?utm_term=.a795b4f35ea0).

**Recommendations**

Efforts should be focused gaining share in states where they have already have a large share such as California.  Pursuing being the mandatory test in more states would increase participation rates but this is likely to be a longer process.  They should focus on gaining population instead of state instead of participation.  Increasing the number of SAT School Days, where the test is given during the week. They can also look for ways to compete on price. 
