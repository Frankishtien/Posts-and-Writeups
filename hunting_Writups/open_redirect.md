# Open Redirect

* [linked_in_post](https://www.linkedin.com/posts/desoukiofficial_%D8%B5%D8%A8%D8%A7%D8%AD-%D8%A7%D9%84%D8%AE%D9%8A%D8%B1-%D9%83%D9%86%D8%AA-%D8%AD%D8%A7%D8%A8%D8%A8-%D8%A7%D8%AA%D9%83%D9%84%D9%85-%D8%B9%D9%86-%D9%86%D9%88%D8%B9-%D8%AB%D8%BA%D8%B1%D8%A9-low-ugcPost-7339303685203591169-eCP0/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)

<details>

صباح الخير 

كنت حابب اتكلم عن نوع ثغرة Low ولكن درجة الخطورة بتاعتها توصلك ل Critical
هشرح ليكم التجربة من نحية تقرير خاص بي ارسلتو من قبل علي HackerOne

الثغرة هي Open Redirect 

بشوف ناس كتير بتلاقي Open Redirect في صفحة Login الخاصة ب Program
وتروح تبلغها Open Redirect وخلاص علي كدا 
ويوم ما تتقبل هتتحسب ليهم Low 

هشرح ليكم طريقة تفكيري لما بلاقي Open Redirect في صفحة Login 
وازاي بتعامل معاها وهشارك ليكم تقرير خاص بي علي PayPal

اولا اول حاجة لما بلاقي Open Redirect في صفحة Login 
بجرب Account TakeOver طب ازاي ..؟!

اول حاجه بتاكد ان الموقع ممكن يرسال بيانات لسيرفر خارجي ..
لان بيكون في ساعات مواقع فيها Open Redirect 
ولكن مش بيرسال بيانات غير لسيرفرات الشركة فقط

طب اتاكد ازاي من دة ..؟ 

مثلا دة Target في ثغرة Open Redirect في صفحة Login 

redirect_url=https://lnkd.in/dbHENKD2

واول ما تعمل Login بيعمل Redirect تروح علي موقع Evil 

طيب بدل ما تعمل Redirect علي Evil اعمل Redirect علي Burp Collaborator
وشوف هل هيبعتلك بيانات علي السيرفر الخاص بيك ولا لا 

لو وصلك بيانات فعلا علي السيرفر الخاص بيك بتقدر من خلال البيانات الوصلت لك 
تستخرج Account TakeOver لان عند تسجيل الدخول بيرسالك لك بيانات 
عملية تسجيل الدخول زي

Access Token
JWT Token

وممكن يحصل Redirect URL Access Token
اول ما تفتح URL دة يسجل دخولك لحساب Victim مباشر
بيكون بالشكل دة 

https://example/access-token:XXXX:XXXX:XXXX:XXXX

طب ايه الحصل معايا في تقرير PayPal 

لقيت موقع قديم ل PayPal كان في اوبشن Login With PayPal 
لما ضغط Login PayPal 

في 3 Redirect_URL بيحصل اول ما بعمل Login With PayPal
وطبعا كان بعد اخر Redirect كان بيديني BA-Token 
خاص بجلسة OAuth الحصلت من PayPal 

لحد ما وصلت لطريقة تجمع بين الموقع العملت في Login With PayPal 
وصفحة تسجيل الدخول الخاصة ب PayPal.com

وغيرت مسار ال Redirect الخاص بالموقع الي Burp Collaborator 
وعملت تسجيل دخول لحسابي علي PayPal تم ارسال بيانات حسابي
الي سيرفر Burp Collaborator 

وتحولة العملية من Open Redirect ل Account Takeover
ولكن للاسف حالة التقرير كانت Duplicate (Closed)

الحمدالله واتمني اني اكون بفدكم فعلا
وبالتوفيق للجميع


 
</details>





---
---














