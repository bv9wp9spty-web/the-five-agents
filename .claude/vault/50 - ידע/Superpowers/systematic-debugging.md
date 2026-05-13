---
title: systematic-debugging
description: סקיל לדיבאג שיטתי לפני שמציעים תיקון
type: skill
tags: [skill, debugging, quality]
skill_path: .claude/skills/systematic-debugging/
created: 2026-05-13
updated: 2026-05-13
---

# systematic-debugging

**מיקום:** `.claude/skills/systematic-debugging/`
**טריגר:** כשנתקלים בבאג, כשל בטסט, או התנהגות לא צפויה — לפני שמציעים תיקון.

## מטרה

לא לקפוץ לתיקון. למצוא קודם את שורש הבעיה.

## קבצים בסקיל

- `SKILL.md` — הסקיל הראשי.
- `root-cause-tracing.md` — מתודולוגיה.
- `defense-in-depth.md` — אסטרטגיית הגנה.
- `condition-based-waiting.md` + `condition-based-waiting-example.ts` — דוגמה לדפוס.
- `find-polluter.sh` — סקריפט עזר.
- `CREATION-LOG.md` — לוג יצירה.
- מספר קבצי טסט (`test-academic.md`, `test-pressure-1.md`, `test-pressure-2.md`, `test-pressure-3.md`).

## רלוונטיות לצוות

- פחות רלוונטי לעולם התוכן הקלאסי. רלוונטי מאוד אם הצוות יזדקק לבדוק בעיות בפייפליין שלו (לדוגמה: API שלא מחזיר תגובות שניתן לפרסם).

## קישורים

- [[.claude - skills]]
- [[MOC - Superpowers]]
- [[verification-before-completion]] — אחרי שתיקנו, לוודא שזה באמת נפתר.
