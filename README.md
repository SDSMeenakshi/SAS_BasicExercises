# SAS_BasicExercises
Homework 1
1.	Visit one of the stores that sells textbooks.  For 10 or more textbooks, record the department abbreviation and the course number (for example ISM 6930), the price of a new textbook, and whether the book is required, recommended, or optional.  Create and print a SAS dataset with this information.  Turn in the program, the log file, and the output. 
ANS:
CODE:
DATA textbooks;
INPUT CourseInfo $ 1-8 Price $ 10-12 Status $ 14-24;
DATALINES;
ISM 6000 100 RECOMMENDED
ISM 4567 200 OPTIONAL
ISM 4000 400 MANDATORY
ISM 3467 150 RECOMMENDED
ISM 2000 250 OPTIONAL
ISM 9000 100 RECOMMENDED
ISM 4537 200 OPTIONAL
ISM 4700 400 MANDATORY
ISM 3487 150 RECOMMENDED
ISM 2340 250 OPTIONAL
;
PROC PRINT DATA=textbooks;
RUN;


2.	Find some soft-drink dispensing machines on campus.  Record the following information about 10 or more beverages: Name the beverage, type of container dispensed (can, bottle, juice box, paper cup), price, and whether that drink was sold out when you visited the machine.  Use SAS to create and print a dataset with this information.  Turn in the program, the log file, and the output. 
ANS:
CODE:
DATA softdrinks;
INPUT BeverageName $ 1-5 ContainerType $ 7-16 Price 18-21 Sold $ 23;
DATALINES;
Fanta Can        1.15 Y
Coke  Can        1.15 N
Cola  Paper Cup  2.30 Y
Lime  Bottle     1.45 N
Cheri Paper Cup  1.23 N
Mochi Can        1.15 N
Pepsi Can        1.15 N
Dew    Paper Cup 2.30 Y
Fresh Bottle     1.45 N
Lemon Juice Box  2.39 N
;
PROC PRINT DATA=softdrinks;
RUN;

3.	Get a copy of a local newspaper or the campus newspaper and find the advertisements for apartment housing in the classified section.  Make and print a SAS dataset with the following information about 10 or more apartments: Number of bedrooms (usually abbreviated BR in the ads), number of bathrooms (abbreviated BA), monthly rent in dollars, and the phone number to call for more information.  Turn in the program, the log file, and the output. 
ANS:
CODE:
DATA apartments;
INPUT BR 1 MonthlyRent 3-5 Phone 7-16;
DATALINES;
2 760   8135467890
3 800   8134567890
2 1000  8134567892
2 750   8135468890
3 800   8134569890
2 1100  8134567892
2 760   8135464890
3 850   8134567890
2 1200  8134587892
2 1300  8134537892
;
PROC PRINT DATA=apartments;
RUN;

4.	For each of the following terms, tell whether that term could be accepted by SAS as a variable name.  If not, describe why SAS could not accept it. 
•	DOLLARS$ : Not acceptable because $ is not allowed
•	DIAMETER : This is acceptable  
•	8Y : This is not acceptable because it begins with digit
•	TREATMENT : This is acceptable
•	_PPX4T_G : This is acceptable

5.	For each of the following terms, tell whether that term could be used as the name of a SAS dataset.  If not, tell why SAS could not use it. 
•	1982DATA : Not acceptable because it begins with number
•	DATA#1 : Not acceptable because it includes special character # in it
•	D_A_T_A_ : This is acceptable
•	TRIALDATA : This is not acceptable because its more than 8 characters
•	BARNEY : This is acceptable

6.	The following passage appears on page 70 of High School Basketball Rules 

It has been reported that when using computers to keep statistics, etc., the numbers 0 and 00 are treated as a single number.  The action of the committee simply decrees that beginning in (the year) 2000 a team’s squad list shall not contain both Numbers 0 and 00.  One of the two may be used, but not both.  The solution for teams would be to purchase shirts with either one or the other, but not both numbers.

Suppose that a team has players with Numbers 0 and 00, and you want to keep track of the team’s statistics using SAS.  Write an example SAS program with fictional data to show one way in which the two players could be identified as a 0 and 00, respectively.
ANS:
CODE:
DATA players;
INPUT Team_Name $ 1-5 Player_Name $ 7-9 Jersey_Number $ 11-12 Score 14-16;
DATALINES;
Team0 abc 0  209
Team0 def 10 30 
Team0 ghi 00 40 
Team1 abd 0  300
Team1 jfk 56 250
Team1 mnp 00 200
Team1 klm 67 290
;
PROC PRINT DATA=players;
PROC freq DATA=players;
tables Jersey_Number;
RUN;

7.	Identify which of the following variable name are valid SAS names: 
Height: Valid
HeingtInCentimeters: Valid
Height_in_centimeters: Valid
Wt-Kg: Invalid because it has a hyphen
X123y456: Valid
76Trombones: Invalid because it begins with a number
MiXedCasE: Valid

8.	In the following, classify each data set name as valid or invalid. 
Clinic: Valid
clinic: Valid
work: Valid
hyphens-in-the-name: Invalid because it has hyphens and more than 8 characters
123GO: Invalid because it begins with a number
Demographics_2006: Valid

9.	You have a dataset consisting of Student ID, English, History, Math and Science test scores on 10 students. 
a.	The number of variables is : 5
b.	The number of observations is : 10

10.	True or false: 
a.	You can place more than one SAS statement on a single line.  True
b.	You can use several lines for a single SAS statement.  True
c.	SAS has three data types: character, numeric, and integer.  False
d.	OPTIONS and TITLE statements are considered global statements. True

11.	What is the default storage length for SAS numeric variables (in bytes)? : 8 bytes

