# React Curriculum — Phases 8–10

This is the **React-specific** plan, not the whole path. Overall order and checkboxes: [README.md](README.md). Phases 1–7: [pre-react-path.md](pre-react-path.md).

You should already have a ticket app in vanilla JS, on a Spring Boot JSON API, and (in part) in HTMX. React is the third implementation.

Course names/versions shift. Search FEM before starting. Do not invent courses.

---

## Phase 8 — React + TypeScript

**Primary**

- **Complete Intro to React, v9** — Brian Holt  
  Hooks-first, Vite, modern React 18/19. Catalog title is sometimes “The Complete Intro to React Course.”  
  This version also introduces **TanStack Router** and **TanStack Query**. Treat those as first contact, not the whole of Phase 9.

- **Intermediate React, v6: RSCs, Hooks, & Performance** — Brian Holt  
  Next step after Complete Intro: React 19, render modes, `useTransition`, performance. Some RSC material overlaps Phase 10 — skim if you are not on Next.js yet.

**Optional if TS + React still feels awkward**

- **React and TypeScript, v3** — Steve Kinney

Do the course exercises in TypeScript even if a demo is JS.

### Topics

JSX/TSX, components, typed props, state, events, conditional render, lists/keys, forms, `useState`, `useEffect`, lifting state, Context, custom hooks, API calls.

Tooling (old “Phase 4”) is folded in here: `npm`/`pnpm`, Vite + React + TS, React DevTools.

### Projects

Course-sized: counter, todo, API-driven UI, multi-step form.

**Main:** rebuild the ticket app (`projects/ticket-app/05-react/`). Same screens as vanilla/HTMX.

After each major piece, add a short note in [notes/comparisons.md](notes/comparisons.md):

| Feature | Vanilla | HTMX | React |
|---|---|---|---|
| Modal | | | |
| List + filter | | | |
| Form submit | | | |
| Detail route | | | |

That comparison is a goal of this phase, not extra credit.

---

## Phase 9 — Production React

Only what you will use on a real app. One choice per job.

**FEM when it exists**

| Need | Course / source |
|---|---|
| Client state at scale | **State Management at Scale in React & Next.js** — David Khourshid |
| Testing (Vitest, Testing Library) | **Testing Fundamentals** — Steve Kinney |
| Performance (if Intermediate v6 was not enough) | **React Performance, v2** — Steve Kinney |
| Accessibility | **Website Accessibility, v3** — Jon Kuperman and/or **Web App Accessibility (feat. React)** — Marcy Sutton Todd |
| TanStack Query, deeper | **TanStack Start & TanStack Query** — Adam Rackis (optional; v9 already introduces Query) |

**Official docs (no current dedicated FEM course used here)**

- [React Router](https://reactrouter.com/) — v9 teaches TanStack Router. Learn one well; skim the other so work codebases make sense.
- [React Hook Form](https://react-hook-form.com/) — no FEM course found.

**Pick**

- Server/async state: TanStack Query (not also SWR + RTK Query)
- Client state: **Zustand or Redux Toolkit**, not both
- CSS: keep what you have (plain CSS / CSS Modules). Tailwind only if you want it
- Deploy: Vercel or Netlify for the React SPA; Spring Boot still hosts the API

JWT/Keycloak specifics are your work project + official docs, not a FEM course.

**Capstone:** production-shaped ticket frontend — routing, query cache, one client store if needed, tested happy paths, deployed. Or the frontend for your microservices work, using the same habits.

---

## Phase 10 — Next.js (optional)

A React SPA + Spring Boot API is a complete architecture. Next.js is a different deployment and rendering model, not a promotion.

**FEM:** **Next.js Fundamentals, v4** — Scott Moss

Cover: mental model, App Router, SSR vs SSG, server vs client components, routing. Stop when you can explain when Next.js is worth the complexity.

FEM also lists **Intermediate Next.js** and **Build a Fullstack Next.js App, v4** — only if you are actually shipping Next.js.

---

## Using FEM

- Individual ~$39/month or ~$390/year; annual wins after ~10 months of real use
- Confirm version numbers. Old recordings disappear or teach stale patterns
- FEM’s **React & Next.js** and **TypeScript** learning paths are a useful cross-check, not a replacement for this order
- Log the exact course + version you took in the README checklist

---

## Suggested rhythm (React block only)

| Stretch | Focus | Primary FEM |
|---|---|---|
| 2 weeks | React + TS + ticket rebuild | Complete Intro to React, v9 → Intermediate React, v6 |
| 1–2 weeks | Production habits on that app | State management, Testing Fundamentals |
| Optional | Next.js | Next.js Fundamentals, v4 |

Pre-React phases are not compressed into this table on purpose.
