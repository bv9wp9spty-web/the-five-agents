---
title: graph.json - Obsidian
description: הגדרות תצוגת הגרף של Obsidian
type: reference
tags: [file-doc, obsidian, graph]
file_path: vault/.obsidian/graph.json
owner: ראובן (מנוהל ע"י Obsidian)
created: 2026-05-13
updated: 2026-05-13
---

# graph.json (Obsidian)

**נתיב:** `vault/.obsidian/graph.json`
**בעלים:** [[ראובן]] (מנוהל אוטומטית)
**סוג:** קובץ JSON עם הגדרות תצוגת הגרף.

## מה הקובץ עושה

מגדיר איך נראית תצוגת הגרף (Graph View) של הוולט: סינונים, צבעים, פיזיקה.

## הגדרות עיקריות נוכחיות

- `showTags`: false — תגיות לא מוצגות בגרף.
- `showAttachments`: false — קבצים מצורפים לא מוצגים.
- `hideUnresolved`: false — קישורים לא-קיימים כן מוצגים.
- `showOrphans`: true — פתקים בלי קישורים כן מוצגים.
- `showArrow`: false — בלי חצים על קישורים.
- `centerStrength`: ~0.52 — כוח משיכה למרכז.
- `repelStrength`: 10 — כוח דחייה בין צמתים.
- `linkDistance`: 250 — מרחק קישור.
- `scale`: ~0.067 — זום נוכחי.

## למה זה חשוב

כשראובן יפתח Graph View, אלה ההגדרות שיראה. אם הוא רוצה מראה אחר — דרך Settings → Core plugins → Graph.

## למי הוא משויך

[[ראובן]] בעלים. מתעדכן אוטומטית כשמשנים הגדרות גרף.

## קבצים קשורים

- [[.obsidian]]
- [[MOC - Obsidian]]
- [[core-plugins.json - Obsidian]] — מגדיר שפלאגין הגרף בכלל פעיל.
