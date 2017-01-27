# Repository: 2017-01.project-1upd.template
# Assignment #1: Python (UPDATED)

> Course: **[CS 1656 - Introduction to Data Science](http://cs1656.org)** (CS 2056) -- Spring 2017    
> Instructor: [Alexandros Labrinidis](http://labrinidis.cs.pitt.edu)  
> 
> Assignment: #1.  
> Released: January 27, 2017  
> **Due:      February 3, 2017**

### Description
This is the **first assignment** for the CS 1656 -- Introduction to Data Science (CS 2056) class, for the Spring 2017 semester (**updated** after Wunderground.com CSV data were no longer available)

### Goal
The goal of this assignment is to familiarize you with the Python programming language.

### Summary of changes from previous version
This assignment description updates the previous version in two ways:  
* we focus on just snow  
* data are downloaded using their JSON API, instead of CSV  


### What to do -- weatherbowl.py
You are asked to write a Python program, called `weatherbowl.py` that will take as input the names of two NFL teams (e.g., `Steelers` and `Patriots`), a year (e.g., `1995`), and the word `snow`, in order to determine which team "won" in terms of **total** precipitation for snow for the specified year (i.e., all 12 months), using weather data from `WeatherUnderground.com` for the  cities of the two teams. Winning means highest precipitation.  

Your program should be called as follows:  
`python3 team1 team2 year snow`   
For example: `python3 weatherbowl.py steelers patriots 1998 snow`

The information about the NFL team names and the corresponding cities is provided as a CSV file, named `NFL_data.csv`, which is included in this repository. Note that you should be matching even part of the team name, provided there is a single match, otherwise it would return an error message. For example, `Pit` or `pitt` or `Pittsburgh` or `Steelers` should all match `Pittburgh Steelers` and lead to using KPIT for the weather data. You should also ignore case.

> **Update**
> You should get the WeatherUnderground weather data using their JSON DATA API, as follows:
>
1. Go to https://www.wunderground.com/signup  
2. Provide your email, password, agree to the Terms of Service, and click "Sign up for free".  
3. After that you should receive an email from wunderground. Click on "Validate Your Email" button in the email.  
4. Go to the webpage https://www.wunderground.com/weather/api/d/pricing.html  
5. Select STRATUS PLAN and Developer option (the one with Monthly Pricing of $0) and click the "Purchase Key" button.  
6. Fill out the form with your name and email, for Project Name you can specify Data Science Assignment #1, for Project Website you can put http://cs1656.org. Select: Other, No, No radio-buttons, select United States from a drop-down list, and write "I will be using the API for my Introduction to Data Science course assignment #1." Check both check-boxes below and click on "Purchase Key" button.  
7. After receiving the key you can query the weather conditions in KPIT airport on 01/01/2010 by sending the http request to:
http://api.wunderground.com/api/INSERT_YOUR_KEY/history_20100101/q/KPIT.json  
8. After receiving JSON, you can access the amount of snow for the whole month in inches here: JSON/history/dailysummary/0/monthtodatesnowfalli  
9. You can find some useful examples on how to read wunderground JSON files using Python here:
https://www.wunderground.com/weather/api/d/docs?d=resources/code-samples  


~~**Obsolete version**
You should get the WeatherUnderground weather data using their historical data interface, e.g., 
`https://www.wunderground.com/history/airport/KPIT/2016/1/1/MonthlyHistory.html?format=1`
to get a CSV with the readings for all days in January 2016 from Pittsburgh's airport.~~

Please note that the type of precipitation should match even if it is part of the event as well, so `snow` should also match cases of `snow-rain`, `rain-snow`, `fog-rain-snow`, etc

### Output format
Your program should report:  
* the year 
* the total precipitation for each team/city,  
* the winning team, and  
* the percent of win (i.e., if W is the total precipitation of the winning team, L is the total precipitation of the losing team, you need to report 100 * (W / L - 1)     
 
Here is an example of the proper output format (only used to indicate the format, the precipitation amounts are fictitious):
```
YEAR: 1850
TYPE: snow 
TEAM-1: Pittsburgh Steelers 
CITY-1: KPIT 
PRECIP-1: 26.5
TEAM-2: New England Patriots 
CITY-2: KOWD
PRECIP-2: 25.0
WINNER: Pittsburgh Steelers 
PERCENT: 6.00%
``` 

**Notes** In case of no precipitation, you should put `infinity %` as the winning percentage. In case of a tie, you should say `NO WINNER`.
 
### Important notes about grading
It is absolutely imperative that your python program:  
* runs without any syntax or other errors (using Python 3) -- we will run it using the following command:  
`python3 team1 team2 year snow`  
* strictly adheres to the format specifications for input and output, as explained above.     

Failure in any of the above will result in **severe** point loss. 


### Allowed Python Libraries (updated)
You are allowed to use the following Python libraries (although a fraction of these will actually be needed):
```
argparse
collections
csv
glob
json
math 
os
pandas
re
requests
string
sys
urllib
urllib2
```
If you would like to use any other libraries, you must ask permission by Wednesday, January 25, 2017, using [piazza](http://piazza.cs1656.org).


### About your github account
It is very important that:  
* Your github account can do **private** repositories. If this is not already enabled, you can do it by visiting <https://education.github.com/>  
* You use the same github account for the duration of the course  
* You use the github account that you specified during the test assignment (i.e., this one)  

### How to submit your assignment
For this assignment, you must use the repository that was created for you after visiting the classroom link. You need to update the repository to include file `weatherbowl.py` as described above, and other files that are needed for running your program. You need to make sure to commit your code to the repository provided. We will clone all repositories shortly after midnight:  
* the day of the deadline **Friday, February 3rd, 2017 (i.e., at 12:15am, Saturday, February 4th, 2017)**  
* 24 hours later (for submissions that are one day late / -5 points), and  
* 48 hours after the first deadline (for submissions that are two days late / -15 points). 

Our assumption is that everybody will submit on the first deadline. If you want us to consider a late submission, you need to email us at `cs1656-staff@cs.pitt.edu`
