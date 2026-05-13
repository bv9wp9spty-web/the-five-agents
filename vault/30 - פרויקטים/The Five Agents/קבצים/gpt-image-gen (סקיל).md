---
title: gpt-image-gen (סקיל)
description: תיעוד הסקיל ליצירת תמונות דרך OpenAI Images API
type: reference
tags: [file-doc, skill, images, openai]
file_path: .claude/skills/gpt-image-gen/SKILL.md
owner: יובל
created: 2026-05-13
updated: 2026-05-13
---

# .claude/skills/gpt-image-gen/SKILL.md

**נתיב:** `.claude/skills/gpt-image-gen/SKILL.md`
**בעלים שעיקרי משתמש בו:** [[יובל]].
**סוג:** סקיל פרויקטלי של Claude Code (לא חלק מ-Superpowers).

## מה הסקיל עושה

מעטפת דקה לקריאת `POST /v1/images/generations` של OpenAI. מקבל prompt וגודל, ומחזיר PNG שמור בדיסק.

הסקיל הזה **לא בוחר סגנון ולא מנסח prompt** — אלה תפקידי הסוכן שקורא לו (כרגע [[יובל]] בלבד).

## YAML Frontmatter

| שדה | ערך |
| --- | --- |
| `name` | `gpt-image-gen` |
| `description` | משפט אנגלי שמסביר מתי להפעיל את הסקיל. כולל את שם המודל. |

## המודל

**`gpt-image-2`** — המודל הסטנדרטי של OpenAI ליצירת תמונות (יצא 21.4.2026). הסקיל מכיל אזהרה מודגשת:

> אם הקריאה נכשלת — הבעיה היא ב-API key, parameters, או rate limit. **לא בשם המודל.** אסור להחליף ל-`dall-e-3` או `gpt-image-1` כניסיון לפתור שגיאה.

## דרישות סביבה

- `OPENAI_API_KEY` ב-[[env]] (מוגדר).
- `curl` + `jq` + `base64` (path מועדף), או `curl` + `python` (fallback).

## ה-flow המרכזי

1. טעינת `OPENAI_API_KEY` מ-`.env`.
2. `curl` ל-`https://api.openai.com/v1/images/generations` עם body שכולל `model`, `prompt`, `size`, `quality`, `output_format`.
3. פענוח `data[0].b64_json` (jq → base64 → file, או Python fallback).
4. אימות שהקובץ קיים ולא ריק.

## פרמטרים

| שדה | ערכים | ברירת מחדל |
| --- | --- | --- |
| `size` | `1024x1024`, `1536x1024`, `1024x1536` | `1024x1024` |
| `quality` | `low`, `medium`, `high` | `medium` |
| `output_format` | `png`, `jpeg`, `webp` | `png` |

## מי משתמש בו

- [[יובל]] — בכל בקשת תמונה. הוא **חייב** לקרוא לסקיל הזה — אין דרך אחרת מאושרת ליצירת תמונות.

## קבצים קשורים

- [[יובל]] — הסוכן המשתמש העיקרי.
- [[yuval (סוכן)]] — קובץ ההגדרה שלו, מקשר חזרה לכאן.
- [[env]] / [[env.example]] — מקור ה-API key.
- [[.claude - skills]] — תקיית הסקילים.
