---
title: .gitignore
description: תיעוד חוקי Git ignore של הפרויקט
type: reference
tags: [file-doc, git, config]
file_path: .gitignore
owner: ראובן
created: 2026-05-13
updated: 2026-05-13
---

# .gitignore

**נתיב:** `.gitignore`
**בעלים:** [[ראובן]]
**סוג:** קובץ Git שמציין מה לא להעלות.

## מה הקובץ עושה

מונע מ-Git לעקוב אחרי קבצים שאסור או מיותר לשתף.

## מה מוחרג

- **סודות**: `.env`, `.env.local`, `.env.*.local` — ראה [[env]].
- **קבצי מערכת**: `.DS_Store` (macOS), `Thumbs.db` (Windows).
- **קבצי IDE**: `.vscode/`, `.idea/`.
- **לוגים**: `*.log`.

## למה זה חשוב

- מונע דליפת מפתחות API ל-Git (ראה [[env]]).
- שומר על נקיון ה-repository.

## למי הוא משויך

תחזוקתי של [[ראובן]] — הוא מוסיף כללים חדשים כשצריך.

## קבצים קשורים

- [[env]] — הקובץ שמוחרג בעיקר.
- [[env.example]] — לא מוחרג (מותר ומומלץ להעלות ל-Git).
