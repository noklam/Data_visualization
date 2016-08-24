#Data Visualization with D3.js Final Project

### Author : Nok Chan
### Date: 2016/08/16

This is the final project Data Visualization with D3.js course, which is part of the Udacity Data Analyst Nanodegree.

Date set: Propser Loan Data Set (Last updated 03/11/2014)

##Data Set Description 
This data set contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others.
Metadata of the dataset can be found in: 
https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit?pref=2&pli=1#gid=0

Used skills: d3.js , R ,HTML, CSS

##Summary

This project used the d3.js library to build visualizations. The data is a subset of Prosper Data Set using R to select the interested features and output the dataset file "loandata.csv". The data is read using script written in the index.html . A line graph is used to describe the dataset and give more information about the company growth and recession.
The boxplot is aimed to demonstrate the relation between different variable to answer the question that what factor affect the loan amount and who borrow the most.

The data is from Dec 2005-2014 March, therefore the number of the count in the first and last year is significantly lower.  The original data set only have the variable for date, I use strptime()$year to extract the year and aggerate the data into year and make the line graph. It is interesting to note that the graph shows the big drop in 2008-2009, which reflected the law issue of Prosper Company. 

In general, the loan amount increased with income range, though the $0 group is a special one, which has a larger median than $1-24,999 group. It is interesting as it shows that sometimes not the richer one will borrow more.
Home Owner is another variable that added into the visualization, in all income range group, homeowner borrows more than non- homeowner.

Variables in this visualization: LoanOriginalAmount, IncomeRange,IsBorrowerHomeOwner

##Design

###Line graph

####Why Line graph?
The line graph is choosed to display the trend of the loan, which shows a increasing trend with an exception that after 2008 a recession occured and the company have encounter law issue that they are forced to stop issuing new loans. The number of loan in a year is encoded as y-axis and the time is encoded as x-axis to show the overall trends.

A tooltips is added to the line graph to give the accurate information about year and number of loan in a year to increase interaction with reader.

####Goal
There are mainly 2 goals:
1. To give a sense of the data to the reader, they can get a sense how many data in the dataset and how these data evolve with time.

2. To show the trend of the increasing trend and the recession after 2008.

###Box plot

#### Why Box Plot?
All 3 variables LoanOriginalAmount, IncomeRange, IsHomeBorrowerHomeOwner are come from the dataset directly, but I have decided to not use"Not Displayed" and "Not employed" as they does not give more information, a number of income range with 6 groups is used.

I choose box plot as I think it is the best way to demonstrate the distribution and trend of the data. There is a linear trend with loan amount and income range, it can be demonstrated by the median of each box plot. However, it will be not appropiate to only demonstrate the median, as the range also changes, the box plot is the best way to exhibit both the trend and distribution in one visualization.

Loan orignal amount is encoded as the y-axis as it is the dependent variable, while income range is encoded as x-axis as it is the independent variable.

I have use a boxplot template and modify it and change the process of reading data as the format are not the same. I also build a <svg> element at first such that everytime you click the button, it will remove the child element and build the new graph. In this way, the structure of the html will be stable, and the words originally below the graph will not change their position. Originally I delete the whole element and build up a new graph, it will make the words under the graph move after clicked.

#### Goal
A box plot is build to show the distribution of loan amount in different subset of variable. People can click the button to see loan amount in home owner group in different income range or non- home owner. I have considered to make both plot in one big graph, but after my consideration, I think it will be better that people can click with options and interact with the data. People should be able to discover that Home owner always borrow more than Non-homeowner, and loan amount increase with income range generally.

####Feedback:

I get 3 feedbacks from the Udacity Forum.


Feedback #1
MylesLeader2d
Hi @lrcnok0929

Two stylistic points about your visualization, that I think will help:

The visualizations are a different width to the text.

The page moves when you change the boxplot (i.e. when you click the boxplot button).

p.s. you should also make both visualizations the same size.


What do you notice in the visualization? 

An odd growth pattern in overall loans issued (with a large dip in 2009).


A higher median and greater variance in loan sizes between homeowners and non-homeowners.
This was easier to see after fixing the div containing the chart (i.e. when the page stopped moving).


What questions do you have about the data? 

No 

What relationships do you notice? 

The relationship mentioned above (which is clear and striking) 

What do you think is the main takeaway from this visualization? 

Homeowners, typically, borrowed more money, and their borrowing had a greater range, than non-homeowners. 

Is there something you don¡¦t understand in the graphic? 

No, it is clear and very well presented! 
Overall, a very nice presentation with a very clear story to tell!! Nice work!!

## Feedback2
michael_2201234319588h1 
@lrcnok0929,

What do you notice in the visualization?

Nice graph showing the amount of loans people have borrowed from 2007 to 2014. Although, I would probably get rid of 2014 since it is incomplete.

What questions do you have about the data?

N/A

What relationships do you notice?

I see relationship between years and number of loans borrowed.

I also see relationship between income range and people's loan original amount.

What do you think is the main takeaway from this visualization?

The main takeaway I see is the number of loans people are borrowing from 2008 to 2014.

And the other takeaway borrowers' income range for all loans borrowed and how much it seems that the higher the income, the more they will tend to borrow.

Is there something you don¡¦t understand in the graphic?

I clearly understand both graphs but I think you should somehow combine both of the two graphs to tell a main story. Maybe with showing how many loans are borrowed per year, could it be that median (or mean) income range is much lower during 2008-2009 than 2010 to 2014? That way, you can probably explain the correlation between a low volume of loans borrowers and their income range (if there is) .

Also you were trying to get your point across by comparing non-home owners and home owners....

...I would believe it would be more appropriate to use a "grouped" chart like this...

http://dimplejs.org/examples_viewer.html?id=bars_vertical_grouped

(or if you can find a grouped boxplot that would be even better.... if there exists one)

Rather having a button to switch between non-home owner and home owner graphs. This just helps see 2 things side by side on one graph. I don't want to make you do the work all over again but this is just something for next time (hopefully in your career :wink: ).

Thanks,

Can you return the favor and comment on mine?

https://discussions.udacity.com/t/p6-project-feedback-pisa-2012/183386/1

#3
georgeliu1998Forum Mentor1d
Hi @lrcnok0929,

Good work! Here are several ideas for you to consider:

Boxplots may not be the most intuitive for general readers as there can be quite some information to absorb. Consider using a bubble chart instead, and use the bubble area to represent medians of different income groups. Dimple can do this easily.
If you can use animation to make a storyboard, the comparison between home owner and non home owners may be clearer. Alternatively, you can also overlay the two groups with different colors so that the reader can easily compare the two groups.
Focusing on one main idea to explain in the text may help better communicate the point to the audience, also fix some minor gramatical and spelling errors.
Hope this helps.



Response to the feedback:
* boxplot will still be a better choice as it can shows the range and distribution. I should have mention it in text though.
* A storyboard will be a great idea for future , but it is a bit advance for me since I have no experience in d3 before, I choose to build a better version of web page using GitHub pages combined with my index.html and make some fine adjustment to improve the visualization.
* I have changes the size of visualization and make them fixed in the web, so people can compare the 2 boxplots easier.


##Reference list:

http://bl.ocks.org/jensgrubert/7789216
https://discussions.udacity.com/t/final-project-boxplot/183468/18
GitHub Pages using Merlot template

##Resource:
Prosper Loan Data Set 