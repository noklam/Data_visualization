Summary:
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

This project used the d3.js library to build visualizations. The data is subseted using R to select the interest features and output the dataset file "loandata.csv". The data is read using script written in the index.html 
The boxplot is aim to demonstrate the relation between different variable to answer the question that what factor affect the loan amount and who borrow the most.

The data is from Dec 2005-2014 March, therefore the number of count in the first and last year is siginficantly lower. This is interesting to note that the graph shows the recession of financial crisis on 2008, which have a significant drop of loan.

In general, the loan amount is increase with income range, though the $0 group is a special one, which has a larger median than $1-24,999 group. It is interesting as it shows that sometime not the richer one will borrow more.
Home Owner is another variable that added into the visualization, in all income range group, home owner borrows more than non- home owner.

Variables in this visualization: LoanOriginalAmount, IncomeRange,IsBorrowerHomeOwner

##Design

###Line graph

####Why Line graph?
The line graph is choosed to display the trend of the loan, which shows a increasing trend with an exception that after 2008 a recession occured. The number of loan in a year is encoded as y-axis and the time is encoded as x-axis to show the overall trends.

A tooltips is added to the line graph to give the accurate information about year and number of loan in a year to increase interaction with reader.

####Goal
There are mainly 2 goals:
1. To give a sense of the data to the reader, they can get a sense how many data in the dataset and how these data evolve with time.

2. To show the trend of the increasing trend and the recession after 2008.

###Box plot

#### Why Box Plot?

I choose box plot as I think it is the best way to demonstrate the distribution and trend of the data. There is a linear trend with loan amount and income range, it can be demonstrated by the median of each box plot. However, it will be not appropiate to only demonstrate the median, as the range also changes, the box plot is the best way to exhibit both the trend and distribution in one visualization.

Loan orignal amount is encoded as the y-axis as it is the dependent variable, while income range is encoded as x-axis as it is the independent variable.

I have use a boxplot template and modify it and change the process of reading data as the format are not the same. I also build a <svg> element at first such that everytime you click the button, it will remove the child element and build the new graph. In this way, the structure of the html will be stable, and the words originally below the graph will not change their position. Originally I delete the whole element and build up a new graph, it will make the words under the graph move after clicked.

#### Goal
A box plot is build to show the distribution of loan amount in different subset of variable. People can click the button to see loan amount in home owner group in different income range or non- home owner. I have considered to make both plot in one big graph, but after my consideration, I think it will be better that people can click with options and interact with the data. People should be able to discover that Home owner always borrow more than Non-homeowner, and loan amount increase with income range generally.






##Reference list:

http://bl.ocks.org/jensgrubert/7789216
https://discussions.udacity.com/t/final-project-boxplot/183468/18

##Resource:
Prosper Loan Data Set