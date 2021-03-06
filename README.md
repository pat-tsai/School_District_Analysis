# School District Analysis
## Overview of school district analysis:
The purpose of this analysis was to obtain statistics describing a variety of groups. These results included analysis based grouped by districts and schools, best and worst performing schools, average scores based on grade levels, and scores based on school funding. However, due to evidence of academic dishonesty, the second portion of this analysis involved replacing 9th grade scores at Thomas High School with "NaN", elimiting these results from the final analysis. By removing the potentially faulty data, we can re-perform the district analysis while upholding state-testing standards, and observe how this original data affected the outcome.

## Results
***How is the district summary affected?***
  - Shown below is the original district analysis on top (without Thomas High School 9th grade data removed), and the updated analysis on bottom. As we can see, there was no significant changes in average math or reading scores, suggesting that these mean values are relatively representative of the total population. However, we can observe over a 1% decrease in students passing both math or reading, which results in a 1% decrease to overall passing rate.   

  ![ScreenShots](/Resources/Resources/old_vs_new_district_analysis.png)

***How is the school summary affected?***
  - Since no changes were made to student data other than to the 9th grade students at Thomas High School, all cell values remained the same except values pertaining to that specific high school. Thus, we can use the `.loc()` method to filter the complete school dataframe to only display results from Thomas High. Below are screenshots of the old high school data(left) versus the new data(right). 
![ScreenShots](/Resources/Resources/old_vs_new_Thomas_High.png)

  - Once again, the data shows no significant changes in average math and reading scores. However, there is a substantial decrease in math and reading passing rates, resulting in about a 25% decrease in overall passing rate.   

***How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?***
  - Shown below are the top 5 performing schools (based on overall passing rate) before revising the data.
  
  ![ScreenShots](/Resources/Resources/top_schools_old.png)  

Thomas High School was previously ranked 2nd out of all schools in the district, with a whopping 90.95% overall passing rate. However, this rate dropped to 65% after removing the potentially tampered 9th grade data, resulting in a large drop in ranking. To put this into perspective, the bottom 5 ranking schools had overall passing rates between 53% - 53.54%.  

***How does replacing the ninth-grade scores affect the following:***
  - **Math and reading scores by grade**
    - By utilizing the following snippet of code: `Thomas_High_math_by_grade = math_scores_by_grade.loc['Thomas High School']`, we can quickly filter the dataframe to display all math scores from Thomas High School. The primary difference is that 9th grade math scores display "NaN". As expected, this analysis reveals no changes in 10th, 11th, or 12th grade data (83.1, 83.5, and 83.5 respectively), since the only changes made to the dataset were to 9th grade scores.
 
  - **Scores by school spending**
    - Shown below are scores based on school funding (old on top, new on bottom).
    ![ScreenShots](/Resources/Resources/old_vs_new_scores_by_funding.png)

    - Based on our analysis above, we discovered that Thomas High Schools' spending range per student is from 630-644. Thus, we only need to pay attention to that row for observable changes. Based on the results, there is about a 6% decrease in passing math rate and 7% decrease in passing reading rate once the 9th grade data from Thomas High was removed. As expected, this translates to a 7% decrease in overall passing rate.
    
  - **Scores by school size**
    - Thomas High School was grouped into the medium school size bin since it had 1,635 students. Shown below are the before(top) and after(bottom) results:
    
    ![ScreenShots](/Resources/Resources/old_vs_new_scores_by_size.png)
    
    - Based on the analysis, there was a 6% decrease in passing math rate as well as passing reading rate, resulting in a 6% overall passing rate decrease. However, there was no change in the average scores themselves.
    
  - **Scores by school type**
    - Shown below are the before(left) and after(right) test results statistics based on school type. As we can see, the charter school group statistics decreased since Thomas High school had previously inflated the stats.
    ![ScreenShots](/Resources/Resources/old_vs_new_by_type.png)
    
    
## Summary
In conclusion, the 4 major changes that occurred after removing the 9th grade Thomas High School scores are as follows:
  - 1. A decrease in 1.08% of the overall district passing rate. While 1% may not seem like a significant number, it is important to keep in mind the district summary encompasses every single school in the district, thus having the largest sample size. It is surprising that removing only 9th grade data from 1 high school would have such a big impact on over all district pass rate, which includes data for 15 schools in grades 9-12.
  - 2. It is no surprise (given that the 9th grade Thomas High School data was faulty) that the overall pass rate for Thomas High dropped. Based on the analysis, we observed over a 25% decrease in overall pass rate while the average math and reading scores remained faily constant. This is because the scores from grades 10, 11, and 12 were all approximate 83.xx, thus removing the 9th grade data did not have a significant effect on the average. This decrease subsequently dropped Thomas High School from #2 in overall ranking based on overall pass rate to #8. 
  - 3. There was a 7% decrease in overall pass rate for the $630-644 spending range bin (the bin that Thomas High belonged to). This bin contained 5 schools total, and was significantly affected by the 9th grade Thomas High data.
  - 4. There was a 6% overall pass rate decrease in the medium size schools bin (1000-2000 students), and a 3% decrease overall decrease in charter type schools category. We can attribute the varying impacts due to each grouping having different sample sizes. For example, the medium size school bin had 7 schools total, whereas the charter school group only had 5 schools total. Nevertheless, we can conclude that the 9th grade data from Thomas high inflated both of these statistics.  

**Based on the analysis, we can observe that Thomas High Schools' 9th grade data greatly inflated the overall statistics.**
