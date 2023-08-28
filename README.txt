Do at least ONE of the following tasks: refactor is mandatory. Write tests is optional, will be good bonus to see it. 
Please do not invest more than 2-4 hours on this.
Upload your results to a Github repo, for easier sharing and reviewing.

Thank you and good luck!



Code to refactor
=================
1) app/Http/Controllers/BookingController.php
2) app/Repository/BookingRepository.php

Code to write tests (optional)
=====================
3) App/Helpers/TeHelper.php method willExpireAt
4) App/Repository/UserRepository.php, method createOrUpdate


----------------------------

What I expect in your repo:

X. A readme with:   Your thoughts about the code. What makes it amazing code. Or what makes it ok code. Or what makes it terrible code. How would you have done it. Thoughts on formatting, structure, logic.. The more details that you can provide about the code (what's terrible about it or/and what is good about it) the easier for us to assess your coding style, mentality etc

And 

Y.  Refactor it if you feel it needs refactoring. The more love you put into it. The easier for us to asses your thoughts, code principles etc


IMPORTANT: Make two commits. First commit with original code. Second with your refactor so we can easily trace changes. 


NB: you do not need to set up the code on local and make the web app run. It will not run as its not a complete web app. This is purely to assess you thoughts about code, formatting, logic etc


===== So expected output is a GitHub link with either =====

1. Readme described above (point X above) + refactored code 
OR
2. Readme described above (point X above) + refactored core + a unit test of the code that we have sent

Thank you!

------------------------------------------------------Comments--------------------------------------------------------------------

I did following code refectoring, 

--BookingController--
index():
instead of using long name twice, assign its value to a variable and use the variable : $userType = $request->__authenticatedUser->user_type;

update function():
no need to use array_except instead directly exclude specific keys from the $data

immediateJobEmail():
minor changes, removed unused variables

getHistory():
to keep it simple, assignment is moved before condition

distanceFeed(): 
inline condtion(ternary expression) can be used instead of if-else 


---BookingRepository---
changed variable names to have consistency like changing $noramlJobs to $normal_jobs.
proper comparison === instead of ==
condition checks for $cuser first instead of checking in both if and elseif
Removed the unused variables $page_num and $num_pages  
inline condition instead of if else
removed commented code

Functions/Methods should be smaller as possible, to do relevent task only as it name suggest

store() function is divided in two functions validateCustomerData() & processCustomerData()
validateCustomerData() :  to process validation, it will be easier to handle validation if we have to add more validation or change   
processCustomerData: will be easier to handle customer data sepratly 

And processCustomerData() is split into further another function called createJob() to handle job related stuff

Similary storeJobEmail() is divided in 2 different functions updateJobInfo() & jobCreated()


sendJobEndedEmail() is created and used twice in a same function to send emails from same function jobEnd()
calculateTimeDifference() can be used again 


simmilary same refectoring rules can be applied to refector the rest of functions 