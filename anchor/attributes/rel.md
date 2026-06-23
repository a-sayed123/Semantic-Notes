# rel

This attribute specify the relashinship between our page and link destinatiobn .

## values

* noopener --> is used to close window.opener = null that can stole an important data or user profiles it always used when target _blank is exist .

* noreferrer --> it close knowing the destination the site that the user come from the destination expect that the user is $Direct\ Traffic\ coming$ it used if you want to make destination know that this user is Direct Traffic coming.

* nofollow --> it warns the brower that i absolutly do not responsible for this link it used with links that i do not trust on it.

<hr>
<h3 style="color:green;">الاستخدام العملي :</h3>

* رابط داخلي (في نفس موقعك): لا تكتب rel أبداً (العلاقة آمنة وموثوقة تلقائياً). 
<hr>

* رابط خارجي + تبويب جديد: اكتب rel="noopener" (أمن وحماية).
<hr>

* رابط خارجي + إخفاء الهوية: اكتب rel="noreferrer" (خصوصية تامة).
<hr>

* رابط غير موثوق / إعلان / تعليق مستخدم: اكتب rel="nofollow" (حماية الـ SEO).