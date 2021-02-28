# Kickstarting with Excel

## An Analysis of Kickstarter Campaigns

### Background
Louise's play _Fever_ was close to hitting its fundraising goal in a short amount of time. She wants to understand how different campaigns fared based on their launch dates and fundraising goals. 

### Purpose
The purpose of this analysis was to help Louise answer her question. Using visualizations from the Kickstarter dataset, I analyzed how launch dates and fundraising goals affected four outcomes: successful, failed, live, and canceled. This analysis will help Louise determine the success of her fundraising efforts for _Fever_ and hopefully provide insights for her future fundraising campaigns.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
#### Overview
The first analysis was to determine if the month of launch date impacted the outcome of **theater** fundraising campaigns. 
#### Process 
To complete this analysis, I created a pivot table using the Kickstarter dataset. I used the **parent category** and **years** fields as my filters, moved **date created conversion** to rows, **outcomes** to columns, and **outcomes** again to values. See the image below for the pivot table field selection:

![Pivot_Table_Fields.PNG](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Pivot_Table_Fields.PNG)

I double-checked that the value field settings of outcomes were set to _count of outcomes._

![Count_of_Outcomes.PNG](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Count_of_Outcomes.PNG)

After I created the pivot table, I noticed the dates row labels showed up as mm/dd/yyyy. After doing a quick search on Google, I learned I could group them in various increments of time. I chose **months** as this was the easiest way to spot outcome trends from 7 years-worth of fundraising campaigns.

![Grouping_Rows.png](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Grouping_Rows.png)

After setting the pivot table field, I filtered the parent category show to only **theater** fundraising campaigns. Then, I filtered out **live** campaigns, as those would show ongoing or incomplete ones, and sorted the outcome column labels in descending order: successful, failed, and canceled. By grouping the **date created conversion** field, the months row label was already sorted chronologically (Jan. - Dec.).

With the correct filters and sorting, I was confident that a pivot chart would display the theater outcomes by the month of the launch date. To explain the data I was showing in the chart, I added the title **Theater Outcomes Based on Launch Date**. I then saved the chart as a .png file, uploaded it to my _Resources_ folder in my repository, and added it below: 

![Theater_Outcomes_vs_Launches](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

#### Challenges

As mentioned in the previous section, I encountered difficulty displaying the **date created conversion** field as **months**. When I created my pivot table, the **date created conversion** column showed as mm/dd/yyyy. This caused each specific date to count outcomes, as shown below: 

![Long_Date](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Long_Date.PNG)

After a few Google searches, I learned that I can right-click and group Row Labels and to display as **months**. This corrected the issue in my pivot table and allowed for cleaner data analysis in my pivot chat. The grouping Row Labels solution is displayed below:

![Grouping_Rows.png](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Grouping_Rows.png)

### Analysis of Outcomes Based on Goals
#### Overview

The second analysis was to determine if fundraising goals impacted the outcome of the Kickstarter campaigns with the subcategory **plays**.

#### Process 

To begin my analysis of outcomes based on goals, I added a new sheet to my Kickstarter workbook and split up fundraising goals ranges in rows, and categorized outcomes in columns, as shown below:

![Blank_Outcomes_Goals](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Blank_Outcomes_Goals.PNG)

After establishing the proper table format, I needed a way to count the number of successful, failed, and canceled fundraising campaigns in each goal range. Using a COUNTIFS formula, I filtered three columns of Kickstarter data to populate **Number Successful**, **Number Failed**, and **Number Canceled**. I used the following formula for cell B2: =COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "successful", Kickstarter!$O:$O, "plays"). See completed chart with cell B2's formula displayed:

![Complete_Outcomes](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Complete_Outcomes.PNG)

To complete the rest of **Number Successful**, I changed the numeric value of the goal filter. See the filter change for cell B2 circled in red:

![Outcomes_OneFilter](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_OneFilter.PNG)

Moving down 1 row to **Goal 1000 to 4999** and across to **Number Failed**, I needed to change the goal and outcome filters. See the two-filter change for cell B3 circled in red:

![Outcomes_TwoFilters](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_TwoFilters.PNG)

I repeated a combination of one- and two-filter changes to complete the rest of the columns **Number Successful**, **Number Failed**, and **Number Canceled**. Once those three columns were complete, I used a SUM formula for **Total Projects**. 

![Total_Projects](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Total_Projects.PNG)

Columns **Percentage Successful**, **Percentage Failed**, and **Percentage Canceled** required a simple division and percentage conversion calculation. See the example from the **Percentage Successful** column:

![Percentage_Successful](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Percentage_Successful.PNG)

I then created a line graph pivot chart to display with the percentage columns to show **Percentage Successful**, **Percentage Failed**, and **Percentage Canceled** at each fundraising goal tier.

![Outcomes_vs_Goals](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

#### Challenges

The hardest part of this analysis was getting the countifs formula correct. I looked back at the module exercises and searched on Google how to write the filters correctly. It took some trial and error to get the pivot table numbers correct. After a couple of tries, I successfully wrote the first two filters =COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "successful"). I was feeling accomplished but then realized it still wasn't the correct formula. I went back into the assignment directions and figured out that I had missed the third filter, to only include the subcategory **plays**. I added the following to the end of my formula to correct it: Kickstarter!$O:$O, "plays". Still, my numbers were slightly off. After reviewing the verbiage of the goals, 1000 to 4999, for example, I missed including the numbers 1000 and 4999 in my formula. I corrected it by adding an "=" sign to range >=1000 and <=4999. I then added equal signs to every other countifs formula except the **Less than 1000** goal. Now, my pivot table was showing the correct outcome numbers and the correct pivot chart.

### Other Challenges and Difficulties Encountered

I encountered some difficulty uploading images to Github and hosting them in this document. As you can see from my commit count, it required much trial and error. I solved the issue by searching for solutions on Stack Overflow and a few other random sites. I added all image screenshots to the Resources folder in my Kickstarter Analysis and then hard-coded them in. I feel like I have the hang of it now, as demonstrated in this document. 

## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?

My analysis on **Theater Outcomes based on Launch Date** showed that May had the most Kickstarter campaigns begin in May. May also had the highest number of successful campaigns. However, I needed to dig a little deeper for Louise if I wanted to recommend May as the best time of year to launch a campaign. I wanted to see the success rate by month, so I calculated the percentage of successful campaigns by month. Using the **Theater Outcomes based on Launch Date** pivot table data, I divided the successful count by the **Grand Total**. The calculations showed that May had the highest success rate with **67%** and the highest successful count.

![May_Success](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/May_Success.PNG)

I would recommend Louise launch a fundraising campaign in May first. Her next best option is June, which had a success rate of **65%**. I wouldn't recommend Louise launch a campaign in December, because it had the lowest success rate by far. For comparison, the month with the second-lowest success rate was October with **57%**.

### What can you conclude about the Outcomes based on Goals?

My analysis on **Outcomes based on Goals** gives Louise insight into how other plays fared based on their fundraising goal. Plays within the goal range **less than 1000** saw the highest success rate with 76%, followed by **1000 to 4999** with 73%. Plays saw the lowest success rate when their fundraising goals fell in the highest ranges: **45000 to 49999** with 0% and **Greater than 50000** with 17%. While these were the least successful fundraising levels, the data was limited. Combined, there were only 13 plays (accounts for 1.2% of plays) with goals greater than 45000, as opposed to 720 plays (accounts for 69% of plays) with goals from less than 4999. 

While the **less than 1000** level saw the highest success rate with 76%, plays within that range only accounted for 18% of plays. I would recommend Louise set her next play's fundraising goal between **1000 to 4999** because more than half of the play data (51%) fell within the range and it also saw the second-highest success rate with 73%.

### What are some limitations of this dataset?

There is limited information on how these fundraising campaigns were performed. As someone who has managed fundraising strategies for political campaigns, I'd like to know if the campaigns raised money online, from in-person solicitation, or phone-banking. It would be interesting to see what method had the highest success rate. This information would help Louise pinpoint her fundraising strategy and possibly if she needed to learn how to say, phone-bank successfully.   

### What are some other possible tables and/or graphs that we could create?

It would be helpful for Louise to see how the average donation amount impacted the outcome of fundraising campaigns. This analysis would help her set her fundraising strategy. With this information, she could see what type of donor: small-, medium-, or large-donors translates into a successful outcome. During the campaign, she could recommend donors to contribute $xx.  For example, campaigns with what I would categorize as a medium-dollar average donation **50 to 99** and **100 to 149** were 82% and 85% successful, respectively, and accounted for 47% of all campaign data. 

![Outcomes_AvgDonation_Chart](https://github.com/dwwatson1/kickstarter-analysis/blob/main/Resources/Outcomes_AvgDonation_Chart.png)

Further analysis shows that Louise should set her fundraising goal to **1000 to 4999** and cater her fundraising strategy to maximize medium-dollar donations. Let's say she sets her goal average donation to $75 and overall fundraising goal to $3,000. She now knows she only needs thirty $75 donations, which makes the fundraising goal seem more manageable and attainable. During the course of the campaign, she will be able to monitor her average donation and donation total and make adjustments as needed.


