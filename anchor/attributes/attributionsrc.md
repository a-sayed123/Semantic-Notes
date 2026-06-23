
**تخيل مدينة كبيرة بها حكومة و بها كميرات بكل شارع و اعطت المتاجر الضخمة امكانية الوصول الى كل كاميرات الشوارع لتعلم ما اذا كانت مصادر اعلاناتها هي ما تدر علينا مشترين لكنالحكومة اكتشفت ان هذا غير امن و انتهاك لحقوق الانسان فقالت للمتاجر صاحبة الاعلانات ان يبرموا صفقات عادي مع شركات الاعلانات لكن نتيجة هذه الاعلانات تحصلون عليها من مركز الشرطة وقتها تم منع اي احد من مراقبة الشوارع الا الحكومة فصار المتجر يبرم صفقة مع الشركة المعلنة و عندما يشتري احدهم بسبب الاعلان وقتها الشركة المعلنة تدلي بتقرير للحكومة و ثم الحكومة بدورها تبلغ المتجر بحال الاعلان و ايراداته و تتعامل هي معه ... بصراحة عبقرية**

# attributionsrc

## Why does it exist?

Traditionally, advertisers wanted to know whether an advertisement resulted in a user visiting or purchasing from a website. Older tracking techniques often relied on cross-site tracking, which raised significant privacy concerns.

`attributionsrc` is part of the Attribution Reporting API. It enables websites to measure the effectiveness of advertisements while reducing direct cross-site user tracking.

## The Problem

Without a privacy-preserving mechanism, advertisers may attempt to track users across multiple websites to determine whether an advertisement led to a conversion.

This approach exposes unnecessary user information and weakens privacy.

## The Solution

Instead of allowing advertisers to directly observe the user's journey across websites, the browser acts as a trusted intermediary.

The website and the advertising platform can register attribution sources, while the browser records attribution events locally.

When a conversion occurs, the browser generates privacy-preserving attribution reports according to the API's rules, instead of exposing the user's browsing activity directly.

## Key Idea

The browser becomes the trusted mediator between:

* The website.
* The advertising platform.

This allows advertising performance to be measured without giving third parties unrestricted visibility into the user's navigation history.

## Goal

**Measure ad effectiveness while improving user privacy.**
<br><hr>

**Eligible** <br>
*--------* <br>
*Browser asks:*
*"Can we use Attribution Reporting?"*

**Register-Source** <br>
*---------------* <br>
*Server replies:* <br>
*"Yes, register this interaction as an attribution source."*
<br><br><br><br><br>
<hr>

Browser  <br>
    │    <br>
    │  Attribution-Reporting-Eligible <br>
    ▼ <br>
Server <br>

Server <br>
    │  <br>
    │ Attribution-Reporting-Register-Source <br>
    ▼  <br>
Browser
