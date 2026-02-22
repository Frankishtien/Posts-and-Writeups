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



### [IDOR to Full Account Takeover](https://medium.com/@amrqansow/idor-to-full-account-takeover-f6dd651f5de4)



---
---



### Zero-click ATO 

<details>
 <summary>details</summary>


Zero-click ATO 

PoC: 

1 - create an account like (amir@example.com)

2 - try to create another account but with puny code , like (amir@exàmple.com)

3 - noticed that the program treats them as one account 

4 - go to forget password and put the email with puny code (amir@exàmple.com)

5 - see that the forget password link received to puny code email 

6 - change password, now u changed the password for the main email (amir@example.com) 


easy to search .. 

طب عشان تجيب دومين تستلم عليه الرسالة وتجرب ؟ 
تجرب منين ؟

use burp collaborator 
amir@`burp collab domain` u copied it 

وهتستلم عليه الرسالة .. 

[https://lnkd.in/d2Mmq6jY](https://www.youtube.com/watch?v=Cj1sOFHDClM)
وده فيديو شارح الطريقة بالتفصيل ..


تعديل بسيط عشان اللغبطة بس : 
مش شرط أن الpuny char يكون في الدومين ممكن برضو تعمل 
amir@example.com
àmir@example.com 

مش شرط أنك تغير الdomain او الميل سيرفر 
المهم تستقبل الرسالة .. 

وده رايت اب بيشرح الثغرة برضو .. 

[https://lnkd.in/dWwRp46w](https://infosecwriteups.com/the-most-underrated-0-click-account-takeover-using-punycode-idn-attacks-c0afdb74a3dc)











 
</details>


---
----

## Account Takeover via Password reset poisoning or email verification poisoning

[post_link](https://www.linkedin.com/posts/wadgamaraldeen_%D9%87%D8%B0%D8%A7-%D9%85%D9%86-%D9%81%D8%B6%D9%84-%D8%A7%D9%84%D9%84%D9%87-%D8%B3%D8%A8%D8%AD%D8%A7%D9%86%D9%87-%D9%88-%D8%AA%D8%B9%D8%A7%D9%84%D9%89-private-ugcPost-7428376837451509760-CGSS/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


<details>
 <summary>explain</summary>



Private BB Program 
# Tips :-
When you ever encounter email verification or password reset request :-

1- intercept it using burpsuite
2- Change the host header value to :- 
Host: attacker.com
 or
X-Forwarded-Host: attacker.com
or 
X-Forwarded-For: attacker.com
or duplicate host header :-
Host: company.com
Host: attacker.com

3- Open your test email inbox and check if the email verification or password reset link got poisoned by attacker.com (attacker controlled domain --> verification or reset token get leaked in the attacker's controlled domain logs --> Token theft --> Account Takeover.

If you wanna understand the Account Takeover via Password reset poisoning or email verification poisoning in detail read these blogs/Writeups :-

-https://lnkd.in/d3sWt-e6

-https://lnkd.in/dasvMKrP

-https://lnkd.in/dMAeyyWK

 
</details>


---
---

























