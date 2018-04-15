# Project 8 - Pentesting Live Targets

Time spent: 6 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration [x]
* Insecure Direct Object Reference (IDOR) [x]
* SQL Injection (SQLi) [x]
* Cross-Site Scripting (XSS) [x]
* Cross-Site Request Forgery (CSRF) [x]
* Session Hijacking/Fixation [x]

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Green

Vulnerability #1: Username Enumeration <br>
Go to the green site's log-in page. If you proceed to try and log in as an invalid user, you will be prompted with an error message stating 'Log in was unsuccessful'. Additionally, logging in with a valid user but an incorrect password, you will see the same error message, this time in bold. This exploit allows unauthorized infiltrators to know whether a username exists in the database or not. <br>
<img src='Username Enumeration.gif' title=' Username Enumeration' width='' alt='GIF Walkthrough' />

Vulnerability #4: Cross-Site Scripting (XSS) <br>
This one primarily focuses on the  green site's comment section. In here, you can insert a XSS attack diguised as an alert by submitting a comment, and consequently a user of the site notices the alert message when they click on the feedback button.<br>
User comment: <br> <img src='XSS user comment.gif' title=' XSS' width='' alt='GIF Walkthrough' /> 
<br>
Logged in: <br> <img src='XSS logged in.gif' title=' XSS' width='' alt='GIF Walkthrough' />

## Blue

Vulnerability #3: SQL Injection  <br>
While on the blue site's salesperson page, if you inject an SQL statement at the end of the salesperson url it will succeed.
For this, I inserted the text ' OR SLEEP(5)=0--' . Doing this, it will make the site to wait about 5 seconds before reloading the first salesperson, Daron Burke.
<br>
<img src='SQL.gif' title='SQL Injection' width='' alt='GIF Walkthrough' />

Vulnerability #6: Session Hijacking/Fixation <br>
While viewing the red site, log in with the pperson credentials given. Now take the url of the red site, paste it in a new web browser (such as Microsoft Edge), then change 'red' to 'blue' un the url, and you will now have user priveleges on the blue site without actually having to log-in. Ta-Da!
<br>
<img src='Session Hijacking.gif' title='Session Hijacking' width='' alt='GIF Walkthrough' />

## Red

Vulnerability #2: Insecure Direct Object Reference <br>
The salespeople can be accessed by specifying an id int in the url. When on the red site, if you change the salesperson id to
10 and 11 it revealed to me two extra people that can't be accessed through IDOR on the blue and green site. <br>
<img src='IDOR.gif' title=' IDOR' width='' alt='GIF Walkthrough' />

Vulnerability #5: Cross-Site Request Forgery <br>
In the red site, you can create a post-method form that sends data to the ip address specified. Inthis particular instance,
I added a new salesman to the list. <br>
<img src='CSRF.gif' title=' CSRF' width='' alt='GIF Walkthrough' />


## Notes

Describe any challenges encountered while doing the work
