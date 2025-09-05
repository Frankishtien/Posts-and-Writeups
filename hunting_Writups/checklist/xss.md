
[My Favourite XSS payloads:](https://www.linkedin.com/posts/rix4uni_bugbounty-bugbountytips-bugbountytip-activity-7369194758872686595-s3Nc/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


<details>


```

My Favourite XSS payloads:
https://lnkd.in/gu6PJ7fi

Don’t just blindly insert payloads anywhere first check for WAF and how the input is reflected in the response.

How I check:
URL: `https://domain[.]com/nodes/search?keywords=rix4uni`
1. Check if rix4uni appears in the response. If there’s no reflection, move to the next URL. If it’s reflected like this:
```
value="rix4uni"
```

2. Test input balancing. For example:
```
keywords=rix4uni'">
```

3. If I see the reflection in the response like this:
```
value="rix4uni&lt;"
value="rix4uni&gt;"
```
then I move to the next URL. If I don’t see it, I try everything to bypass.

4. I also use this tool: xss-payloads-generator
https://lnkd.in/gERGbM-8

```

  
</details>

[xss-payloads-generator_tool](https://github.com/rix4uni/xss-payloads-generator)
[xss_payloads](https://github.com/rix4uni/WordList/blob/main/payloads/xss/favourite.txt)



---
----











