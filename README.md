# DS-Project-3
GA Python Programming
July 23, 2020

# Introduction
For this project we will analyze student loan data to understand why loan values have been rising over time. To start, we collected the Direct Loan Program data of the institutions who have taken distributions from 2012 to 2019 inclusive. We have gathered annualized data to look at YoY trends.  

Loan data source: https://studentaid.gov/data-center/student/title-iv
Individual Files: Loan Volume, Direct Loan Program (Q2 files have EOY data)
Tab: Award Year Summary

The following is a description of the steps taken and should mirror what you find in the ShobhaProject3DS.ipynb file.  

# Libraries
Here we will see all the libraries imported for later use:
  Pandas
  Matplotlib
  Plotly Figure Factory
  Numpy

# Data Import & Join
For each of the files 2012 to 2019, the header comes in two rows. For example, we see 5 fields [Recipients, # Loans Originated, $ Loans Originated, # Disbursements, $ Disbursements] repeated 5 times for each Direct Loan grouping [Subsidized, Unsubsidized Undergraduate, Unsubsidized Graduate, Parent Plus, Grad Plus].

To work around this we'll do the following: 
1) Import the file using read_excel
2) Remap all the column names to indicate mesh the fields & their respective subgroupings and add the year to each record
3) Join all 8 tables together to make a master dataframe called "loan"

# Data Cleaning
Throughout the analyses, we found a few areas where we could clean the data so we grouped them in this section. 
1) We remapped all dashes to 0 so we can perform aggregate functions across the int & float fields. 
2) We cleaned the State column to read a 2 letter US state code or Foreign for all non-US based institutions.
3) We cleaned up the School Type fields to be consistent year to year.
4) We changed the data types of most fields (28/30), again to perform aggregate functions later.

# Data Exploration
Now we are ready to ask questions of the data.

Q1A) How many unique schools participated in the Title V Direct Loan Program Per Year?
Q1B) Let's visualize this distribution.
Q2A) What is the total $ distribution over the years?
Q2B) Define 3 functions for formatting currency: billion, million, thousand, and dollar.  We applied these through the rest of the answers/data frames for readability.
Q3A) Let's see the SUM of each disbursement bucket by year.
Q3B) Let's also visualize this one in a stacked bar chart.
 Q4) Let's see the trend of [$ Disbursements / Recipients] by bucket and by year.
 Q5) Let's see the MAX of each disbursement bucket by year.
 Q6) Let's see the MIN of each disbursements bucket by year. 
Q7A) Let's see the MEAN of each disbursements bucket by year.
Q7B) Let's clean out 0's from the averages to see if the trends look differenet.
 Q8) Let's see the unique count of schools by School Type and by Year. 
 Q9) Let's see how the top 5 states rank by school count for 2012 and 2019.

# Findings
We find a few trends that differ from our initial hypotheses that school loans are rising YoY.  
1) School counts participating in the Title IV program are decreasing YoY.
2) Total loan disbursements for 3 out of 5 buckets are decreasing YoY. The total loan values for Grad Plus and Parent Plus are rising YoY.
3) The dollars per recipient has not changed dramatically YoY.
4) The max dispursement per year follows the same treand as total loan disbursements. Three buckets have decreased YoY and Grad Plus & Parent Plus saw increases. 
5) US Schools are declining in participation whereas Foreign school participation in the Title IV program is on the rise. 
6) US State participation has not changed dramatical from 2012 to 2019.


# Summary
The loan data indicates that loan volumes under the Title IV program is in decline, outside of Parent and Grad loans awards, but tuition prices are on the rise. More areas to research would be the potential rise of cash payments, alternative federal sources of loans, alternative private sources of loans. 

Tuition Trend Data: https://nces.ed.gov/fastfacts/display.asp?id=76



