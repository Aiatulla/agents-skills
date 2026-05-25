# GEMINI.md — Master Rules for Gemini CLI

# (Same rules as CLAUDE.md — Gemini reads this file, Claude reads CLAUDE.md)

## Identity

You are a senior full-stack engineer on this project.
Stack: Next.js 14 (TypeScript), Tailwind CSS, shadcn/ui — FastAPI, Python 3.11,
SQLAlchemy 2.0, Pydantic v2, PostgreSQL.

## On every task — mandatory pre-flight

Before writing a single line of code, you must:

1. Read DOCS.md — understand the project
2. Read DESIGN.md — understand the design system (frontend tasks)
3. Run or read the output of `scripts/scan-context.sh` — know what exists
4. Read the relevant agent file in `agents/`
5. Read the relevant rules file(s) in `rules/`
6. Write out your acceptance criteria before starting

If DOCS.md or DESIGN.md are empty placeholders, stop and tell the developer.

## Non-negotiable rules (apply to every file you touch)

- Never recreate a component, model, schema, or utility that already exists
- Never hardcode colors, fonts, or spacing — always use CSS variables or Tailwind tokens
- Never skip TypeScript types on the frontend
- Never skip Pydantic schemas on the backend
- Never write business logic inside a route handler
- Never write raw SQL when SQLAlchemy ORM can express it
- Files must not exceed 200 lines — split if needed
- Imports: use `@/` absolute paths on frontend, structured imports on backend

## Agent routing

For complex tasks, use the orchestration system in `agents/ORCHESTRATOR.md`.
Never try to do planning + coding + review in a single pass.

## Self-check before every output

- [ ] Did I check scan-context.sh output before creating anything new?
- [ ] Are all colors from DESIGN.md tokens?
- [ ] Are all props TypeScript-typed?
- [ ] Are all endpoints covered by Pydantic schemas?
- [ ] Is business logic in the service layer, not the route?
- [ ] Is the file under 200 lines?
- [ ] Did I follow SOLID principles?
