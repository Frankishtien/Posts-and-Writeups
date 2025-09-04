# recon

* [WaybackLister]([https://github.com/anmolksachan/WaybackLister](https://www.linkedin.com/posts/eldoctorams_ahmedmelsayed-recontools-waybacklister-activity-7336820674876862465-4UxU/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok))
  - [WaybackLister tool](https://github.com/anmolksachan/WaybackLister)
 

---
---

* ### ``how passive recon and search engine dorking can reveal real-world vulnerable assets``

[post_link](https://www.linkedin.com/posts/ajay-solanki-3a47b6180_bugbounty-bugbountytip-bugbountytips-activity-7342758495428960256-Ayd_/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>

🔍Security Research] - Found Exposed Hangfire Dashboards via FOFA Dorking 🔍

Hey security fam 👋
Sharing one of my recent findings to help beginners learn how passive recon and search engine dorking can reveal real-world vulnerable assets — no brute force, no login, just smart search!

🔥 Target: Hangfire Dashboard (used to monitor background jobs in .NET apps)
🔓 Issue: Dashboard exposed without any authentication
📡 Method Used: FOFA Search Engine
💡 Dork Used:

body="Hangfire Dashboard"


🧠 What is Hangfire?
A job monitoring dashboard for .NET apps. It helps devs/admins track background jobs like mailers, DB tasks, reports, etc. But if it's open to the public, it’s a serious issue.

🔍 How I Found It (Beginner Friendly Guide):

Went to https://fofa.info/ (a search engine for exposed services)
Searched using the dork:
body="Hangfire Dashboard"
Found several publicly accessible dashboards
Picked one target and opened the link in incognito mode
Dashboard loaded without login! — I could see job data, task queues, internal stack traces etc.
⚠️ Why It’s Dangerous:

Internal job/task information exposed
Stack traces can reveal internal logic or sensitive data
If misconfigured, attackers can trigger or delete background jobs
Full visibility of backend workflows
🛡️ Fix:
Admins should never expose Hangfire dashboards without authentication.
Guide to secure it ➝ (https://lnkd.in/dbEgjvr3)
🔗 Securing Hangfire Dashboard

💬 For Beginners:
✅ Learn to use search engines like FOFA/Shodan
✅ Try dorks that target common keywords
✅ Always test in incognito to bypass saved sessions
✅ Passive recon = low noise + high impact

📸 PoC Screenshot: [Attached]
Let’s keep hunting and learning! 🐺

  
</details>



---
---


* ## ``From One JS File to Full Recon: Gigya API Misconfiguration Exposing Company’s Logic & User Schema``

[post_link](https://www.linkedin.com/posts/wadgamaraldeen_bugbounty-recon-infosec-activity-7347042597690859521-zK0R/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


<details>


# From One JS File to Full Recon: Gigya API Misconfiguration Exposing Company’s Logic & User Schema

---

## Summary of the Finding

During testing of **Company.net**’s login flow, I discovered that their frontend JavaScript (`gigya.js`) embeds a publicly accessible **Gigya API Key**, allowing **unauthenticated access** to sensitive SAP Customer Data Cloud (Gigya) endpoints.

### Exposed Endpoints
Using this API key, it was possible to perform unauthenticated calls to:

- `accounts.getScreenSets` → Leaks full login UI HTML
- `accounts.getSchema` → Leaks the entire user data structure (e.g., meter number, address, terms agreement)
- `accounts.getPolicies` → Reveals password policies and session logic

---

## Status

- **Accepted and confirmed** by Zerocopter and Company Security Team
- Fix is currently in progress

---

## Example Leaked Endpoint

```
https://login.Company.net/js/gigya.js?apikey=...&lang=nl
```


---

## Proof of Concept (PoC)

```bash
curl -s "https://accounts.eu1.gigya.com/accounts.getScreenSets?apiKey=EXPOSED_KEY"
```


---

Security Impact
Information Disclosure: Internal login UI, schemas, and policies exposed

Phishing Facilitation: Attackers can replicate login screens for realistic attacks

Reconnaissance: Insight into internal logic & social login providers

Misconfiguration: Endpoints are meant to be protected, but unauthenticated access was allowed

Why This Matters
While the APIs are hosted by SAP (accounts.eu1.gigya.com), the exposed API Key is specific to Company’s Gigya project.
The misconfiguration lies in the company’s project settings, which must be secured via their own admin portal (by updating access policies).

Bonus
Rendered the leaked login screen using returned HTML, demonstrating pixel-perfect phishing potential.

Suggested Fixes
🔐 Restrict unauthenticated access to key endpoints.

🔁 Rotate the exposed API key immediately.

🚫 Avoid embedding secrets in public JavaScript files.

🧪 Regularly audit API access scopes and CORS policies.

Takeaway
This finding highlights the power of recon and passive analysis in bug bounty.
If you’re a hunter — always check those gigya.js files, you might find something valuable hiding in plain sight 👀



  
</details>





---
---


## ``15 Minutes, Recon and €250 Bounty``

[linked_in_Post](https://www.linkedin.com/posts/lucas-gon%C3%A7alo-de-morais_15-minutes-recon-and-250-bounty-english-activity-7352092810319147011-JW_-/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>


---

I recently received a €250 bounty in a public Bug Bounty program on Intigriti. This outcome reinforces that effective asset enumeration and reconnaissance are crucial for significant discoveries and impacts.

In less than 15 minutes of analyzing the scope, I identified Firewall and Endpoint Management Server (EMS) panels publicly exposed on a subdomain of an in-scope asset.

The particularity of this discovery lies in the fact that these endpoints were not indexed on Google and were not accessible via conventional dorking techniques. The identification was made possible through an in-depth SSL/TLS certificate enumeration analysis, a methodology that often reveals hidden assets that remain invisible through superficial recon approaches.

The public exposure of these critical administrative interfaces represents a security misconfiguration with inherent risks. Initially, the report was classified with low criticality by the company's team. However, after a subsequent re-evaluation, the team confirmed that the actual criticality was Medium. Despite platform limitations to adjust the severity, a bonus was granted, reflecting the recognition of the revised severity.
  
</details>













