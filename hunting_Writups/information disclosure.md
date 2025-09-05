# information disclosure

### [writeup](https://medium.com/@abdalah336/simple-manual-recon-leads-to-p1-finding-and-uncovering-aws-access-and-secret-keys-01739de81633)

<img width="553" height="833" alt="image" src="https://github.com/user-attachments/assets/b69f1951-8998-4505-95ad-907001e8803d" />

---

### **` IIS Shortname Enumeration Lead to Potential Sensitive File Disclosure`** 

[post_link](https://www.linkedin.com/posts/wadgamaraldeen_bugbountytips-cybersecurity-activity-7343264254508056577-_Y31/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

* [shortscan_tool](https://github.com/bitquark/shortscan)
* [nuclei-templates](https://github.com/coffinxp/nuclei-templates/blob/main/iis.yaml)

---
---

## `Got a new reward for Mass Information Disclosure on a payment service company via exposed i18n.json file`

[linkedin_post](https://www.linkedin.com/posts/wadgamaraldeen_bugbountytips-infosec-recon-activity-7353712257500938241-yh-S/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


---
---


[linkedin_post](https://www.linkedin.com/posts/mohamed-m-mourad_codereview-criticalvulnerabilities-hackerone-ugcPost-7364069624272814081-tyNd/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


<details>


```
Recently, I was awarded a bounty!
Amazing Hacking > Amazing Abuse & Leakage > Amazing Critical Vulnerability 🔥🔥🔥

Summary:
While analyzing the source code, I discovered a hard-coded credential. These credential was used to obtain an access token (token1) from endpoint1. According to the source code flow, token1 was then used to fetch another token (token2) from endpoint2. With token2, it was possible to call third-party API endpoints and retrieve Firebase configuration secrets (token, API key, etc.).

From there, I achieved several impacts. One of them was combining the Firebase token with the API key to call Firebase API endpoints and perform authenticated operations.

After deep diving into the Firebase documentation, I found that this combination could be used with the "signInWithCustomToken" operation to obtain an idToken. This idToken could then be leveraged to perform privileged operations, such as deleting Firebase account, updating account settings, and more. 


Impact: 

- An attacker can permanently disrupt the Firebase project by deleting the associated Firebase account.

- An attacker could read and write data on different endpoints across multiple APIs (3 APIs).

- Information disclosure, including database URLs, API keys, account information, and more.


Tips: 

- Analyze the source code thoroughly—not just on the primary subdomain, but also on secondary/non-primary subdomains.

- Don’t be quick to report a leak; think and brainstorm how to escalate the vulnerability to a higher impact.
```

  
</details>




