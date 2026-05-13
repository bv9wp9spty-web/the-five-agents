---
title: yuval (סוכן)
description: תיעוד קובץ ההגדרה של הסוכן יובל - .claude/agents/yuval.md
type: reference
tags: [file-doc, agent-config, yuval]
file_path: .claude/agents/yuval.md
owner: יובל
created: 2026-05-13
updated: 2026-05-13
---

# .claude/agents/yuval.md

**נתיב:** `.claude/agents/yuval.md`
**בעלים:** [[יובל]] (זוהי ההגדרה הקנונית שלו).
**סוג:** קובץ סוכן של Claude Code (sub-agent definition). פלאט MD, לא תקייה — בדומה ל-[[yael (סוכן)]].

## מה הקובץ עושה

מגדיר את [[יובל]] כ-sub-agent של Claude Code. מכיל YAML frontmatter עם המטא-דאטה והוראת השם, ואחריו פרומפט המערכת בעברית שמלמד אותו מה לעשות בכל בקשת תמונה.

## YAML Frontmatter

| שדה | ערך | הערה |
| --- | --- | --- |
| `name` | `yuval` | חובה lowercase-ASCII (מגבלת Claude Code). השם העברי "יובל" בגוף. |
| `description` | משפט אנגלית עם trigger keywords עברית+אנגלית | מה ש[[ראובן]] (Claude הראשי) משתמש בו כדי להחליט מתי לנתב אליו. |
| `tools` | `Read, Write, Bash, Glob` | רשימה מצומצמת. **Bash דרוש** ל-OpenAI API. אין WebSearch, אין Edit, אין MCP. |
| `color` | `blue` | צבע ה-tag בממשק (יעל=pink, יובל=blue). |

## Trigger Keywords

**עברית:** תמונה של, ציור של, תיצור תמונה, איור, תמונת קאבר, באנר.
**English:** image of, picture of, generate image, illustration, draw, cover image, banner.

## מבנה הפרומפט

הפרומפט מחולק לסעיפים:

1. **מי אתה** — תפקיד + המטרה המרכזית (עקביות ויזואלית).
2. **מה אתה לא** — סייגי scope: לא כותב, לא חוקר, לא מנתב.
3. **כלים מותרים** — הסבר למה Bash דרוש.
4. **Flow קבוע לכל בקשת תמונה** — 7 שלבים מ-scan reference ועד דיווח.
5. **כללי-זהב** — 7 כללים, כולל "אל תחליף את שם המודל" וצורך ב-sibling `.txt`.

## תלויות

- **[[gpt-image-gen (סקיל)]]** — הסקיל שיובל משתמש בו לקריאת OpenAI Images API.
- **[[env]]** — `OPENAI_API_KEY` חייב להיות מוגדר.
- **[[yuval]]** — תקיית העבודה: `reference/` ו-`outputs/`.

## קבצים קשורים

- [[יובל]] — דף הסוכן בוולט.
- [[yael (סוכן)]] — תבנית דומה (סוכן ראשון בפרויקט).
- [[.claude - agents]] — תקיית ההגדרות.
- [[CLAUDE.md - תיעוד]] — מתעד את שילוב יעל+יובל בתהליך מאמר-עם-תמונות.
