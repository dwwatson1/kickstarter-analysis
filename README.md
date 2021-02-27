# Kickstarting with Excel

## An Analysis of Kickstarter Campaigns

### Background
Louise's play _Fever_ was close to hitting its fundraising goal in a short amount of time. She wants to understand how different campaigns fared based on their launch dates and fundraising goals. 

### Purpose
The purpose of this analysis was help Louise answer her question. Using visualizations from the Kickstarter dataset, I analyzed how launch dates and fundraising goals affected four outcomes: successful, failed, live, and canceled. This analysis will help Louise determine the success of her fundraising efforts for _Fever_ and hopefully provide insights for her future fundraising campaigns.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
#### Overview
The first analysis was to determine if the month of launch date impacted the outcome of **theater** fundraising campaigns. 
#### Process 
To complete this analysis, I created a pivot table using the Kickstarter dataset. I used the **parent category** and **years** fields as my filters, moved **date created conversion** to rows, **outcomes** to columns, and **outcomes** again to values. See image below for the pivot table field selection:

![Pivot_Table_Fields.PNG](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Pivot_Table_Fields.PNG)

I made sure to double check that the value field settings of outcomes in values was set to _count of outcomes._

![Count_of_Outcomes.PNG](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Count_of_Outcomes.PNG)

After I created the pivot table, I noticed the dates row labels showed up as mm/dd/yyyy. After doing a quick search on Google, I learned I could group them by various increments of time. I chose **months** as this was the easiest way to spot outcome trends from 7 years-worth of fundraising campaigns.

![Grouping_Rows.png](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Grouping_Rows.png)

After setting the pivot table field, I filtered the parent category show to only **theater** fundraising campaigns. Then, I filtered out **live** campaigns, as those would show ongoing or incomplete ones, and sorted the outcome column labels in descending order: successful, failed, and canceled. By grouping the **date create conversion** field, the months row label was already sorted chronologically (Jan. - Dec.).

With the correct filters and sorting, I was confident that a pivot chart would clearly display the theater outcomes by month of launch date. To explain the data I was showing in the chart, I added the title **Theater Outcomes Based on Launch Date**. I then saved the chart as a .png file, uploaded it to my _Resources_ folder in my repository, and added it below: 

![Theater_Outcomes_vs_Launches](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

#### Challenges

As mentioned in the previous section, I encountered difficulty displaying **date create conversion** as **months**. When I created my pivot table, **date create conversion** showed as mm/dd/yyyy. This caused each specific date to count outcomes, as shown below: 

![Long_Date](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Long_Date.PNG)

After a few Google searches, I learned that I right click and group Row Labels and to display as **months**. This corrected the issue in my pivot table and allowed for cleaner data analysis in my pivot chat. The grouping Row Labels solution is displayed below:

![Grouping_Rows.png](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Grouping_Rows.png)

### Analysis of Outcomes Based on Goals
#### Overview

The second analysis was to determine if fundraising goals impacted the outcome of the Kickstarter campaigns with the subcategory **plays**.

#### Process 

To begin my analysis of outcomes based on goals, I added a new sheet to my Kickstarter workbook and split up fundraising goals ranges in rows and categorized outcomes in columns, as shown below:

![Blank_Outcomes_Goals](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Blank_Outcomes_Goals.PNG)

After establishing the proper table format, I needed a way to count the number of successful, failed, and canceled fundraising campaigns in each goal range. Using a COUNTIFS formula, I filtered three columns of Kickstarter data to populate **Number Sucessful**, **Number Failed**, and **Number Canceled**. I used the folllowing forumula for cell B2: =COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "successful", Kickstarter!$O:$O, "plays"). See completed chart with cell B2's formula displayed:

![Complete_Outcomes](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Complete_Outcomes.PNG)

To complete the rest of **Number Successful** , I changed the numeric value of the goal filter. See the filter change for cell B2 circled in red:

![Outcomes_OneFilter](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_OneFilter.PNG)

Moving down 1 row to **Goal 1000 to 4999** and across to **Number Failed**, I needed to change the goal and outcome filters. See the two-filter change for cell B3 circled in red:

![Outcomes_TwoFilters](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_TwoFilters.PNG)

I repeated a combination of one- and two-filter changes to complete the rest of the columns **Number Successful**, **Number Failed**, and **Number Canceled**. Once those three columns were complete, I used a SUM forumula for **Total Projects**. 

![Total_Projects](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Total_Projects.PNG)

Columns **Percentage Sucessful**, **Percentage Failed**, and **Percentage Canceled** required a simple division and percentage conversion calculation. See example from the **Percentage Sucessful** column:

![Percentage_Successful](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Percentage_Successful.PNG)

I then created a line graph pivot chart to displays with the percentage columns to show **Percentage Sucessful**, **Percentage Failed**, and **Percentage Canceled** at each fundraising goal tier.

![Outcomes_vs_Goals](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

#### Challenges

### Other Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
