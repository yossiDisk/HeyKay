# Hey Kay · דף הרשמה לפיילוט

דף סטטי אחד (`index.html`) שאוסף פרטים ופותח וואטסאפ עם הודעה מוכנה למספר של Hey Kay.
אין שרת, אין מסד נתונים, אין analytics ואין cookies. הבקשה החיצונית היחידה היא לגופן Rubik מ־Google Fonts.

כתובת חיה: https://yossidisk.github.io/HeyKay/

## איך משנים את המספר
בראש ה־`<script>` ב־`index.html`:
```js
const CONFIG = {
  WA_NUMBER: "972XXXXXXXXX", // ← כאן: קידומת מדינה ובלי + ובלי 0 מוביל. לדוגמה 0501234567 → "972501234567"
  PILOT_OPEN: true,
};
```

## איך סוגרים את הפיילוט
משנים ל־`PILOT_OPEN: false`. במקום הטופס יופיע "הפיילוט מלא כרגע 🙏".

## העלאה
**GitHub Pages** (כבר מוגדר בריפו הזה): כל push ל־`main` מתפרסם אוטומטית תוך דקה–שתיים.
כדי להגדיר מחדש: Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / `(root)`.

**Netlify**: [app.netlify.com/drop](https://app.netlify.com/drop) וגוררים את התיקייה, או מחברים את הריפו (בלי build command, publish directory = `/`).

## פורמט ההודעה (הבוט מפרסר לפי התוויות, לא לשנות אותן)
```
היי Kay! נרשמתי לפיילוט 🙌
קוד: HK-4821
שם: דנה
עסק: סטודיו לפילאטיס בחולון
קהל: נשים 30–50 באזור
מטרה: יותר הרשמות לשיעור ניסיון
מול מצלמה: רק קול
טיקטוק: @dana.pilates
אינסטגרם: @dana.pilates
דמות ציבורית: לא
✅ אישרתי את תנאי הפיילוט
```
שורות טיקטוק/אינסטגרם נכנסות רק אם מולאו. קוד HK נשמר ב־sessionStorage, כך שלחיצה חוזרת באותו טאב שומרת על אותו קוד.

## לפני שעולים לאוויר
- [ ] להחליף את `WA_NUMBER` במספר האמיתי.
- [ ] תנאי הפיילוט מסומנים `<!-- TODO: legal review -->`. להעביר בדיקה משפטית.

## בדיקות שבוצעו
Chrome headless עם emulation של iPhone ו־Android:
מילוי מלא פותח `wa.me` עם ההודעה המדויקת · שדות אופציונליים ריקים לא נכנסים · שדה חובה חסר מציג שגיאה, גולל ולא פותח כלום · שליחה חוזרת שומרת את אותו קוד · `PILOT_OPEN=false` מסתיר את הטופס · אין בקשות רשת חוץ מהגופן.
Lighthouse מובייל: Performance 100, Accessibility 100, Best Practices 100, SEO 100.

צילומי מסך בתיקייה [`screenshots/`](screenshots/).
