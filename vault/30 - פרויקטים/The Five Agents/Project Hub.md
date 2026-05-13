---
title: Project Hub - The Five Agents
description: ה-MOC המרכזי של פרויקט תשתית הצוות
type: project
status: active
tags: [project, hub, moc, ai-team]
created: 2026-05-13
updated: 2026-05-13
---

# The Five Agents — Project Hub

מערכת תשתית לצוות של ארבעה סוכני AI ליצירת תוכן. הפרויקט מאפשר תהליך עבודה מסודר שבו [[ראובן]] (מנכ"ל) מקבל בקשות מהמשתמש ומנתב אותן לחבר הצוות המתאים: [[יעל]], [[יובל]], או [[חן]].

## סטטוס

**שלב נוכחי:** תשתית מתקדמת. שני סוכנים מוגדרים (יעל + יובל), סקיל פרויקטלי ראשון נוצר (`gpt-image-gen`). [[חן]] עדיין לא מוגדרת. אין פקודות תחת `.claude/commands/`.

## הצוות

ראה [[MOC - הצוות]] לסקירה מלאה.

- [[ראובן]] — CEO, ניתוב.
- [[יעל]] — כתיבת תוכן.
- [[יובל]] — עיצוב תמונות.
- [[חן]] — מחקר.

## קבצים בשורש הפרויקט

- [[CLAUDE.md - תיעוד]] — הגדרת ראובן והצוות (קובץ הוראות לקלוד).
- [[env]] — קובץ הסביבה האמיתי עם המפתחות (לא ב-Git).
- [[env.example]] — תבנית המפתחות לשיתוף.
- [[gitignore]] — חוקי Git.
- [[yael (סוכן)]] — קובץ ההגדרה של [[יעל]] (`.claude/agents/yael.md`).
- [[yuval (סוכן)]] — קובץ ההגדרה של [[יובל]] (`.claude/agents/yuval.md`).
- [[gpt-image-gen (סקיל)]] — סקיל ליצירת תמונות דרך OpenAI Images API (`.claude/skills/gpt-image-gen/SKILL.md`).

## תקיות הפרויקט

- [[.claude]] — תקיית התשתית של Claude Code.
  - [[.claude - agents]] — הגדרות סוכנים (יעל ויובל מוגדרים, חן עדיין לא).
  - [[.claude - commands]] — פקודות מותאמות (ריקה).
  - [[.claude - skills]] — סקילים מותאמים (Superpowers + obsidian-vault-workflow + example-skills).
  - [[.claude - vault]] — הוולט הראשון (ארכיון, מ-13.5.2026).
- [[vault]] — הוולט הפעיל (הוולט הזה).
- [[Content]] — מאמרי גלם נכנסים לעיבוד של [[יעל]].
- [[Output]] — תוצרים יוצאים של [[יעל]] (.md + .html).
- [[yael]] — תקיית העבודה של [[יעל]] (style guide + reference).
- [[yuval]] — תקיית העבודה של [[יובל]] (reference + outputs).

## ידע תומך

- [[MOC - Superpowers]] — אינדקס של 14 סקילים שמותקנים תחת `.claude/skills/`.
- [[MOC - Obsidian]] — קונפיג הוולט עצמו.
- [[obsidian-vault-workflow]] — הסקיל שמגדיר איך הוולט מתוחזק.

## החלטות פתוחות

- מתי לכתוב קובץ הגדרה ל-[[חן]]?
- אילו פקודות צריך לבנות תחת `.claude/commands/`?
- מה לעשות עם [[.claude - vault]] (הוולט הראשון)? למחוק/לארכב/להשאיר?
- מתי [[ראובן]] יכתוב את `yael/style-guide.md` ו-`yael/reference/`?
- מתי המשתמש יוסיף תמונות השראה ל-`yuval/reference/`?

## הערות והיסטוריה

- **2026-05-13** — סוכן שני: [[יובל]] קיבל קובץ הגדרה ב-`.claude/agents/yuval.md`. נוצרו תקיות `yuval/reference/` ו-`yuval/outputs/`. נוצר סקיל פרויקטלי ראשון: [[gpt-image-gen (סקיל)]] שעוטף את OpenAI Images API. `CLAUDE.md` עודכן עם תהליך מלא של מאמר-עם-תמונות + מילות טריגר ליובל. [[יעל]] עודכנה לסמן `{{IMAGE_NEEDED: ...}}` placeholders בזמן כתיבה.
- **2026-05-13** — סוכנת ראשונה: [[יעל]] קיבלה קובץ הגדרה ב-`.claude/agents/yael.md`. תקיות `Content/`, `Output/`, `yael/`, `yael/reference/` הוקמו. `CLAUDE.md` עודכן עם מילות-טריגר לניתוב אוטומטי.
- **2026-05-13** — הוולט החדש (`vault/`) הוקם. תיעוד מלא של כל קבצי הפרויקט והתקיות.
- **2026-05-13** — הוולט הראשון (`.claude/vault/`) הוקם. נשאר כארכיון.
- **2026-05-13** — Superpowers v5.1.0 הותקן (commit `89cfe2a`).
- **2026-05-13** — `.env.example` ו-`.gitignore` נוספו (commit `235b4a2`).
- **2026-05-13** — תשתית ראשונית (commit `205fc18`).
