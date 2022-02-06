# An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter data to uncover trends.

## Overview of Project
The purpose of this analysis was to identify trends related to the outcomes of a Kickstarter campaigns. In this data, there are many metrics tracked including those related to financial goals, amount pledged, length of campaign, type of campaign and more. 

### Purpose
The purpose of this analysis was to inform the client whether a campaign's success may be correlated to the launch date and finanical goals for amount of money raised.  

## Analysis & Challenges

### Analysis of Outcomes Based on Launch Date
In the analysis of the Kickstarter data, I added additional columns to the dataset enabling further analysis of some data already provided. First, Category and Subcategory were grouped together, by separating this information into two columns (Parent Category and Subcategory), I was able to narrow the analysis to just focusing on theatre (Parent Category) and plays (Subcategory), as requested by the client. Additionally, I converted the Date from Unix timestamps to the more readable, MMDDYYYY, using the formula =(((J2/60)/60)/24)+DATE(1970,1,1) in the Date Created Conversion and Date Ended Conversion columns. This allowed me to analyze the data based on the month (and year, if desired) for when the campaign was launched.  

After the data was organized, I created a pivot table for the Parent Category. This pivot tables displays the count of each outcome (“failed,” “canceled,” or “successful”) for each month a campaign was launched. I added the filters for Parent Category and Years, allowing me to narrow my search to the desired campaign type, theatre. Lastly, I created a pivot chart (“Theater Outcomes Based on Launch Date”), visualizing how the three outcomes changed (or didn't change) based on the calendar month (all data compiled, 2009-2017). If the client would like to filter for certain years or specific categories, they can do so by selecting the desired variable(s) in the filter dropdowns.  

### Analysis of Outcomes Based on Goals
To analyze the outcomes of the Kickstarter campaigns by its fundraising goals, I created a new sheet, grouping the fundraising goals into twelve intervals in roughly $5000 increments (less than $1000, $1000-$4999, $5000 to $9999, ..., $5000 or more). By using the COUNTIFS formula in Excel, I pulled the number of campaigns whose outcome was successful, failure, or cancelation, for each of the twelve intervals. I then calculated the percentage of successful, failed, and canceled campaigns. 

Example code for number of successful play Kickstarter campagins with fundraising goal of $10000 to $14999 (Result = 39): 
=COUNTIFS(Kickstarter!$D:$D, ">=10000",Kickstarter!$D:$D, "<=14999", Kickstarter!$F:$F, "successful",Kickstarter!$R:$R, "plays")

After obtaining the data needed, I created a line chart displaying the fluctuations in outcome percentage for each of the fundraising goal intervals. This allows the client to easily identify, fundraising goals that lead to more successful, failed, or canceled campaigns.

### Challenges and Difficulties Encountered
As I have used pivot tables in the past, this task did not face outstanding challenges. That said, when performing the analysis of outcomes based on goals, I initially missed the clients request for analysis of plays. This affected the COUNTIFS formula used, and ultimately the line graph, that displayed different results than intended. I remedied this by adding the additional criteria.  

## Results

* What are two conclusions you can draw about the Outcomes based on Launch Date?

Campaigns launched in May (and early summer months) were by far the most successful. In contrast, December was the least successful. From 2009 to 2017, May campaigns were    three times more likely to be successful than campaigns launched in December. Summer months in general have the most campaigns launched and most campaigns launched        successfully. 

Further, the number of cancelled campaigns is not corelated to the month for which they are launched. On average, canceled campaigns average 3.36 per month with a standard deviation of 1.43 indicating the means data are clustered around the mean. 

* What can you conclude about the Outcomes based on Goals?

Play campaigns with fundraising goals below $1000 have the highest likelihood of being successful. After a campaign surpasses $5000, the likelihood for a successful play campaign continuously decreases. 

That said, there a campaign has a goal of $35000 to $44999, the campaign has a staggering 67% percentage of successful campaigns. If you look at the data $0 to $34999, the data is pretty linear, indicating that projects within this budget should keep below $5000 for a higher probability for success. As the goal continues to surpass $5000, the liklihood of success decreases. For the intervals $35000 to $50000+, the data suggests the same. For most successful play campaigns, campaign organizers should set a goal between $35000 and $44999 for a higher liklihood of successful campaigns. If they go above $44999, their campaign is less likely to be successful. 

The two linear patterns found within the analyzed data suggests that campaign organizers should group their campaigns into low or high goal ranges. Campaign organizers should, in general, keep their goals to under $1000 for the most successful campaigns. If they have a larger scale project, the campaign organizers should set a goal between $35000 and $44999 for a higher likelihood of success. 

* What are some limitations of this dataset?

Within this data set, it would have been helpful to know how much the campaign needed to raise along with how much funding they already had prior to starting the campaign. This would have been helpful to determine if some of the reasons these campaigns failed was due to fear of investors if the campaign does not have any money to begin work. 

* What are some other possible tables and/or graphs that we could create?

As we look at this data more, I am interested in determining if the average donation or number of backers affected the outcome of the campaign. Additionally, I'd also like to look at the average lengths for the campaigns to see if this correlates to an outcome. Many of the campaigns received significant funding but ultimately failed. Further analysis can potentially identify any tips for campaign starters to set appropriate strategy for their campaigns.
