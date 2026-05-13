---
title: workspace.json - Obsidian
description: מצב הפתחים והתצוגה הנוכחי של Obsidian
type: reference
tags: [file-doc, obsidian, workspace]
file_path: vault/.obsidian/workspace.json
owner: ראובן (מנוהל ע"י Obsidian)
created: 2026-05-13
updated: 2026-05-13
---

# workspace.json (Obsidian)

**נתיב:** `vault/.obsidian/workspace.json`
**בעלים:** [[ראובן]] (מנוהל אוטומטית)
**סוג:** קובץ JSON שמתאר את מצב המסך הנוכחי.

## מה הקובץ עושה

שומר את החלוקה של חלון Obsidian: אילו פתקים פתוחים, באילו לשוניות, איזה צד פתוח, איזה גודל לכל פאנל.

## למה לשים לב

הקובץ הזה **משתנה כל פעם שראובן עובד**. כל פתיחה/סגירה של טאב, כל גרירה של פאנל — מעדכנים את הקובץ. אם הוא ב-Git, יהיו הרבה commits של "workspace state" בלי תוכן אמיתי.

**המלצה עתידית:** אם הולכים לעבוד מכמה מחשבים, להחריג את הקובץ הזה ב-[[gitignore]]:

    vault/.obsidian/workspace.json

(או להעביר לתקייה `.obsidian/workspace.json` אם רוצים החרגה ספציפית.)

נכון לעכשיו לא מוחרג. ראובן יחליט.

## תוכן נוכחי

המבנה כולל `main` (חלוקת הפאנל הראשי), `left` ו-`right` (סיידברים), `active` (הפתק הפעיל). כל פאנל עם רשימת `children`.

## למי הוא משויך

[[ראובן]] בעלים — אבל לא נוגעים ידנית, מתעדכן אוטומטית.

## קבצים קשורים

- [[.obsidian]]
- [[MOC - Obsidian]]
- [[gitignore]] — מקום פוטנציאלי להחרגה עתידית.
