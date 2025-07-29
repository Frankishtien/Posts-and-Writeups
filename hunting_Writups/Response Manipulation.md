# Response Manipulation

* [linked_in_post](https://www.linkedin.com/posts/pt-ahmed-alaa_%D9%8A%D8%A7-%D9%85%D8%B3%D8%A7%D8%A1-%D8%A7%D9%84%D9%81%D9%84-%D9%8A%D8%A7-hunters-%D8%AF%D9%87-%D8%A3%D9%88%D9%84-%D8%B1%D9%8A%D8%A8%D9%88%D8%B1%D8%AA-%D9%84%D9%8A%D8%A7-activity-7337208734248529921-6mf_/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

![image](https://github.com/user-attachments/assets/dbd64608-3ba1-48a6-b410-45b63ce1fde9)

---
---

* ### ``Response Manipulation: The Hidden Path to Account Takeover``

[writup_link](https://medium.com/@Y0S3TREX/response-manipulation-the-hidden-path-to-account-takeover-1f009bb5a676)
  
---
---


* ### ``Null Byte Injection + Response Tampering ``

[postlink](https://www.linkedin.com/posts/khaled-ahmed-1958b3249_hackerone-bugbounty-cybersecurity-activity-7335360531588874240-yfip/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>

# Exploiting Logic Flaw in Registration Flow (Null Byte Injection + Response Tampering)

## Overview
This writeup describes a logic flaw in a web application's registration flow. By combining **Null Byte Injection** and **Response Tampering**, it was possible to bypass certain validations and even create accounts using internal emails (e.g., the founder’s email).

---

## Techniques Used

### 1. Null Byte Injection
- **Payload Example:**

```
email@example.com\u0000
```

- **Goal:** Trick the backend into treating the string before the null byte as the real email.
- **Result:** In this case, the backend correctly validated the email and rejected it.  
- **Note:** On some systems, this bypass works because null bytes terminate strings in C-based environments.

---

### 2. Response Tampering
- The server returned:

```http
HTTP/1.1 409 Conflict
```

- Modified in Burp Suite to:

```http
HTTP/1.1 201 Created
```

- **Effect:**  
The frontend trusted the modified status code and continued the registration flow (sending verification emails) without additional backend checks.

---

## Exploiting Internal Emails

- Using [Hunter.io](https://hunter.io) to gather internal emails (high confidence: 99%).
- Registering with an internal email using the same tampering technique.
- If the victim clicks the verification link → potential **Account Takeover (ATO)**.

---

## Impact

- **Medium Risk:** When used on your own email (flow manipulation only).
- **High Risk:** When used on internal emails, leading to ATO of privileged accounts.

---

## Lessons Learned

- Never trust **frontend-only validation** or rely solely on HTTP status codes.
- Backend must re-check email uniqueness and validity before sending verification emails.
- Monitor for **response tampering attacks** during registration and critical flows.

---

## Tools Used

- **Burp Suite**: For intercepting and modifying server responses.
- **Hunter.io**: For finding internal email addresses.
- **Null Byte Injection**: For bypassing string validation in some environments.

---

## References

- [Null Byte Injection Explanation](https://owasp.org/www-community/attacks/Null_byte_injection)
- [Response Tampering Techniques](https://portswigger.net/web-security/response-tampering)









  
</details>

