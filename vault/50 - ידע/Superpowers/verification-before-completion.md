---
title: verification-before-completion
description: סקיל לאימות לפני שטוענים שמשהו גמור
type: skill
tags: [skill, verification, quality]
skill_path: .claude/skills/verification-before-completion/
created: 2026-05-13
updated: 2026-05-13
---

# verification-before-completion

**מיקום:** `.claude/skills/verification-before-completion/`
**טריגר:** לפני שמכריזים שמשימה גמורה / תוקנה / עברה, לפני commit, לפני פתיחת PR.

## מטרה

ראיות לפני הצהרות. דורש הרצת פקודות אימות וקבלת אישור אמיתי לפני כל טענת הצלחה.

## קבצים בסקיל

- `SKILL.md` — הסקיל היחיד.

## רלוונטיות לצוות

- [[ראובן]] — לפני שמדווח למשתמש שהמשימה הושלמה.
- [[יעל]], [[יובל]], [[חן]] — כל אחד אחרי שגמר את התוצר שלו.

## קישורים

- [[.claude - skills]]
- [[MOC - Superpowers]]
- [[systematic-debugging]]
- [[requesting-code-review]]
- [[finishing-a-development-branch]]
