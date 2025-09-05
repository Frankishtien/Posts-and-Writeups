[From One JS File to Full Recon: Gigya API Misconfiguration Exposing Company’s Logic & User Schema](https://www.linkedin.com/posts/wadgamaraldeen_bugbounty-recon-infosec-ugcPost-7347042595782492162-2mVQ/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>


🚨 From One JS File to Full Recon: Gigya API Misconfiguration Exposing Company’s Logic & User Schema

🚨 Summary of the Finding:
While I am testing the login flow of Company.net, I discovered that their frontend JavaScript (gigya.js) embeds a publicly accessible Gigya API Key, allowing unauthenticated access to sensitive SAP Customer Data Cloud (Gigya) endpoints.

- Using this API key, it was possible to perform unauthenticated calls to:
accounts.getScreenSets → Leaks full login UI HTML
accounts.getSchema → Leaks the entire user data structure, including utility-specific fields like meter number, address, and terms agreement
accounts.getPolicies → Reveals password policies and session logic

## Status: Accepted and confirmed by Zerocopter && Company Team, and in Fix process.

🛠️ Example Leaked Endpoint:
https://login[.]Company[.]net/js/gigya.js?apikey=...&lang=nl

🧪 Proof of Concept (PoC):
curl -s "https://accounts[.]eu1[.]gigya[.]com/accounts.getScreenSets?apiKey=EXPOSED_KEY"

🖼️ I even extracted and rendered the full HTML of the leaked login screen, demonstrating how an attacker could reconstruct the platform’s UI without access to the original source code.


🎯 Security Impact:

📥 Information Disclosure: Internal login UI, schemas, and policies exposed
🎭 Phishing Facilitation: Attackers can fully replicate the login screens for realistic attacks
🧠 Reconnaissance: Insight into internal logic & social login providers
⚠️ Misconfiguration: These endpoints are meant to be protected, but unauthenticated access is allowed

📌 Note: While the APIs are hosted by SAP (accounts.eu1.gigya.com), the exposed API Key is specific to the Company Gigya project, and the misconfiguration lies in their own project settings, making it their responsibility to secure it via the admin portal (update access policies in their own admin portal).


👀 Bonus:
I even rendered the actual leaked login screen using the returned HTML — showing how an attacker could build a pixel-perfect phishing page without touching the main app.

✅ Suggested Fixes:

🔐 Restrict unauthenticated access to key endpoints.
🔁 Rotate the exposed API key.
🚫 Don’t embed secrets in public JavaScript files.
🧪 Regularly audit API access scopes and CORS policies.

🙌 Thanks to Zerocopter and the Company security team for the transparent coordination.

## This kind of bug is a perfect example of why recon and passive analysis are so powerful in bug bounty.

📣 If you're a hunter — check those gigya.js files, you might be surprised what’s hiding in plain sight 👀



  
</details>

