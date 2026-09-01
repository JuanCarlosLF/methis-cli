---
name: pr-generation
description: PR title, PR description, and GitHub pull request body. Use when drafting or rewriting a pull request title/body from a change summary.
---

# PR Generation

Use this skill to write GitHub PR titles and descriptions that match the ticket convention established in Trello.

## Title

- Format: `[TICKET]: short imperative summary`
- Obtain the ticket identifier and naming convention from the relevant Trello card or board
- Put the ticket first, preserving the casing and punctuation used in Trello
- Keep it one line, factual, and outcome-focused
- Start with a verb such as `Add`, `Remove`, `Update`, `Rename`, `Complete`, or `Document`
- Avoid vague wording and avoid extra commentary

Examples:

- `[ABC-123]: Add initial project configuration`
- `[ABC-X]: Add reusable project convention`

## Body

Use this structure:

```md
## Ticket
ABC-123

## Description
One sentence describing what changes and why.

## Development
Concrete implementation details, grouped by what was changed.

## Validation
- [x] Unit tests — 89 passed (`./gradlew testDebugUnitTest`)
- [x] Manual verification — tested on emulator API 34
```

## Rules

- Treat Trello as the source of truth for the ticket identifier and convention
- Inspect the relevant Trello context before drafting the PR when it is available
- If the ticket is missing, ambiguous, or cannot be identified confidently, ask the user before writing the title
- Never invent a ticket identifier or infer one from unrelated repository content
- Keep `Description` short and high-level
- Use `Development` for technical specifics, file areas, behavior changes, or ADRs
- Use `Validation` for observed test/build results that were run; do not list what was not run — absence implies not verified
- Keep the tone direct and factual
- Do not invent benefits or write marketing copy

## Default phrasing

- `Description`: what the change does and the reason it matters
- `Development`: how the code changed and why, if needed
- `Validation`: what was verified in this session
