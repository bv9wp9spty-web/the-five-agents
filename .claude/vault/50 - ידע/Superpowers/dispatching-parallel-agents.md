---
title: dispatching-parallel-agents
description: סקיל להפעלת סוכנים במקביל למשימות עצמאיות
type: skill
tags: [skill, agents, parallel]
skill_path: .claude/skills/dispatching-parallel-agents/
created: 2026-05-13
updated: 2026-05-13
---

# dispatching-parallel-agents

**מיקום:** `.claude/skills/dispatching-parallel-agents/`
**טריגר:** מעל שתי משימות עצמאיות שניתן לעבוד עליהן בלי תלות הדדית.

## מטרה

הפעלת מספר סוכנים במקביל כשאין תלויות ביניהם — חוסך זמן ושומר על קונטקסט המאסטר.

## קבצים בסקיל

- `SKILL.md` — הסקיל היחיד.

## רלוונטיות לצוות

- [[ראובן]] — **הסקיל הכי רלוונטי עבורו**. כשבקשה דורשת גם טקסט וגם תמונה, יכול להפעיל את [[יעל]] ו-[[יובל]] במקביל.
- [[חן]] — יכולה לחקור מספר נושאים במקביל.

## קישורים

- [[.claude - skills]]
- [[MOC - Superpowers]]
- [[subagent-driven-development]] — אפשרות חלופית/משלימה (subagents במקום סוכנים מקבילים).
