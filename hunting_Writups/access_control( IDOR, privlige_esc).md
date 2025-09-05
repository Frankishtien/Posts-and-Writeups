
## ``Logic Flaw in Role Management Leading to Permanent Organization Lockout``

[writeup_link](https://medium.com/@islamghandar/logic-flaw-in-role-management-leading-to-permanent-organization-lockout-f5b55eefb89e) 


---
---

## ``Privilege Escalation via Response Manipulation``

[writeup_link](https://medium.com/@HBlackGhost/privilege-escalation-via-response-manipulation-1bdb829c8748)


---
---

[linked_in_post](https://www.linkedin.com/posts/ahmed-magdy-1452b928a_bugbounty-racecondition-idor-activity-7352251263083761665-2BhB/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>


التارجت مكانش موقع عادي… كان PaaS platform بيقدّم خدمات إدارة البنية التحتية والتطبيقات، وبيستهدف شركات بتشتغل في الـ healthcare والـ compliance (HIPAA/SOC2)
يعني أي حاجة ليها علاقة بالـ access control هناك تعتبر خط أحمر


خلال اختبار بسيط مدته يومين، قدرت أطلع ثغرتين منفصلين بيأدوا لنفس النتيجة:
شلل إداري كامل (Organization Admin Lockout)
لكن كل واحدة بتستخدم تكنيك مختلف

الثغرة الأولى: Race Condition في حذف أعضاء دور المالك (Account Owner)

الـ system بيمنع حذف آخر Verified Owner (وده منطقي)،
بس المشكلة إن الـ check ده مش atomic،
فلو عملت اتنين DELETE parallel، كل request بيشوف إن فيه Owner تاني،
فبيسمح بالحذف…
والنتيجة؟
الاتنين بيتحذفوا في نفس اللحظة — والـ org خلاص مفيهاش أي admin. والـrole نفسها اختفت من الواجهة
مافيش ادمن هيعرف يعمل invite، او roles، ولا يتحكم في أي حاجة.

اللي حصل هنا هو
 TOCTOU (Time of Check to Time of Use) bug = classic race condition 


الثغرة التانية: IDOR – حذف دور المفروض يكون Protected

الفرق بينها وبين الاولى ان الاولى كنت بستخدم race condition علشان امسح كل الادمن انما التانية انا بمسح role الادمن باللي فيها اصلا

لو دخلت على أي role عادي وقررت تحذفه،
تقدر تمسك الـ DELETE /api/account_roles/{role_id}
وتبدّل الـ role_id بـ ID بتاع الـOwner role (اللي مالوش settings في الـ UI أساسًا ومفروض يكون immutable)

المفاجأة؟
الـ API بيرد 204 No Content — يعني الحذف تم 
ومفيش ولا Check على الـ backend يمنع ده!
ودا خلاني أقدر أحذف role المفروض يكون "محمي" من التعديل أو الحذف تمامًا.

التأثير في الحالتين؟

- الـrole اللي فيها الادمن اختفت وبالتالي الـAdmins اختفوا.

- مفيش طريقة self-service ترجع صلاحياتك.

- كل التحكم الإداري راح.
ومحتاج تدخل يدوي من دعم المنصة.

بلغت الثغرتين بالتفصيل، لكن للأسف تم اعتبارهم
 “تصرف خاطئ من Admin موثوق”
مع انهم معترفين بوجود المشكلة في الحالتين،
بس سمعت كلام ملوش علاقة بالمنطق ولا يقنع واحد من الشارع حرفيا 

 الدرس؟
مش كل المنصات بتشوف الـ Logic Bugs بنفس النظرة.

ومش دايمًا الـ تأثير = Breach أو تسريب بيانات.

بس ده لا يمنع إن في مشاكل ممكن تكون catastrophic من منظور الـ Availability والـ Governance.

  
</details>




---
---


<details>

<img width="647" height="826" alt="image" src="https://github.com/user-attachments/assets/e1c0e91d-0a9b-4748-bc21-b9a14d0cc992" />

 
</details>


---
---

[post_link](https://www.linkedin.com/posts/deepmarketer_bugbounty-bugbountytips-bughunting-activity-7365958760441311232-OnQP/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


<details>


<img width="528" height="658" alt="image" src="https://github.com/user-attachments/assets/c890f800-cc9b-47e7-bf93-d879ebf77a31" />

 
</details>


---
---


[IDOR in Invitation Flow Leads to Denial of Signup and Account Manipulation](https://medium.com/@mhmodgm54/idor-in-invitation-flow-leads-to-denial-of-signup-and-account-manipulation-98c51e0dd942)


---
---




[How I Increased the Impact of a Simple Bug to a Full Org Lockout](https://medium.com/@mohammedyousriy/how-i-increased-the-impact-of-a-simple-bug-to-a-full-org-lockout-da32a38b5650)




---
----


<details>
   <summary>I recently encountered an IDOR :</summary>


```
I recently encountered an IDOR :

DELETE /api/notes/:id → tried deleting someone else’s note → 403 Forbidden (expected)

PUT /api/notes/:id → tried editing the same note → success ✅, no authorization check

After editing the note, DELETE /api/notes/:id → succeeded, could now delete the notes which was showing 403 forbidden earlier

Reason: Likely edit endpoint mutated ownership or permission flags, letting delete pass.

Tip: Always test chained actions, not just individual endpoints.
```

<img width="718" height="767" alt="image" src="https://github.com/user-attachments/assets/49a5fa1d-af8b-4f17-9817-9ff2e6499313" />


 
</details>



















