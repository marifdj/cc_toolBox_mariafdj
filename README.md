# CCToolbox María Florencia De Juan

## Introduction 
This document explains the steps to follow the API tests on Jmeter that applies for each test case and how to execute them.  
The .jmx files are separate in folders, by testcase. 


## Data of a request:
Sampler result
Request:
- Request Headers
- Request Body
- Response data


### Behavior of the request:
- Validate the data that it returns.
- Validate if with the modified content-type the behavior continues the same.
- Validate if the JSON or XML structure is correct.
- Validate if when it gives an error, the status agrees with the error codes.
- Validate if there is an application with incomplete information, what will be the behavior of the application.


## Expected behaviors:
- TEST 1
"Ping" : GET request "'https://echo-serv.tbxnet.com/v1/system/ping" the answer must be correct and return "ok": true 

- TEST 2
"Echo":  GET request "'http: // echo-serv.tbxnet.com/v1/echo?text=test" the answer must be correct and return" text ":" test "



### Jmeter graphic interface
Steps for run the testcases on the Jmeter  [https://jmeter.apache.org/](https://jmeter.apache.org/) - HTML to Markdown

Requires Java Runtime Environment version 1.7 or higher.
To open the Jmeter graphic interface you can go to de the bin folder and search for the file jmeter.bat
You would see on the screen something like the picture below.

 ![image](https://i.imgur.com/dcCKzKw.png)

Then you open the .jmx file from the script folder and put it on the Jmeter graphic interface.
In this script are the setup for the thread groups, the steps of the testcase separate by name, the type of assertions, and the listeners.


You would see on the screen something like the picture below.

![image](https://i.imgur.com/0pHD8nB.png)

![image](logoBH.jpg)


To run the test
You can click on the listener “View Results Tree” to appreciate the results in a clearer way, and then click on the green top button so the test can start.



You would see on the screen something like the picture below.
![image](https://i.imgur.com/bTX3idh.png)


If you want to run the test case again and clean the solution from the view result tree you can go to the clear or clear all brushes

![image](https://i.imgur.com/hkWeqHY.png)
 

### From Command Line

Requires Java Runtime Environment version 1.7 or higher.

First: Open a cmd window and change directory to: C:\Users\mariafdj\Downloads\apache-jmeter-5.1.1\bin
Execute the next command: jmeter -n -t  “name of the .jmx”
You could see on the screen something like the picture below.



### LISTENERS

The listeners that we mainly use for  the testcases are:

- View Results Tree
- Summary Report
- Aggregate Report

### ASSERTIONS

- Response Assertion: Response code = 200
- JSON response Assertions

### HTML REPORTS

In the root directory of the project run: jmeter -n -t  “name of the .jmx” -l “name of the .jtl we want to create” -e -o  “ path of the html folder ” 

For example :
jmeter -n -t  "Scripts/cc_echo_toolBox_mariafdj.jmx" -l "Reports/echo.jtl" -e -o  "Reports\report_echo"



## Images of the HMTL REPORTS
 
 
![image](https://i.imgur.com/NHGvUeG.png)

![image](https://i.imgur.com/0vLT9Sa.png)





### Threads Criteria  
Thread criteria in all the testcases:
1- Baseline
