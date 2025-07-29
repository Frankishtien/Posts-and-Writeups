# HTML injection

[Tips for Finding HTML Injection](https://www.linkedin.com/posts/ramah-bashir-1592a1231_hackeron-bugbounty-bugbountytips-ugcPost-7342493505006579712-L8rE/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>

Tips for Finding HTML Injection (Based on My Discovery)

🛠️ Here’s how I found a real HTML Injection vulnerability that gets rendered inside an email:


---

✅ 1. Look for public forms
I started by testing a public form where users can submit info (like name, address, etc.).
Target: https://lnkd.in/ek_giKPJ


---

✅ 2. Submit HTML as input
I entered this into the "Full Name" field:

<h1 style="background:red;color:black;">Injected by Rima7</h1>

No filters? You're onto something.



✅ 3. Trigger the email
Once I submitted the form, I received the confirmation email.

Boom 💥 — the HTML was rendered inside the email, not escaped.


4. Bonus tip: check for phishing potential
Try this:

<a href="https://phishing.com" style="color:red;">Click here to update your account</a>

If it looks like a real internal message — that’s phishing potential!

Final Tips :
Target Any form that reflects user input
Always check email confirmations
 
</details>


---



* ## ``Escalated Simple HTML Injection to SSRF via PDF Rendering``

[writeup_link](https://medium.com/@0x_xnum/how-i-escalated-simple-html-injection-to-ssrf-via-pdf-rendering-682ea94b3194)

















