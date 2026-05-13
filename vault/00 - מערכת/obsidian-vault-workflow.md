---
title: obsidian-vault-workflow
description: עותק רשמי של הסקיל שמגדיר איך הוולט נבנה ומתוחזק
type: reference
tags: [skill, vault, meta]
created: 2026-05-13
updated: 2026-05-13
source: הודעת המשתמש מ-2026-05-13
---

# Obsidian Vault Workflow

> זהו עותק נאמן של הסקיל שראובן הגדיר ב-2026-05-13. כל שינוי בעקרונות צריך לעבור דרך הפתק הזה תחילה, ואז ליישם בוולט.

**Assistant:** Claude (Sonnet/Opus 4.7)

**Purpose:** Build, maintain, and refactor an Obsidian vault for Israeli AI-team CEO Reuven, blending Personal Knowledge Management (PKM), agent orchestration, and project documentation.

---

## 1. Why this skill exists

Reuven uses Obsidian as a unified workspace for:

- Managing himself and a team of 4 AI agents (Yael, Yuval, Chen, plus Reuven the CEO).
- Centralizing project context, prompts, notes, decisions, and processes.
- Linking knowledge across personal, professional, and creative domains.

The skill gives a clear method to start a vault from scratch, extend an existing one, and refactor a chaotic vault into a clean, navigable system without losing information.

---

## 2. Core principles

1. **Single source of truth** – Obsidian is the canonical workspace for plans, decisions, and team context. External tools (Notion, Drive, ChatGPT chats) feed into it via summaries and links.
2. **Atomic notes** – Each note covers one idea, person, project, or task. Use links instead of long monolithic documents.
3. **Plain Markdown, minimal plugins at first** – Stick to vanilla MD, internal links `[[Note Name]]`, simple folder structure, and YAML frontmatter. Add plugins only when a concrete need emerges.
4. **Bilingual support (HE/EN)** – Use Hebrew titles when natural for Reuven, English for technical/code terms. Headings can mix; tags should be lowercase English for consistency.
5. **Agent-aware structure** – The vault must clearly reflect Reuven's team: who is who, what each agent does, and how they collaborate.
6. **Refactor with care** – Never delete content silently. Move, rename, or archive – and update links.

---

## 3. Standard vault structure

Recommended top-level folders (Hebrew names allowed, English aliases optional):

- `00 - מערכת/` — vault rules, templates, MOCs (Maps of Content), this skill notes.
- `10 - אישי/` — personal life: family, health, finance, journaling.
- `20 - עבודה/` — current job, clients, internal politics, meeting notes.
- `30 - פרויקטים/` — active projects, including the AI team project.
- `40 - סוכנים/` — one folder per agent (Reuven, Yael, Yuval, Chen).
- `50 - ידע/` — domain knowledge: AI, prompting, business, design, etc.
- `60 - יומן/` — daily notes, weekly reviews.
- `90 - ארכיון/` — old projects, deprecated notes.

This is a template; adapt to existing vaults instead of forcing it on Reuven.

---

## 4. Note conventions

### Frontmatter

Every meaningful note should have YAML frontmatter, e.g.:

    ---
    title: שם הפתק
    type: project | person | agent | meeting | idea | reference | daily
    status: active | paused | done | archived
    tags: [team, ai, project-x]
    created: 2025-11-19
    updated: 2025-11-19
    ---

### Naming

- Files: descriptive, Hebrew or English, no dates in filename unless it's a daily/journal note.
- Daily notes: `YYYY-MM-DD.md`.
- Agents: `Reuven.md`, `Yael.md`, `Yuval.md`, `Chen.md` (or Hebrew equivalents).

### Linking

- Use `[[Note Name]]` liberally to weave a knowledge graph.
- Prefer linking over duplicating content.
- For long lists or hubs, build MOC (Map of Content) notes.

---

## 5. Agent & team modeling

For Reuven's AI team, each agent gets a dedicated note in `40 - סוכנים/` with sections for: תפקיד, כלים והרשאות, סגנון ושפה, תקציר פרומפט, פרויקטים פעילים, הערות והיסטוריה.

ראה: [[ראובן]], [[יעל]], [[יובל]], [[חן]].

---

## 6. Project notes

כל פרויקט משמעותי גר תחת `30 - פרויקטים/<project-name>/` עם:

- `Project Hub.md` — MOC ראשי לפרויקט.
- `Decisions.md` — יומן החלטות.
- `Meetings/` — סיכומי פגישות.
- `Specs/` — דרישות, briefs, prompts.
- `Tasks.md` — משימות שוטפות.

ראה: [[Project Hub]].

---

## 7. Daily & weekly workflow

- **Daily notes** (`60 - יומן/`): כוונות בוקר, משימות עיקריות, captures, רפלקציה.
- **Weekly reviews**: גלגול של ה-daily notes, סטטוס פרויקטים, ביצועי סוכנים.

לא הופעל עדיין בוולט הזה.

---

## 8. Refactor playbook

כשאני צריך לסדר וולט קיים: Audit ← הצעת מבנה ← מיגרציה הדרגתית ← בניית MOCs ← ארכוב ← תיעוד המבנה ב-README.

---

## 9. עבודה מול ראובן

- עברית כברירת מחדל, אנגלית לקוד.
- ראובן הוא ה-CEO של הוולט: הוא מחליט, אני מציע ומבצע.
- מאשרים לפני שינוי שמות/מבנה גדול.
- שלוש אופציות (A/B/C) במקום שאלה פתוחה.

---

## 10. בקשות שהסקיל מטפל בהן

- הקמת וולט חדש.
- ריפקטור וולט קיים.
- יצירת דפי סוכנים וקישורם לפרויקטים.
- עיצוב מערכת Daily/Weekly.
- מיגרציה מ-Notion / Drive / ChatGPT.
- כתיבת טמפלטים.

---

## 11. סגנון תגובה

- עברית + אנגלית טכנית.
- מבני תקיות בבלוקי קוד.
- לכל שינוי — הסבר קצר על הרציונל.
- מינימליזם: לא לבנות יותר ממה שנדרש כרגע.
- המשתמש בשליטה.
