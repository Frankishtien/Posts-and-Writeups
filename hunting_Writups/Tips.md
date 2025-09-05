<img width="577" height="765" alt="image" src="https://github.com/user-attachments/assets/bb17ac46-7a63-47ef-83cc-fc2a584b417c" />

---
---

<img width="834" height="719" alt="image" src="https://github.com/user-attachments/assets/fba180e9-326c-42a8-a7d3-550b2ac146b8" />

---
---


<img width="1019" height="835" alt="image" src="https://github.com/user-attachments/assets/8bf0799d-0ea5-41aa-9694-58cd4ffa3ee5" />

---
---

<img width="661" height="765" alt="image" src="https://github.com/user-attachments/assets/5ee72f00-70b6-423e-81f1-9d9d20e0e761" />


---
---


[linked_in_post](https://www.linkedin.com/posts/daoud-youssef-yany_%D8%AF%D8%AE%D9%84%D8%AA-%D8%A7%D8%A8%D9%84%D9%8A%D9%83%D8%B4%D9%86-%D9%88%D9%82%D8%B9%D8%AF%D8%AA-%D8%AA%D8%AA%D9%8A%D8%B3%D8%AA-%D9%81%D9%8A%D9%87-%D9%88%D9%84%D9%82%D9%8A%D8%AA%D9%87-%D9%85%D9%82%D9%81%D9%84-activity-7363328055093714944-FDqp/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>


```
دخلت ابليكشن وقعدت تتيست فيه ولقيته مقفل خالص ومش لاقي فيه اي ثغرات هاقولك على سر ..... عارف لما واحد يكون داخل خناقة ومعاه شومة وهو لوحده قدام عشرة بيعمل ايه ؟؟ بيلوش ايوة بالظبط انت مطلوب منك انك تلوش اللي هي بالمصطلح التقني تعمل fuzzing
اعمل حاجات مش متوقعة وصدقني هتتفاجئ برد فعل الباك ايند بتاع الويب ابليكشن زي :-
1- غير request method 
في الاول بدل get - post ابعت put -delete - patch - trace 
وبعدين ابتدي ابعت اسماء غريبة حتى لو اسمك انت 
2- بدل الهوست هيدر بهوست تاني خالص او احقن هيدرز عشوائية بهوست تاني زي x-host | x-forwarded-host | x-forwarded-for ... etc 
3- حط الهوست هيدر لوكال هوست او الهيدرز اللي في النقطة السابقة برضه حطها لوكال هوست او اي ايبي داخلي 
4- غير content-type: application\x-daoud مثلا يعني اي حاجة غريبة 
5- خلي الهيدر بتاع content-type حاجة والبايلود في ال request bosy حاجة تانية خالص يعني واحد json والتاني xml
6- ابعت الريكويست مش/وه يعني مثلا شيل قوس او شيل علامة يساوي او حط حروف غريبة او علامات 
7- احقن null byte في كل حاجة 
8- حط حروف بالعربي في الريكويست ( جابت معايا ثغرة في مرة ) 
9- ابعت ال content-length اكبر او اقل من القيمة الحقيقية بس طبعا متنساش تقفل التعديل الاوتوماتيكي بتاعه في البرب 
10- بدل الارقام حط حروف او حط ارقام كبيرة جدا او صغيرة جدا تؤول للصفر او ارقام سالبة او hex encoded 
11- بدل النصوص حط ارقام او حط مصفوفات arrays او عناصر objects 
12- ضيف بارامترز من عندك او اقسم قيمة البارامتر الموجود على نصين وكرر البارامتر مرتين 
13- اي بارامتر فيه قيمة سواء نص او رقم جرب تغيره ب true or false 
14 - شيل بارامتر خلاص او بدل قيمهم ببعض 
15- تلاعب في الكوكيز في القيم اللي ممكن تتوقع قيمتها مش الحاجات العشوائية 
16- ضيف ارقام او حروف كتير جدا قبل قيمة البارامتر ( في حدود اربع الاف حرف او رقم ) 
17- غير اليوزر ايجينت بتاعك بمتصفح يكون قديم طحن او حط اوامر فيه 
18- غير الريفريرر هيدر ل burp collaborator 
19- حط ايموجي في الريكويست ( اه والله شوفت مقال طويل الراجل كان عامل بايباس للواف بايموجي 
 ) 
20- حط invalid encoding يعني مثلا استعمل UTF-7 / UTF-32 
دي الافكار اللي في دماغي حاليا ولو حد عنده افكار تانية يقولها ونحدث البوست
```
  
</details>



---
----



<img width="1005" height="829" alt="image" src="https://github.com/user-attachments/assets/21eff1b1-e58c-401d-a6d9-eb10ccf378d7" />


---
---


## ``HTTP method inconsistency``


<img width="701" height="538" alt="image" src="https://github.com/user-attachments/assets/b77e7722-8d92-4ccc-aa03-9b4436488abc" />


---
---



<img width="725" height="647" alt="image" src="https://github.com/user-attachments/assets/4fa120bb-5088-4a63-b9ee-8083347f01ef" />




---
---









