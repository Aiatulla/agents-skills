# RULES_GENERAL.md

# Language-agnostic rules. Apply to every file in this project.

## Code quality

1. Write code for the next developer, not just the machine.
2. Name variables and functions for what they do, not how they do it.
3. No commented-out code. Use git history instead.
4. No TODO comments without a ticket/issue reference.
5. If you copy-pasted something, stop and extract it into a shared utility.

## SOLID at a glance

- Single Responsibility: one reason to change per module/class/function
- Open/Closed: open for extension, closed for modification
- Liskov Substitution: subtypes must behave like their base type
- Interface Segregation: small, focused interfaces over large general ones
- Dependency Inversion: depend on abstractions, inject dependencies

## DRY (Don't Repeat Yourself)

If the same logic appears twice → extract it.
If the same constant appears twice → name it once.
If the same validation appears twice → centralize it.

## KISS (Keep It Simple)

The simplest solution that correctly solves the problem is the right solution.
Never add abstraction layers that aren't justified by actual requirements.
Never optimize before profiling proves it's needed.

## File size limits

- 200 lines max per file (all languages)
- If a file needs more: it has more than one responsibility. Split it.

## Naming conventions

- Frontend (TS): PascalCase components, camelCase variables/functions, UPPER_SNAKE constants
- Backend (Python): snake_case everything, PascalCase classes, UPPER_SNAKE constants
- Files: kebab-case for frontend, snake_case for backend
- Database tables: snake_case plural (`product_items`, `user_sessions`)

## What never to do

- Never commit secrets, API keys, or credentials
- Never push directly to main/master
- Never skip error handling because "it won't happen"
- Never leave console.log / print() debug statements in committed code
