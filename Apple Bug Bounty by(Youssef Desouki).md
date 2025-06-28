# Apple Bug Bounty by(Youssef Desouki) 

[Linked_in_post](https://www.linkedin.com/posts/desoukiofficial_hackerone-apple-bugbounty-ugcPost-7339135339036344322-PBqq/?utm_source=share&utm_medium=member_android&rcm=ACoAAEvbB6gBsfqHvlwzrauR1IimSlFa7C0L4ok)


---


صباح الخير 

البوست ده لان في ناس كتير بعتتلي بتسألني ازاي بتستخرج ثغرات من Apple Bug Bounty 
في البوست ده هتكلم عن الموضوع ده بجزء من التفصيل :

اولا للناس المتعرفنيش انا يوسف دسوقي Penetration Tester Freelance
علي منصة HackerOne و Apple Bug Bounty 

قبل ما اخش مجال ال Bug Bounty انا كنت Software Engineer For Mobile Repair 

الانجازات : 

اضافة اسمي علي حائط شرف شركة Apple عام 2022
اضافة اسمي مرتين علي حائط شرف شركة Apple عام 2024
اضافة اسمي مره علي حائط شرف شركة Apple عام 2025 في شهر 6 
وبعض الانجازات علي منصة HackerOne 

النهاردة هشرح لكم طريقة تفكيري شوية في استخراج الثغرات من Apple 

اولا بحب دايما اتابع التقارير الفي Hacktivity التعملها Fix علي HackerOne 
لو كان التارجت بتاعي هو Apple ف بروح خانة Search for reports 
اكتب فيها كلمة Apple وبشوف تقارير الشركات الاخري الكان ليها علاقة 
بشركة Apple ممكن اوصل لشئ او اعمل Bypass ..

جيت في يوم بالصدفة شوفت التقرير دة علي HackerOne : 

https://lnkd.in/d33FAPAs

One-click account hijack for anyone using Apple sign-in 

بداءت اركز اكتر و اشتغلت علي Login With Apple 
لانك لو قدرت توصل لثغرة في Login With Apple 
ف انت قدرت تنفذ الثغرة علي Apple و برامج HackerOne 
الفيها خاصية Login With Apple ..

طيب اولا الثغرة عشان اقدر انفذها لازم اوصل لموقع بيستخدم Login With Apple 
وكمان يكون مصاب بثغرة ClickJacking عشان اقدر افتح صفحة تسجيل الدخول 
في iFrame ..

استخدمت هنا موقع builtwith.com وقدرت استخرج 9,592 موقع فيهم 
اوبشن Login With Apple

فضلت اجربهم واحد واحد و الموضوع اخد معايا اكتر من 7 ساعات بحاول الم المواقع 
الفيها صفحة تسجيل الدخول ومصابة بثغرة ClickJacking

لحد ما وصلت ل WebSite كان قديم و في خاصية Login With Apple
قديمة ولكن الغريب بالنسبة لي ان Login With Apple كانت شغاله 
رغم انها اصدار OAuth كان قديم جدا ...

بداءت اجرب الثغرة علي WebSite دة الثغرة اتشتغلت بالفعل والكان واضح لي 
ان Apple عملت Fix لاصدارت معينه من OAuth وليس جميع الاصدارات

من خلال الخطاء دة قدرت ارسال تقرير ل Apple Bug Bounty بثغرة

One-Click Account Takeover in via Sign in with Apple OAuth Misconfiguration and window.name Token Leakage

تم ارسال التقرير و تاكيد الاصلاح و القبول

بس كدا ف انا دايما ببداء من اني اشوف التقارير القديمة الفي Hacktivity 
بعد كدا ببداء اشتغل واجرب كل شئ ودي تجربتي مع جميع برامج Bug Bounty
البيكون Scope بتاعها كبير ..

زي Apple و Google و Microsoft

بالتوفيق للجميع 
