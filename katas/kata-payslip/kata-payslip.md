# Payslip Kata

In this code kata, we have several levels of difficulty.

## The payslip rules

* Pay period = per calendar month   
* Gross income = annual salary / 12 months   
* Income tax = based on the tax table provided below    
* Net income = gross income - income tax    
* Super = gross income x super rate    
* All calculation results should be rounded to the whole dollar. If >= 50 cents round up to the next dollar increment, otherwise round down.   

----

## Basic Payslip Kata

When supplied employee details: first name, last name, annual salary (positive integer) and super rate (0% - 50% inclusive), payment start date, generate pay slip information with name, pay period,
gross income, income tax, net income and super.

The following rates for 2017-18 apply from 1 July 2017:

| Taxable Income     | Tax on this Income                         |
|--------------------|--------------------------------------------|
| $0 - $18,200       | Nil                                        |
| $18,201 - $37,000  | 19c for each $1 over $18,200               |
| $37,001 - $87,000  | $3,572 plus 32.5c for each $1 over $37,000 |
| $87,001 - $180,000 | $19,822 plus 37c for each $1 over $87,000  |
| $180,001 and over  | $54,232 plus 45c for each $1 over $180,000 |

For example, the payment in March for an employee with an annual salary of $60,050 and a super rate of 9% is:

* pay period = Month of March (01 March to 31 March)  
* gross income = 60,050 / 12 = 5,004.16666667 (round down) = 5,004  
* income tax = (3,572 + (60,050 - 37,000) x 0.325) / 12 = 921.9375 (round up) = 922  
* net income = 5,004 - 922 = 4,082  
* super = 5,004 x 9% = 450.36 (round down) = 450  

### Your Task

Generate a basic payslip application. You should be able to enter a single employee details, the application will generate a basic payslip.

Everything will be done via the console.

An example run through of of how this console would be...

~~~
Welcome to the payslip generator!

Please input your name: John  
Please input your surname: Doe  
Please enter your annual salary: 60050
Please enter your super rate: 9
Please enter your payment start date: 1 March
Please enter your payment end date: 31 March

Your payslip has been generated:

Name: John Doe  
Pay Period: 01 March – 31 March  
Gross Income: 5004  
Income Tax: 922 
Net Income:4082 
Super: 450  

Thank you for using Payslip!
~~~

----

## Taking it to the next level...variations

There are a number of possible customizations that can be added as well.

----

### Loading from CSV File  

Adjust your payslip generator to load csv files.

It should be able to process the following csv input and generate the expected output. 

Example File Formats:  

* [Sample Input File](sample_input.csv)  
* [Sample Output File](sample_output.csv)  

----

### Adding a Front End

Put a web front end on the application. Users should be able to select a CSV file to upload and evaluate.  
