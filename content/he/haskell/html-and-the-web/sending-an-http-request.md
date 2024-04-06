---
date: 2024-01-20 18:00:30.992927-07:00
description: "\u05D0\u05D9\u05DA \u05DC\u05E2\u05E9\u05D5\u05EA: \u05D4\u05E8\u05E6\
  \u05EA \u05D4\u05E7\u05D5\u05D3 \u05D4\u05D6\u05D4 \u05EA\u05D7\u05D6\u05D9\u05E8\
  \ \u05DE\u05E6\u05D1 \u05EA\u05D2\u05D5\u05D1\u05D4 (\u05DB\u05D2\u05D5\u05DF 200\
  \ \u05DC\u05EA\u05D2\u05D5\u05D1\u05D4 \u05DE\u05D5\u05E6\u05DC\u05D7\u05EA) \u05D5\
  \u05D0\u05EA \u05D4\u05EA\u05D5\u05DB\u05DF \u05E2\u05E6\u05DE\u05D5 - \u05D1\u05D3\
  \u05E8\u05DA \u05DB\u05DC\u05DC \u05D1\u05E4\u05D5\u05E8\u05DE\u05D8 JSON \u05D0\
  \u05D5 HTML."
lastmod: '2024-04-05T21:53:40.578435-06:00'
model: gpt-4-1106-preview
summary: "\u05D4\u05E8\u05E6\u05EA \u05D4\u05E7\u05D5\u05D3 \u05D4\u05D6\u05D4 \u05EA\
  \u05D7\u05D6\u05D9\u05E8 \u05DE\u05E6\u05D1 \u05EA\u05D2\u05D5\u05D1\u05D4 (\u05DB\
  \u05D2\u05D5\u05DF 200 \u05DC\u05EA\u05D2\u05D5\u05D1\u05D4 \u05DE\u05D5\u05E6\u05DC\
  \u05D7\u05EA) \u05D5\u05D0\u05EA \u05D4\u05EA\u05D5\u05DB\u05DF \u05E2\u05E6\u05DE\
  \u05D5 - \u05D1\u05D3\u05E8\u05DA \u05DB\u05DC\u05DC \u05D1\u05E4\u05D5\u05E8\u05DE\
  \u05D8 JSON \u05D0\u05D5 HTML."
title: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP"
weight: 44
---

## איך לעשות:
```Haskell
-- נבצע התקנה של ספריית 'http-conduit' בעזרת cabal:
-- cabal install http-conduit

{-# LANGUAGE OverloadedStrings #-}
import Network.HTTP.Simple

-- דוגמא לשליחת בקשת GET
main :: IO ()
main = do
    response <- httpLBS "http://httpbin.org/get"
    putStrLn $ "סטטוס: " ++ show (getResponseStatusCode response)
    putStrLn $ "תוכן תשובה: " ++ show (getResponseBody response)
```

הרצת הקוד הזה תחזיר מצב תגובה (כגון 200 לתגובה מוצלחת) ואת התוכן עצמו - בדרך כלל בפורמט JSON או HTML.

## הבטן העמוק:
שליחת בקשת HTTP ב-Haskell לא הייתה תמיד כל כך פשוטה. בעבר, נדרשו יותר שורות קוד והבנה טכנית גבוהה יותר. כיום, ספריות כמו `http-conduit` מספקות ממשק נקי ומקוצר לביצוע בקשות.

באופציות אחרות, ניתן לעשות שימוש בספריות כמו `wreq` או `req`, אשר מציעות תכונות נוספות ושימוש נוח. כל ספרייה מתמקדת בסט שונה של פיצ'רים והתאמה לצרכים ספציפיים.

מבין הפרטים הטכניים של שליחת בקשות HTTP, תספקתי דוגמה בסיסית, אבל זיכרו שיש הרבה יכולות כמו ניהול הדר 'Headers', שימוש בשיטות שונות כמו POST או DELETE, ועבודה עם משתנים של פרמטרים ומשתני סביבה.

## ראה גם:
- [http-conduit on Hackage](https://hackage.haskell.org/package/http-conduit)
- [wreq on GitHub](https://github.com/bos/wreq)
- [req on Hackage](https://hackage.haskell.org/package/req)

המאמרים והמקורות הנ"ל יכולים להרחיב את הידע שלך על שליחת בקשות HTTP בהסקל ובכלל.

גלישה מהנה! 🚀
