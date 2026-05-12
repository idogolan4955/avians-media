# Avians Media Repository

מאגר התמונות והנכסים הדיגיטליים של **Gal Avitan Bridal Couture**.
משמש כ-CDN ציבורי לאתר ולקטלוג המוצרים.

**Repo:** https://github.com/idogolan4955/avians-media
**תיקיית עבודה מקומית:** `~/Library/Mobile Documents/com~apple~CloudDocs/avians-media` (iCloud)
**סטטוס:** Public — לינקים פעילים ללא טוקן.

---

## תוכן הענייני

- [מבנה התיקיות](#מבנה-התיקיות)
- [תהליך עבודה - הכנת קולקציה חדשה](#תהליך-עבודה---הכנת-קולקציה-חדשה)
- [מבנה לינקים (Raw URL)](#מבנה-לינקים-raw-url)
- [קולקציות קיימות](#קולקציות-קיימות)

---

## מבנה התיקיות

```
avians-media/                              ← תיקיית האב (iCloud)
│
├── README.md                              ← הקובץ הזה
│
├── Regal Collection Images/               ← Landscape של Regal
│   ├── REGAL COLLECTION.jpg               ← כריכת קולקציה
│   ├── REGINA.jpg, ELARION.jpg, ...       ← תמונה לכל דגם (שם הדגם = שם הקובץ)
│   └── Regal_URLs.xlsx                    ← אקסל עם URLs + מחירים + Silhouette
│
├── תמונה ראשית/                          ← Portrait של Regal (1080×1920, אנכי כמו אייפון)
│   └── REGINA.jpg, ELARION.jpg, ...
│
├── Gallery Collection Images/             ← Landscape של Gallery
│   ├── GALLERY COLLECTION.jpg
│   ├── FLORA.jpg, ETOILE.jpg, ...
│   └── Gallery_URLs.xlsx
│
├── Gallery - תמונה ראשית/                 ← Portrait של Gallery
│
├── ABU DHABI Collection Images/           ← Landscape של ABU DHABI
│   ├── ABU DHABI COLLECTION.jpg
│   ├── LYRA.jpg, NAILA.jpg, ...
│   └── ABU_DHABI_URLs.xlsx
│
├── ABU DHABI - תמונה ראשית/               ← Portrait של ABU DHABI
│
├── banner_hero_1600x900.jpg               ← Hero Banner - Regal
├── banner_gallery_1600x900.jpg            ← Hero Banner - Gallery
└── banner_abudhabi_1600x900.jpg           ← Hero Banner - ABU DHABI
```

---

## תהליך עבודה - הכנת קולקציה חדשה

חמישה שלבים, מ-PDF של הלוקבוק ועד עדכון Base44.

### שלב 1 — הכנת סט התמונות

לכל קולקציה מכינים שני סוגי תמונות:

| סוג | מימדים | תיקיה | שימוש |
|---|---|---|---|
| **Landscape** (גלריה) | ~2636×2250 px | `<Collection> Collection Images/` | תצוגה רחבה באתר, חיתוך הטקסט/תיאור מה-PDF |
| **Portrait** (תמונה ראשית) | 1080×1920 px | `<Collection> - תמונה ראשית/` | יחס 9:16 כמו מסך אייפון, תצוגה מובייל |

**כללים:**

- שם הקובץ = שם הדגם באנגלית באותיות גדולות, למשל `REGINA.jpg`, `LYRA.jpg`.
- לדגמים עם רווחים, השאר רווח: `LA BELLE.jpg`.
- לכריכת קולקציה: `<COLLECTION NAME> COLLECTION.jpg`, למשל `REGAL COLLECTION.jpg`.
- איכות JPEG: 92%, צבע sRGB.
- בנוסף, מכינים **באנר ראשי** 1600×900 עם 4-5 כלות מאותה קולקציה (ראה דוגמאות ב-`banner_*.jpg`).

### שלב 2 — מיקום בתיקיית האב

מעתיקים את שתי התיקיות שהוכנו (Landscape + Portrait) אל:

```
~/Library/Mobile Documents/com~apple~CloudDocs/avians-media/
```

iCloud מסנכרן אוטומטית.

### שלב 3 — Commit ו-Push דרך GitHub Desktop

1. פותחים את **GitHub Desktop**
2. בוחרים `avians-media` ב-Current Repository, branch `main`
3. ב-"Summary" כותבים מה הוסף, לדוגמה: `Add <Collection Name> collection`
4. **Commit to main**
5. למעלה ימינה: **Push origin**

**שים לב:** אם מופיע "lock file" — לסגור עורכים/מקורות אחרים שעובדים על הריפו ולנסות שוב.

### שלב 4 — יצירת רשימת Raw URLs

לכל קולקציה יש קובץ אקסל מובנה בתוך תיקיית ה-Landscape:

```
<Collection> Collection Images/<Collection>_URLs.xlsx
```

עמודות הקובץ:

| עמודה | תיאור |
|---|---|
| Model | שם הדגם (REGINA, LYRA, ...) |
| Code | קוד פנימי (R1021, GA-DU-2201, ...) |
| Silhouette | A-LINE / BALL GOWN / MERMAID / SHEATH / MINI (יכול להיות מרובה, מופרד בפסיק) |
| Price (USD) | מחיר בדולרים |
| Production Days | ימי ייצור (30-120) |
| Landscape | Raw URL לתמונה הרחבה |
| Portrait | Raw URL לתמונה האנכית |

### שלב 5 — עדכון Base44

1. נכנסים ל-Base44 (פלטפורמת הניהול של האתר/הקטלוג)
2. מייבאים את האקסל של הקולקציה (`<Collection>_URLs.xlsx`)
3. מאשרים את המיפוי של העמודות לשדות במערכת
4. שומרים. הקטלוג מתעדכן והתמונות נטענות מ-GitHub raw.

---

## מבנה לינקים (Raw URL)

תבנית כללית:

```
https://raw.githubusercontent.com/idogolan4955/avians-media/main/<FOLDER>/<DRESS>.jpg
```

**דוגמאות:**

```
# Landscape (אנגלית רגילה — רווחים = %20)
https://raw.githubusercontent.com/idogolan4955/avians-media/main/Regal%20Collection%20Images/REGINA.jpg

# Portrait (תיקיה בעברית - URL-encoded)
https://raw.githubusercontent.com/idogolan4955/avians-media/main/%D7%AA%D7%9E%D7%95%D7%A0%D7%94%20%D7%A8%D7%90%D7%A9%D7%99%D7%AA/REGINA.jpg

# Banner
https://raw.githubusercontent.com/idogolan4955/avians-media/main/banner_hero_1600x900.jpg
```

**מקרא תווי URL:**

| תו | קוד |
|---|---|
| רווח | `%20` |
| ת | `%D7%AA` |
| מ | `%D7%9E` |
| ו | `%D7%95` |
| נ | `%D7%A0` |
| ה | `%D7%94` |
| ר | `%D7%A8` |
| א | `%D7%90` |
| ש | `%D7%A9` |
| י | `%D7%99` |

בקובץ ה-Excel של כל קולקציה הלינקים כבר מקודדים ומוכנים להעתקה.

---

## קולקציות קיימות

| קולקציה | דגמים | קידומת קוד | תיקיית Landscape | תיקיית Portrait |
|---|---:|---|---|---|
| **Regal** (2026) | 20 | R10xx | `Regal Collection Images/` | `תמונה ראשית/` |
| **Gallery** (2026) | 11 | GA-GLY-26xx | `Gallery Collection Images/` | `Gallery - תמונה ראשית/` |
| **ABU DHABI** | 17 | GA-DU-22xx | `ABU DHABI Collection Images/` | `ABU DHABI - תמונה ראשית/` |

**סה"כ: 48 דגמים + 3 כריכות + 3 באנרים.**

---

## הערות

- ה-Repo **פומבי** — אין שימוש בטוקנים זמניים. הלינקים יציבים לשימוש אתר.
- iCloud עלול לעיתים לנעול את `.git/index.lock`. אם Commit נכשל בגלל זה, סגור עורכים פעילים, מחק את הקובץ ידנית מ-Finder ונסה שוב.
- שמות בעברית בתיקיות מצריכים URL-encoding בלינקים. האקסל לכל קולקציה כבר עושה את זה אוטומטית.
- שינוי חזותי או הוספת דגמים → repeat שלבים 1–5.

