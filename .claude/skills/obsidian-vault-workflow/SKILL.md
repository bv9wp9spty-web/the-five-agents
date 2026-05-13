---
name: obsidian-vault-workflow
description: Use whenever any vault work happens — creating, editing, refactoring, linking, or organizing notes in the project's Obsidian vault at vault/. Also use when the user mentions Obsidian, "the vault", notes structure, MOCs, or any of the agents/files/folders documented there. Defines the canonical conventions for this project's vault.
---

# Obsidian Vault Workflow

> Authoritative source: [vault/00 - מערכת/obsidian-vault-workflow.md](../../../vault/00%20-%20%D7%9E%D7%A2%D7%A8%D7%9B%D7%AA/obsidian-vault-workflow.md). Edit there first, this file mirrors it.

**Assistant:** Claude (Sonnet/Opus 4.7)

**Purpose:** Build, maintain, and refactor an Obsidian vault for Israeli AI-team CEO Reuven, blending Personal Knowledge Management (PKM), agent orchestration, and project documentation.

---

## 1. Where the vault lives

`vault/` at the project root. `.obsidian/` config is already inside it. An older vault exists at `.claude/vault/` — it is **archived only, do not edit**.

## 2. Core principles

1. **Single source of truth** – The vault is the canonical workspace for plans, decisions, and team context.
2. **Atomic notes** – Each note covers one idea, person, project, or task. Use links instead of monolithic documents.
3. **Plain Markdown, minimal plugins** – Vanilla MD, internal links `[[Note Name]]`, simple folder structure, and YAML frontmatter.
4. **Bilingual support (HE/EN)** – Hebrew titles for natural Reuven-facing content, English for technical/code. Tags are lowercase English.
5. **Agent-aware structure** – The vault reflects Reuven's team explicitly: who is who, what each agent does, how they collaborate.
6. **Refactor with care** – Never delete content silently. Move, rename, or archive — and update links.

## 3. Standard folder structure

- `00 - מערכת/` — vault rules, MOCs, templates, this skill's mirror.
- `30 - פרויקטים/` — active projects (currently `The Five Agents/`).
- `40 - סוכנים/` — one note per agent (ראובן, יעל, יובל, חן).
- `50 - ידע/` — domain knowledge (Superpowers, Obsidian config).
- Reserved (not yet activated): `10 - אישי/`, `20 - עבודה/`, `60 - יומן/`, `90 - ארכיון/`.

## 4. Note conventions

### Frontmatter

Every meaningful note has YAML frontmatter:

    ---
    title: שם הפתק
    type: project | person | agent | meeting | idea | reference | daily
    status: active | paused | done | archived
    tags: [team, ai, project-x]
    created: YYYY-MM-DD
    updated: YYYY-MM-DD
    ---

### Naming

- Files: descriptive, Hebrew or English, no dates in filename unless it's a daily note.
- Daily notes: `YYYY-MM-DD.md`.
- Agents: first name only (`ראובן.md`, `יעל.md`, `יובל.md`, `חן.md`).
- MOCs: prefix `MOC - ` then the topic.
- File-doc notes: filename or a clear variation of it.

### Linking

- Use `[[Note Name]]` liberally to weave the knowledge graph.
- Prefer linking over duplicating content.
- For long lists or hubs, build MOC notes.

## 5. Agent & team modeling

Each agent gets a dedicated note in `40 - סוכנים/` with sections: תפקיד, כלים והרשאות, סגנון ושפה, תקציר פרומפט, פרויקטים פעילים, הערות והיסטוריה.

Existing notes: [[ראובן]] (CEO), [[יעל]] (writer), [[יובל]] (designer), [[חן]] (researcher).

## 6. Project notes

Each significant project lives under `30 - פרויקטים/<project-name>/` with at least a `Project Hub.md` (MOC), plus optional `קבצים/` (file docs), `תקיות/` (folder docs), `Decisions.md`, `Meetings/`, `Specs/`, `Tasks.md`.

## 7. Daily & weekly workflow

Not active yet. Reserved for `60 - יומן/` when Reuven chooses to enable.

## 8. Refactor playbook

When reorganizing an existing vault: Audit → propose structure → migrate gradually → build MOCs → archive (don't delete) → document the structure in `Vault README.md`.

## 9. Working with Reuven

- Hebrew by default, English for code/technical terms.
- Reuven is the CEO of the vault: he decides, I propose and execute.
- Confirm before renames or large structural changes.
- Offer 3 options (A/B/C) instead of open-ended questions.

## 10. Requests this skill handles

- Starting a new vault.
- Refactoring an existing vault.
- Creating agent pages and linking them to projects.
- Designing Daily/Weekly systems.
- Migrating from Notion / Drive / ChatGPT.
- Writing templates.

## 11. Response style

- Hebrew + technical English.
- Folder structures in code blocks.
- Each change comes with a short rationale.
- Minimalism: don't build more than what's currently needed.
- The user stays in control.

---

## Pointer to the canonical copy

Full version with link-rich navigation, in Hebrew, lives at:
**`vault/00 - מערכת/obsidian-vault-workflow.md`**

Any change to principles should be edited there first, then reflected back here.
