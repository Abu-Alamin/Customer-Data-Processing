# Customer-Data-Processing

## Context
This project is designed to evaluate the ability to read and write file formats of common types used in Data Science, and to manipulate complex data into different representations. The tasks provided here are indicative of Data Pre-processing workloads which are common to all Data Science projects. The techniques learned and evaluated in this module will prepare for further theoretical and applied topics later on in the programme, where you will further develop your skills.
This assignment makes use of an extensive collection of mocked data. These have been generated with some resemblance to real world values and distributions, including some relations between data elements.
Whilst teaching, both asynchronous and synchronous, stops for this module by Teaching Week 4, ad-hoc support will be available until submission of the assignment on the MS Teams site.

## Background
You have been given a collection of data from a company wishing to process its customer records for business purposes (acw_user_data.csv). The existing systems in-place at the company only export to a CSV file, and this is not in an appropriate format for analysis. You have been given the task of preparing this data for further analyses by your colleagues within the company, including representation changes, filtering, and deriving some new attributes / metrics for them.
These data include attributes such as first name, second name, credit card number, marital status, and even contains data on the customer’s car. The number of records provided is significant, and therefore it is expected that solutions are robust to varying types of data, and varying values, offering a programmatic solution.

## Tasks

### Data Processing 

Using standard python (No pandas / seaborn) with default libraries (os, sys, time, json, csv) you have been given the following tasks:

1. Read in the provided ACW Data using the CSV library.

2. As a CSV file is an entirely flat file structure, we need to convert our data back into its rich structure. Convert all flat structures into nested structures. These are notably:
a. Vehicle - consists of make, model, year, and type
b. Credit Card - consists of start date, end date, number, security code, and IBAN.
c. Address - consists of the main address, city, and postcode.

   For this task, it may be worthwhile inspecting the CSV headers to see which data columns may correspond to these above.
   Note: Ensure that the values read in are appropriately cast to their respective types.

3. The client informs you that they have had difficulty with errors in the dependants column. Some entries are empty (i.e. “ “ or “”), which may hinder your conversion from Task 2. These should be changed into something meaningful when encountered.
Print a list where all such error corrections take place.
E.g. Problematic rows for dependants: [16, 58, 80, 98]

4. Write all records to a processed.json file in the JSON data format. This should be a list of dictionaries, where each index of the list is a dictionary representing a singular person.

5. You should create two additional file outputs, retired.json and employed.json, these should contain all retired customers (as indicated by the retired field in the CSV), and all employed customers respectively (as indicated by the employer field in the CSV) and be in the JSON data format.

6. The client states that there may be some issues with credit card entries. Any customers that have more than 10 years between their start and end date need writing to a separate file, called remove_ccard.json, in the JSON data format. The client will manually deal with these later based on your output. They request that you write a function to help perform this, which accepts a single row from the CSV data,and outputs whether the row should be flagged. This can then be used when determining whether to write the current person to the remove_ccard file.

7. You have been tasked with calculating some additional metrics which will be used for ranking customers. You should create a new data attribute for our customers called “Salary-Commute”. Reading in from processed.json:
a. Add, and calculate appropriately, this new attribute. It should represent the Salary that a customer earns, per mile of their commute.
  i. Note: If a person travels 1 or fewer commute miles, then their salary-commute would be just their salary.
b. Sort these records by that new metric, in ascending order.
c. Store the output file out as a JSON format, for a commute.json file.

7. You have been tasked with calculating some additional metrics which will be used for ranking customers. You should create a new data attribute for our customers called “Salary-Commute”. Reading in from processed.json:
a. Add, and calculate appropriately, this new attribute. It should represent the Salary that a customer earns, per mile of their commute.
  i. Note: If a person travels 1 or fewer commute miles, then their salary-commute would be just their salary.
b. Sort these records by that new metric, in ascending order.
c. Store the output file out as a JSON format, for a commute.json file.
