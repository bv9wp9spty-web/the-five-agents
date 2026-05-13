---
title: subagent-driven-development
description: סקיל לפיתוח באמצעות subagents בתוך אותו סשן
type: skill
tags: [skill, agents, development]
skill_path: .claude/skills/subagent-driven-development/
created: 2026-05-13
updated: 2026-05-13
---

# subagent-driven-development

**מיקום:** `.claude/skills/subagent-driven-development/`
**טריגר:** ביצוע תכנית יישום עם משימות עצמאיות בתוך אותו סשן.

## מטרה

הפעלת subagents שמקבלים כל אחד תת-משימה עצמאית, אבל בתוך הסשן הראשי.

## קבצים בסקיל

- `SKILL.md`
- `implementer-prompt.md` — פרומפט למיישם.
- `spec-reviewer-prompt.md` — פרומפט לסוקר ספציפיקציות.
- `code-quality-reviewer-prompt.md` — פרומפט לסוקר איכות קוד.

## רלוונטיות לצוות

- [[ראובן]] — מתאים לתהליך עבודה שבו הוא מפעיל את [[יעל]], [[יובל]] ו-[[חן]] במשימות עצמאיות בתוך אותה איטרציה.

## קישורים

- [[.claude - skills]]
- [[MOC - Superpowers]]
- [[dispatching-parallel-agents]] — חלופה למשימות שלא דורשות איכות-קוד-ביניים.
- [[executing-plans]] — מתאים כשהמשימות סדרתיות.
