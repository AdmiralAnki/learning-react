# Web Frontend Learning

Repo name stays `learning-react`. Scope is broader: learn the web platform first, then choose React deliberately.

Single source of truth. Edit checkboxes here, keep notes in `/notes`, keep the evolving ticket app in `/projects`.

```
HTML/CSS
   ↓
JavaScript
   ↓
Vanilla JS
   ↓
Spring Boot API
   ↓
HTMX
   ↓
Frontend Architecture
   ↓
React + TypeScript
   ↓
Production React
```

Numbered phases below add TypeScript and a vanilla-app refactor inside the Vanilla JS stretch, then a short “why frameworks” pause (Frontend Architecture on the diagram) after HTMX.

**Why HTMX before React:** after a real vanilla JS + Spring Boot app exists, HTMX shows a second way to update the UI (server returns HTML fragments). Comparing that to `fetch` + DOM work makes React’s job obvious instead of magical.

Philosophy: **Learn → Build → Break → Recall → Rebuild**. See [strategy.md](strategy.md).

---

## Setup

```bash
git clone git@github.com:AdmiralAnki/learning-react.git
cd learning-react
git pull    # start of every session
# …work…
git add .
git commit -m "Phase 2: event delegation + ticket list"
git push    # end of every session
```

**Always `pull` before starting, `push` before stopping.**

---

## Documents

| Doc | Role |
|---|---|
| [phase-0-mental-model.md](phase-0-mental-model.md) | Web platform + UIKit mapping |
| [pre-react-path.md](pre-react-path.md) | Phases 1–7 detail (HTML through why frameworks) |
| [react-learning-roadmap-v3-fem.md](react-learning-roadmap-v3-fem.md) | Phases 8–10 detail (React curriculum) |
| [strategy.md](strategy.md) | How to study |
| [projects/ticket-app/README.md](projects/ticket-app/README.md) | One evolving ticket app |
| [notes/gotchas.md](notes/gotchas.md) | Things that trip you up |
| [notes/cheatsheet.md](notes/cheatsheet.md) | Syntax only |
| [notes/journal.md](notes/journal.md) | Daily log |
| [notes/comparisons.md](notes/comparisons.md) | Vanilla vs HTMX vs React |

Course names/versions change. Search the [Frontend Masters catalog](https://frontendmasters.com/) (may redirect to master.dev) before starting a phase.

---

## Progress

Check items off in this file (`- [x]`). GitHub renders checkboxes.

### Phase 0 — Web Mental Model
- [ ] Read [phase-0-mental-model.md](phase-0-mental-model.md)
- [ ] Can explain request → HTML/CSS/JS → DOM → paint
- [ ] Can place Spring Boot, HTMX, and React on that path

### Phase 1 — HTML + CSS
Courses: **Getting Started with CSS, v2** (Jen Kramer) · **Intermediate HTML & CSS** (Jen Kramer) · **Ultimate CSS Grid & Layout Techniques, v3** (Jen Kramer)
- [ ] Semantic HTML + forms
- [ ] Box model, cascade, specificity, inheritance
- [ ] Flexbox (Flexbox Froggy optional)
- [ ] Grid (CSS Grid Garden optional)
- [ ] Responsive layout / media queries
- [ ] Accessibility fundamentals (labels, headings, keyboard)
- [ ] **Project:** static ticket UI — dashboard, list, details, form, modal, sidebar

### Phase 2 — JavaScript + Vanilla App
Courses: **Deep JavaScript Foundations, v3** (Kyle Simpson) · **Vanilla JS: You Might Not Need a Framework** (Maximiliano Firtman)
- [ ] Values, types, objects, arrays, functions
- [ ] Scope, closures, `this`
- [ ] Destructuring, spread/rest, array methods
- [ ] Promises, async/await, event loop
- [ ] ES modules
- [ ] DOM APIs, events, event delegation
- [ ] Forms + browser validation
- [ ] `fetch`, HTTP, JSON
- [ ] Browser storage, URL / History APIs
- [ ] **Project:** vanilla JS ticket app (no React, no HTMX)

### Phase 3 — TypeScript
Course: **TypeScript 5+ Fundamentals, v4** (Mike North)
- [ ] Basic types, interfaces, aliases, unions, narrowing
- [ ] Function types, generics, optional properties, inference
- [ ] Compile-time types vs runtime validation
- [ ] **Project:** type the ticket app’s data + API layer

### Phase 4 — Frontend Architecture (no framework)
Course: **The Hard Parts of UI Development** (Will Sentance) — watch for the mental model. Do **not** build a homemade React.
- [ ] Separate app / UI / server / derived state
- [ ] Modules: API, render, events
- [ ] Loading / error / empty states
- [ ] Client-side routing + URL state
- [ ] **Project:** refactor the vanilla ticket app. Stop before inventing a framework.

### Phase 5 — Spring Boot REST API
No FEM course — you already know Java/Spring. Official Spring docs only.
- [ ] REST controllers, DTOs, validation, JSON
- [ ] Pagination, filtering, sorting, error body
- [ ] CORS + same-origin
- [ ] Auth concepts (enough to call a protected API)
- [ ] **Project:** point the vanilla app at a real API. **No Thymeleaf.**

### Phase 6 — HTMX
Primary: [htmx.org/docs](https://htmx.org/docs/). Optional FEM: **HTMX & Go** (ThePrimeagen) — HTMX ideas only; ignore Go/templates. Spring Boot stays the backend.
- [ ] Mental model: server returns HTML fragments
- [ ] `hx-get` / `hx-post` / `hx-put` / `hx-delete`
- [ ] `hx-target`, `hx-swap`, `hx-trigger`, `hx-push-url`
- [ ] Forms, indicators, history, pagination, search, filter
- [ ] **Project:** rebuild selected ticket screens with HTMX. HTML fragments without Thymeleaf.

### Phase 7 — Why Frameworks Exist
No course. Write the comparison yourself.
- [ ] Fill [notes/comparisons.md](notes/comparisons.md) for list, form, modal, navigation
- [ ] Know when vanilla, HTMX, or React starts to hurt

### Phase 8 — React + TypeScript
Detail: [react-learning-roadmap-v3-fem.md](react-learning-roadmap-v3-fem.md)

Courses: **Complete Intro to React, v9** (Brian Holt) · **Intermediate React, v6: RSCs, Hooks, & Performance** (Brian Holt)
- [ ] JSX/TSX, components, props, state, events
- [ ] Lists/keys, forms, `useState`, `useEffect`
- [ ] Lifting state, Context, custom hooks, API calls
- [ ] **Projects:** counter · todo · API app · multi-step form · rebuild the ticket app
- [ ] Compare each major feature to the vanilla and HTMX versions

### Phase 9 — Production React
Detail in the React roadmap. Do not collect libraries for their own sake.
- [ ] Routing (React Router docs; v9 course uses TanStack Router)
- [ ] Server state: TanStack Query
- [ ] Client state: Zustand **or** Redux Toolkit
- [ ] Forms: React Hook Form (official docs)
- [ ] Testing: **Testing Fundamentals** (Steve Kinney)
- [ ] A11y: **Website Accessibility, v3** (Jon Kuperman) and/or **Web App Accessibility (feat. React)** (Marcy Sutton Todd)
- [ ] Deploy a ticket-app frontend

### Phase 10 — Next.js (optional)
Course: **Next.js Fundamentals, v4** (Scott Moss)
- [ ] SSR / SSG / server vs client
- [ ] When a React SPA is enough vs when Next.js helps

---

## One project, five skins

Same ticket/task domain the whole way. See [projects/ticket-app/README.md](projects/ticket-app/README.md).

| Stage | Stack |
|---|---|
| 1 | HTML/CSS static UI |
| 2 | Vanilla JS |
| 3 | Vanilla JS + Spring Boot JSON API |
| 4 | HTMX + Spring Boot HTML fragments |
| 5 | React + TypeScript |

---

## Notes log

One line per session is enough. Longer entries go in [notes/journal.md](notes/journal.md).

```
2026-08-15: Restructured repo into a web-frontend path. React is now Phase 8+.
```
