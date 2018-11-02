---
layout: default
permalink: /about/
title: About 
---

#Welcome to the Hydrae_Project wiki

The project is meant to be worked on for the Business Intelligence, Analytics, and Data team within Corporate Services section of the Treasury Board of Canada Secretariat. The current project team Members are:
1. Cathy Abrera - Cathy.Abrera@tbs-sct.gc.ca - Team leader
2. Roy Angelo Saavedra - RoyAngelo.Saavedra@tbs-sct.gc.ca - Data Analyst
3. Byron Clairoux - Bryron.Clairoux@tbs-sct.gc.ca - Team leader
4. Madeleine Imboden - Madeleine.Imboden@tbs-sct.gc.ca - Database Analyst
5. Daming Xu - Daming.Xu@tbs-sct.gc.ca - Techincal Advisor
***

The current development environment is the Microsoft Azure Data Science Virtual machine. I'm currently using Jupyter Lab Alpha to work with analysis, and construct pre-processing pipeline. I had tested Data bricks 

The current goal of the project is to detect over spending of a department based on various features/ characteristics of the department. We had originally constructed a model and framework on the Hydrae data using two existing approaches 
1. Sentiment Analysis with NLTK. 
2. CART Model using Azure ML Studio

# The Data 

The dataset that we are analyzing is the historical data of every Federal Department over the last three years of data. 
The purpose of analyzing this data is to gather insights on Federal Departments spending habits.This data set contains a binary variable that flags whether not a Department will over spend in a given Fiscal year. The variables are defined as
Lapse10,Lapse20,Lapse30, and Overspend. Where lapse implies their expenditures exceeded it's available authorities amount. 
1. Overspend - The primary binary label for the data set. 
2. Lapse10 - 10% Spent over Budget binary label 
3. Lapse20 - 20% Spent over budget binary label
4. Lapse30 - 30% Spent over budget binary label 


We are working with three main data sets. I have come across the following data sets that are required for the analysis and help constructing a model. 
The main data sets that contain data about expenditures, frozen
1. Full time employee and planning organization FTEPO 
2. Planned Full time equivalent program organization - Detailed 
3. Planned-expenditure-program organization -Detailed 
4. Planned expenditure program organization - PEPO
5. Main Data Set called ACE only by Year and Quarter ( requires a Fiscal year only ) 
6. Textual Data scraped from 2018 html and off open-canada.ca


### Bryon's Explanation 

I’ve completed loading and doing the transforms on the three years of Hydrae data we extracted. The data output is in the file ACE_Output_for_ML.csv in the SampleData\ACE folder on the DataScience share in the VM environment.

As we’d discussed last week I have generated a set of flags for each department and fiscal year. The flags are:
•	LAPSE10 – the department lapsed at least 10% of its Available Authorities amount
•	LAPSE20 – the department lapsed at least 20% of its Available Authorities amount
•	LAPSE30 – the department lapsed at least 30% of its Available Authorities amount
•	Overspend – the department Expenditures exceeded its Available Authorities amount

These flags, and the summary amounts used to calculate them – Authorities (the Amount of Estimates and Allotments), Frozen (the amounts in Frozen Allotments, as a negative), Available (Authorities plus Frozen [Frozen is a negative value so it subtracts]), Expenditures (the Actual Expenditures amount), and the Lapse (Available less Expenditures) – have been combined with the more detail level transaction data linked by department and fiscal year.

We can start looking for trends and correlations against those flags based on the detailed information. Some of the fields we can look to see if they correlate to one of the flags being ‘Y’ include the AuthorityType, FundType, FundApplication, NoE (Nature of Expenditure), Process, Budget Type (T=Time Limited, O=Ongoing), or which Quarter the transactions were in.

The Departmental Plans are basically each department’s breakdown of planned spending, planned HR levels, and some results-oriented planning (targets for different indicators used to show the department is doing what they are supposed to be doing based on their mandate). With a lot of text wrapped around it. The Departmental Plans used to be handled by TBS and were part of the Main Estimates document many years ago but got separated out at some point and handed off to the individual departments to manage. They are tabled at roughly the same time as the Main Estimates so not much will be impacted by the Budget in them either. The financial planning numbers are typically a little different from what appears in the Main Estimates because they include a “best guess” at what the overall spending (including future Supplementary Estimates money) will be for the year.

We don’t have much say in the Departmental Plans. There was an effort about five years ago to bring the production of them into Hydrae but that project went nowhere in the end. I can probably still give you an overview of the general content that goes into them, or what went into them five years ago but talking a look I don’t think they’ve changed too much.

For the Main Estimates and the Supplementary Estimates documents, all the content, text included, comes from Hydrae. The web versions are produced from the same Crystal Reports as the PDF used for the printed version. We export the Crystal Reports to an XML file which gets run through a couple of sets of XSL Tranforms to produce accessibility-compliant HTML which we give to EMS, who in turn give it to the TBS communications team for posting on the web. So I can get you the data used for the web versions (if you don’t mind HTML tags in the text), your choice of the Crystal Reports schema XML version, the DocBook schema intermediary XML version, or the XHTML version that gets sent to the comms team.


### Madeleine Notes

This is the methodology, obstacles, and data analysis for my ML project. You already have this one, just resending so the links are in the same place. 
https://gcdocsp.tbssct.local/gcdocs/llisapi.dll/open/31929016


This is the PowerPoint I will try to update when I have time. I started explaining some of the models and put up how I edited and selected models based off of Wendy’s work. 
There are some useful links at the end that explain really well. I’m a visual person so some of it may seem redundant but I like to reference visuals. 

https://gcdocsp.tbssct.local/gcdocs/llisapi.dll/open/32050997




#### Original Pilot Project from April 18 2018
IMTD will be hosting a free 6-week pilot project for data scientists using TBS’s unclassified cloud environment.
Consider joining the pilot project for TBS’s data science workbench and offer your feedback!
#### Objective
The pilot is a fact-finding project to determine the strengths and weaknesses of selected tools that are part of TBS’s data science workbench.

#### What will you do?
We’re looking for 10 data scientists from any sector of TBS. Participants will have access to a Windows or Linux server on the cloud. There will be equal numbers of participants testing the tools on Windows and Linux

More than 10 tools will be tested, including Anaconda, PowerBI, R, Python, SQL and Visual Studio. The results will be used to finalize decisions on implementing these tools.
Reasons:

### What now - Hydrae Pilot Project

I have been working on the Hydrae Pilot project which was the first page.






[back](./)