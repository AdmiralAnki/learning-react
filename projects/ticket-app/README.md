# Ticket app

One domain, five implementations. Compare, do not collect toys.

```
01-static/    Phase 1   HTML/CSS only
02-vanilla/   Phase 2–4 JS, then typed + structured
03-api/       Phase 5   same UI, Spring Boot JSON
04-htmx/      Phase 6   selected screens as HTML fragments
05-react/     Phase 8–9 React + TypeScript
```

Create each folder when you start that phase.

## Domain (keep it small)

Ticket: `id`, `title`, `description`, `status` (open / in progress / done), `priority`, `createdAt`.

Screens: dashboard, list, detail, create/edit, delete confirm.

UI: sidebar, modal, toast, loading / empty / error, search, filter, pagination or load-more.

## Rules

- No React before `05-react/`
- No HTMX before `04-htmx/`
- Spring Boot is a REST (and later fragment) backend
- **No Thymeleaf**
- HTMX fragments: HTML files or Java text blocks, not a new template stack

## Spring shape

```
Browser
  HTML/CSS/JS  or  HTMX  or  React
        ↓
Spring Boot
  /api/tickets     JSON
  /fragments/...   HTML (Phase 6 only)
        ↓
Database
```
