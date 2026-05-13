---
title: MOC - Obsidian
description: אינדקס של קבצי הקונפיג של Obsidian (.obsidian/) ומה כל אחד עושה
type: reference
tags: [moc, obsidian, config]
created: 2026-05-13
updated: 2026-05-13
---

# MOC — Obsidian

תקיית `.obsidian/` בתוך [[vault]] מחזיקה את כל הקונפיג של אפליקציית Obsidian עצמה. חמישה קבצים שעובדים יחד.

## הקבצים

- [[.obsidian]] — התקייה עצמה.
- [[app.json - Obsidian]] — הגדרות אפליקציה כלליות.
- [[appearance.json - Obsidian]] — תמה, מצב כהה, פונט.
- [[core-plugins.json - Obsidian]] — אילו פלאגינים בסיסיים מופעלים.
- [[graph.json - Obsidian]] — הגדרות תצוגת ה-Graph.
- [[workspace.json - Obsidian]] — מצב המסך הנוכחי (פתחים, חלוקה, lists).

## למי הם משויכים

[[ראובן]] — הוא הבעלים של הוולט. אבל בפועל, הקבצים האלה **מתעדכנים אוטומטית** על ידי Obsidian. בדרך כלל לא נוגעים בהם ידנית.

## האם להעלות ל-Git?

יש מחלוקת מקובלת:

- **כן**: שומר על הגדרות אחידות בין מחשבים. מומלץ לפלאגינים ולגרף.
- **לא**: `workspace.json` משתנה כל הזמן (מצב הפתחים), יוצר רעש ב-Git.

הסטטוס הנוכחי: התקייה לא מופיעה ב-[[gitignore]], אז Git **כן** עוקב אחריה.

## קבצים קשורים

- [[vault]] — תקיית האם.
- [[gitignore]] — מקום פוטנציאלי להחרגה עתידית של `workspace.json`.
