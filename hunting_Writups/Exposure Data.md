# Exposure Data

* [linked_in_post](https://www.linkedin.com/posts/rajeshranjan4_bugbounty-infosec-cybersecurity-activity-7338123269998301184-V7vE/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)
* [another_bug_same_idea](https://www.linkedin.com/posts/mohammad-ajarmeh-997b26317_bugbounty-cybersecurity-infosec-activity-7339303574411100160-02mj/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

![image](https://github.com/user-attachments/assets/b76460cf-6eaf-4026-be87-6f42dfcdec58)

لو عندك API Key من VirusTotal (مجاني لو سجلت):

```css
curl -s "http://virustotal.com/vtapi/v2/domain/report?apikey=YOUR_API_KEY&domain=example.com"  /* for main domain or subdomain */
curl -s "https://www.virustotal.com/vtapi/v2/url/report?apikey=YOUR_API_KEY&resource=https://example.com/invoices"  /* for spsific endpoint */
curl -s "http://virustotal.com/vtapi/v2/ip-address/report?apikey=YOUR_API_KEY&ip=1.2.3.4"        /* for ip */
```

هيرجعلك JSON فيه كل حاجة متأرشفة تخص الدومين ده.

OTX AlienVault

```css
curl -s "https://otx.alienvault.com/api/v1/indicators/domain/example.com/url_list?limit=500&page=1"  /* for main domain or subdomain */
curl -s "https://otx.alienvault.com/api/v1/indicators/IPv4/1.2.3.4/general"  /* for ip */
```


---
---
