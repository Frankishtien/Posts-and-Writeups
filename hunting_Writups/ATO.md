# ATO 

[The easiest Multiple Account Takeover (ATO)](https://hesham-elbadry.github.io/posts/Multiple_ATO/)


---
---
[writeup_link](https://medium.com/@mohammedemarah/security-misconfiguration-bypassing-client-side-email-restrictions-in-oauth-enabled-8d4b775f9c3e)


---
---

[linkedin_post](https://www.linkedin.com/posts/hossam-ayman-123330193_bugbounty-bugbountytips-accountakeover-activity-7357597220730191872-Vc5w/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>

Firing 8 Account Takeover Methods


Unicode Normalization Issue
1. victim account: victim@gmail.com
2. create an account using Unicode | example: vićtim@gmail.com (here is ć is an Unicode character)

 list of Unicode character: 
 https://lnkd.in/dWCrsCh4
Note: check where verification doesn’t require

Authorization Issue
1. change email of Account A and put email B
2. check confirmation mail in account B
3. open the confirmation mail from account C
Taken over Account C

Reusing Reset Token
if target allows you to reuse the reset link then hunt for more reset link via gau ,wayback or urlscan.io

Pre Account Takeover
1. signup using normal signup form as a hacker but hacker has no verification link.
2. then if victim signs up using oauth .
3. Verification bypass now attacker can login the victim account without verification link with the password he entered while registering.

CORS Misconfiguration to Account Takeover
1. check api , any endpoint has access access token/session/secret/fingerprint
2. if yes check for CORS misconfiguration does it allow us to fetch data from target?
3. make a payload to fetch data and replace headers and boom


CSRF to ATO
If profile modification in cookie based authentication doesn’t generate any token
1. open Account A change & Put email that you own click save intercept the request and generate a csrf poc.
2. if fully cookie based auth then you dont have to modify anything send the CSRF file to victim.
3. if it requires UUID/UserID or unique token it becomes hard to do that but that doesn't mean it is secure , just start playing with target
hint: password reset page helps many times for UUID/GUID and UserID


Host Header Injection
well in this case there are 4 ways do that.
1. click reset password change host header.
2. or change proxy header ex: X-Forwarded-For: attacker.com
3. or change host, referrer, origin headers at once as attacker.com
4. click reset then click resend mail and do all 3 methods above


Response Manipulation
1. code manipulation * to 200 OK
2. code and body manipulation
code * to 200 OK
body * to {"success":true} or {}
It works when json is being used to transfer and receive data.
  
</details>



---
---


[Zero-Click ATO via Reusable Password Reset Token](https://medium.com/@mahmodziad40/zero-click-ato-via-reusable-password-reset-token-3299d0bfc005)




---
---

[0-Click ATO and Privilege Escalation](https://hesham-elbadry.github.io/posts/0-Click-ATO-and-privilege-escalation/)


---
---


### [A Critical Zero-Day in Atlassian Jira Service Management Cloud: Password Reset Account Takeover](https://medium.com/@MoSalah11/a-critical-zero-day-in-atlassian-jira-service-management-cloud-password-reset-account-takeover-1903cbb8bd31)


---
---















