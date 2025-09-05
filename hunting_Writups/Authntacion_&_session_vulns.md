# Authntation and session vulns

<details>
  <summary>Broken Session Management (methodolgy)</summary>

حابب اكلمكم عن ال methodology اللى ماشى عليها فى ال Broken Session Management 
سوا انت Bug hunter or Penetration tester دا هيفيدك اوى و اتمني لو حد عنده اي اضافه يقولى 

1- login to your account with firefox and chrome
 - change the password in firefox 
 - observe the account in chrome is still logged in and didn't logout
 - Broken session Management 

2- login to your account with firefox and chrome 
 - enable 2FA in firefox 
 - reload the page in chrome and observe session is still valid 

3- login to your account and update anything 
 - intercept the request with burpsuite 
 - send the request to repeater
 - logout from your account 
 - use the request in repater to update and if still valid (vulnerability)

4- ask for reset password 
 - don't click on the link reached you 
 - login with your username and password 
 - change the password of the email 
 - logout from your account and then use the link in step 1 
 - if still valid then (Vulnerability)

5-logout from your account 
 - click on (Alt+Left-arrow) button or <--
 - observe the session and profile data is still found 
 - broken cache vulnerability

6- when updating email address 
 - check if OTP is sent to existing email not the new email 
 - broken function lead to verification bypass

7- create account with email A => victim 
 - update the email to B => hacker then verify it -> vierfy your account 
 - update email back to A => victim 
 - if shown as verified then vulnerability 

8- verifiaction bypass 
 - account with victim@gmail.com => don't verify it 
 - update account email to hacker@gmail.com
 - once you clicked the link , if verified victim@gmail.com then vuln 


  
</details>

* [linked_in_post](https://www.linkedin.com/posts/ahmed-elhawary12_cybersecurity-bugbounty-2fa-activity-7343212599024529409-81N-/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

---
---


<img width="611" height="834" alt="image" src="https://github.com/user-attachments/assets/723d1c4f-cb92-4f77-915f-348cba309560" />



---
---

# `Bypass 2FA Logic Flaw`

[linkedin _post](https://www.linkedin.com/posts/0xoverlord_bugbounty-bugbountytip-ugcPost-7353741273851158528-HhNq/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>

Bug Summary:

1. Try to login to victim account 
2. The system will prompt for the 2FA verification code — do NOT enter the code yet Instead, return to the login page ( by hitting the back button or navigating directly). 
3. Enter the same credentials again and attempt to log in. 
4. Observe that you get access to the account without 2fa

  
</details>

---
---


[Zero-Click ATO via Reusable Password Reset Token](https://medium.com/@mahmodziad40/zero-click-ato-via-reusable-password-reset-token-3299d0bfc005)



---
---





