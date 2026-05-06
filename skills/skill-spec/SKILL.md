---
name: skill-spec
description: Use this skill when authoring or reviewing a Claude Code skill package, to apply the canonical spec — folder layout, SKILL.md shape, frontmatter, progressive disclosure — and avoid the common skill/agent/orchestrator confusions.
---

# Skill Spec

When this skill is activated, guide the host agent through authoring or reviewing a skill package against the canonical spec.

## When to use

- Creating a new skill (folder layout, `SKILL.md`, frontmatter).
- Reviewing whether an existing folder is well-formed as a skill.
- Deciding whether a capability belongs in a skill, an agent, or an orchestrator.
- Writing or revising a skill's `description` for discovery.

## Core rule

> An agent executes. A skill instructs.

A skill packages reusable workflow knowledge. It does not own the model, tools, permissions, memory, turn loop, or final responsibility — those belong to the host agent.

## Workflow

1. **Read the canonical reference**: `references/skill-anatomy.md`. It is the single source of truth for what a skill is, the canonical tree, `SKILL.md` shape, frontmatter, progressive disclosure, and what does *not* belong in a skill folder.
2. **Apply the canonical tree**: `SKILL.md` is required; `scripts/`, `references/`, `assets/`, `requirements.txt`, `tests/` are optional and added only when used.
3. **Write a discovery-grade `description`** that names both *what* the skill does and *when* to use it. Weak descriptions ("Helps with research.") fail routing.
4. **Push details out of `SKILL.md`** into `references/` or `assets/` whenever the host only needs them in a specific branch of the workflow. Keep `SKILL.md` short, procedural, and action-oriented.
5. **Avoid runtime-claiming language**. Do not write "this skill spawns agents", "this skill uses model X", or "this skill grants tool Y". Prefer "if the host supports delegation, it may assign …".
6. **Keep the package self-contained**. Paths inside `SKILL.md` are relative to the skill root; do not depend on files outside the skill directory unless explicitly documented.

## Reference

- `references/skill-anatomy.md` — the full canonical chapter. Load it whenever the host needs the authoritative wording, the do/avoid examples, or the lists of what does and does not belong in a skill folder.
