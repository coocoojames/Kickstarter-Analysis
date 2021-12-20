# An Analysis of Kickstarter Campaigns
Analyzing Kickstarter data for trends.

# Purpose of analysis:
To analyze the success rate of theater and play projects based on launch dates and the pledge goals by finding possible correlations between them.

# How I performed my analysis:
1.	Extracted years from the Launch Date Conversion column using the Year() function.
2.	Created a pivot table with the range of all the data on the main data table.
3.	Populated pivot table with following fields:
Filter: Parent Category, Year
Columns: Outcomes
Row: Launch Date Conversion
Values: Count of outcomes
4.	Filter Parent Category to just: theater
https://github.com/coocoojames/Kickstarter-Analysis/blob/main/Resources/Screenshot%201.png

5.	Inserted line chart from the pivot table
https://github.com/coocoojames/Kickstarter-Analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png

6.	Populated the self-made table of pledge goal range and the number of successful, failed, and canceled campaigns and the percentage of them based on total number of campaigns using the COUNTIFS() function.  https://github.com/coocoojames/Kickstarter-Analysis/blob/main/Resources/Screenshot%202.png
https://github.com/coocoojames/Kickstarter-Analysis/blob/main/Resources/Screenshot%203.png

Here, I ran into a few troubles here. I thought I could filter out the main Kickstarter workbook data with the subcategory: plays so that I didn’t have to include that in one of the criteria in my COUNTIFS() function. When I did that, first thing that happened was I got results other than 0 for my “number of canceled” column. I tried and tried, and I finally fixed my criteria in the function to be “<canceled”, instead of “canceled”. It returned the correct number of canceled campaigns. What I didn’t realize was all the other numbers were wrong for successful and failed campaigns. When I finally moved on to the line chart, I realized it was totally wrong and I had to include the criteria: plays, in my function for it to work. I learned that every time I’m dealing with large numbers, I’d better go back to the main data and double check there first.
I still don’t understand how that works because if it was retrieving data from everything on the main data, the total number of campaigns was much larger after the calculation.
7.	Made a pivot table for myself to look at just the percentage of success, fail, and cancel rates.
https://github.com/coocoojames/Kickstarter-Analysis/blob/main/Resources/Screenshot%204.png

8.	Inserted a line chart from the pivot table I made. Then added a title for the chart.
https://github.com/coocoojames/Kickstarter-Analysis/blob/main/Resources/Outcomes_VS_Goals.png

### Another possible problem encounter would be not having the correct data set to put in the first pivot table to get the right results from the main data.

#Results:
## Theater Outcomes by Launch Date
From the data based on launch dates, in May and June there are most successful campaigns. Interestingly there are also the most failed campaigns in May and second most in June. There are equal amounts of canceled campaigns but the most are in January. Based on this we can say that a theater campaign is most likely to succeed in the month of May and the most likely to be canceled in the month of January. We can also conclude that you are more likely to fail from April to August than you are in the other months.

## Outcomes based on Goals
From the data based on goal of the pledge, there is a downward success rate trend the higher the goal is. At first that is. Because when you get to campaigns that ask between $35,000 and $49,999 the success rate shot up almost as high as between $0 and $4,999. From this we can conclude that you are most likely to succeed if you ask anything between $0 to $4,999. You are most likely to fail if you ask anything between $45,000 to $49,999.

## Limitations
There are a few limitations when it comes to these conclusions, however. In terms of outcomes based on launch dates, it is clear from the line chart that typically when there are more campaigns there are more failed campaigns. I took the liberty to make a chart to filter out the plays category as well. I found that it is even more likely for plays to fail in May than for the theater category, as a whole, to fail. When you filter out just the year, you’ll see that, disregarding which month, there are more successful campaigns in 2015 than there are in any other year from 2010 to 2017. This indicates that there are other external factors.
Furthermore, when you calculate the success rate in all the months, you’ll see that even though it is true the month of May has the highest success rate, many other months actually don’t fall too far behind with most months having higher or equal to 60%.
When analyzing outcomes based on the pledge goal, a few things are noteworthy: 1. In three different ranges the lines crossed. 2. The fact that the line shot up from $35,000.  3. The number of total projects. It’s easy to understand why plays that ask for less than $1000 are more likely to succeed. But with a 50/50 chance to succeed in three other vastly different ranges, it’s hardly an indicator of how likely you would succeed based on how much you ask. With 889 projects out of 1047 being between $0 to $9,999, it’s also hard to determine whether the data is reliable especially when it comes to high-budget plays. Only one campaign ever asked between $45,000 to $49,999 and failed, does that you would?

## Suggested Graphs
Overall, I would suggest doing another line chart based on year. I would suggest a line chart based on success rate of each month. Then I would suggest a line chart of success and fail rate based on each month across all categories to compare.
I would suggest a line chart of success and fail rate based on pledge goal across all categories to compare. Compare line charts based on pledge goal across different countries. Then a line chart based on pledge goal filtered with just theater to compare.
