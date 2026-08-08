# Repository Guidelines

## Project Structure & Module Organization

This repository is a library of Markdown prompts for fantasy character and creature artwork. Content is grouped by visual system:

- `Animale/`: full-body semi-painterly anime character prompts.
- `Astrael/`: geometric half-body character prompts.
- `Fantasya/`: geometric knee-up character prompts; `Fantasya/Criaturas/` contains the full-creature variant.

Each system normally contains a canonical `*_template.md`, an `instrucoes_criacao_*.md` workflow, `exemplos/` for approved reference outputs, and `personagens/` for generated character prompts. Keep new content in the matching system; do not use root-level files for finished prompts.

## Development & Validation Commands

There is no build system or automated test suite. Review changes with lightweight repository checks:

```bash
git diff --check                 # Detect whitespace errors
git diff -- '*.md'               # Review Markdown and prompt changes
rg '\[[A-Z _-]+\]|\[e\.g\.'    # Find likely unfilled placeholders
find . -name '*.md' -type f      # Inventory prompt documents
```

Before creating a character, read that system's instructions and complete template. Compare examples for expected detail without copying their concepts.

## Writing Style & Naming Conventions

Use UTF-8 Markdown, ATX headings (`#`, `##`), blank lines between sections, and consistent bullet lists. Follow the language already established by each file: input fields are generally written in clear Portuguese, while fixed rendering-engine text remains in English. Never casually rewrite a template's fixed engine or constraints.

Character files follow `Nome - Funcao.md`; when system instructions require it, omit accents from the function portion (for example, `Nome - Cacador de Monstros.md`). Use descriptive lowercase snake_case for templates and instruction files, such as `fantasya_creature_template.md`.

## Testing Guidelines

Validation is editorial. Confirm that every input field is filled, no example placeholders remain, framing and detail budgets match the selected system, and the character is original. Check that filenames are unique before writing. For template edits, inspect representative files in both `exemplos/` and `personagens/` for compatibility.

## Commit & Pull Request Guidelines

Recent history uses Conventional Commit-style subjects such as `feat(astrael): adota padrao geometrico de meio corpo` and `fix: remove json legado`. Use an imperative, concise subject with an optional system scope: `feat(fantasya): ...`, `fix(animale): ...`, or `docs: ...`.

Pull requests should summarize the affected prompt system, explain visual or structural changes, list validation performed, and link any relevant issue. Include before/after excerpts for template changes and generated-image comparisons only when visual output was tested.
