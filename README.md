# writeup---surfer

<img width="706" height="274" alt="image" src="https://github.com/user-attachments/assets/2392d02a-601a-4e71-b5b3-245a4a931824" />

Information:
- application has internal page functionality
- I'm looking for a flag on a hidden page
- A link to check out SSRF
- given IP address, no website


**Step 1:**
I have the IP address, so I'm going to go to the web browser and check out the web app to see what I'm looking at exactly. 
I see a basic login page. 

<img width="1277" height="647" alt="image" src="https://github.com/user-attachments/assets/10c19764-70fd-41f5-b661-28a085ae994b" />

I see it's using php by the url it takes me to:

<img width="338" height="82" alt="image" src="https://github.com/user-attachments/assets/aeb9a58e-a4b9-4e0f-a70f-9d56e3e9cc4e" />

**Step 2:**

I dont have any credentials to log in. Let me see if I can use burpsuite to find any. 




