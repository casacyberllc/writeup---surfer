# writeup---surfer

<img width="706" height="274" alt="image" src="https://github.com/user-attachments/assets/2392d02a-601a-4e71-b5b3-245a4a931824" />

Information:
- application has internal page functionality
- I'm looking for a flag on a hidden page
- A link to check out SSRF
- given IP address, no website


Ok so there is going to be some kind of ssrf vulnerability. This is when you're able to manipulate a url to navigate to another part of a website. 

I'm going to check the source code to start, lets check if there's any hidden form fields. 

Ok so far I see that the form is supposed to validate using validate.php and then redirect to index.php. I don't seem to be getting anywhere from here trying to insert those. 

Let's check the robots.txt file. 

I see a link to a text file. I go there, and it's a conversation between two employees, Kate and Admin. Kate tells admin to stop using the username as the password. I try 'admin' and 'admin' on the login form and immediately get into the system. 


I see there's a link on the bottom to generate a report for the internal server. 

<img width="1026" height="379" alt="image" src="https://github.com/user-attachments/assets/86bb7008-5025-41a5-9679-4385fdc65c78" />

I open the report, and I see the following. 

<img width="854" height="736" alt="image" src="https://github.com/user-attachments/assets/b1d62790-781a-4cd3-aa7b-9ba3c5b398a3" />

Ok so the server information is being grabbed locally. Let's note that for now. 

I went back to the main admin page on index.php. I see notes on the side showing where you can access the internal admin pages where the flag is located. 

<img width="420" height="480" alt="image" src="https://github.com/user-attachments/assets/eb75ba6e-2c55-4343-b933-47dd0aa9865e" />

Ok so let's try to access it on the site. 

It says it can only be accessed internally. 

I'm going to try to use burpsuite to access the flag. 

I went back to the index.php page, turned the proxy and intercept on and tried to download the PDF once again. 

In burpsuite, I intercepted the traffic and I'm going to modify the link. 


This is what I originally had, and I modified the bottom url to redirect to /internal/admin.php

<img width="811" height="488" alt="image" src="https://github.com/user-attachments/assets/dd41c539-2c5f-4806-8ee3-7aec7930c8ff" />


<img width="677" height="298" alt="image" src="https://github.com/user-attachments/assets/0360499a-f335-41ce-afbf-9eab2911fd5e" />

I can forward this now, and tada. I got the flag. 

<img width="971" height="244" alt="flag" src="https://github.com/user-attachments/assets/a012cba0-63ea-4d65-9acb-22ec36049374" />
