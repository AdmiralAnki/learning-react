# Phases 1–7 — Web platform before React

Dashboard and checkboxes: [README.md](README.md). React detail: [react-learning-roadmap-v3-fem.md](react-learning-roadmap-v3-fem.md).

Always confirm the current Frontend Masters version before starting. Do not invent extra courses.

---

## Phase 1 — HTML + CSS

Skip “what is a browser” intros. Spend time on mechanics and a real UI.

**FEM**

| Course | Use for |
|---|---|
| **Getting Started with CSS, v2** — Jen Kramer | Semantic HTML, selectors, box model, a first layout |
| **Intermediate HTML & CSS** — Jen Kramer | Cascade, specificity, inheritance, more HTML |
| **Ultimate CSS Grid & Layout Techniques, v3** — Jen Kramer | Flexbox, Grid, responsive layout |

Optional later (or Phase 9): **Website Accessibility, v3** — Jon Kuperman. Phase 1 only needs labels, headings, buttons, keyboard, and contrast.

**Also cover:** forms, native controls, media queries, composing a business UI (not a marketing page).

**Project — static ticket UI** (`projects/ticket-app/01-static/`)

Dashboard, ticket list, ticket details, create/edit form, modal, sidebar/nav. Responsive. No JavaScript.

---

## Phase 2 — JavaScript + a vanilla app

Two jobs: the language, then the browser.

**FEM**

| Course | Use for |
|---|---|
| **Deep JavaScript Foundations, v3** — Kyle Simpson | Types, scope, closures, `this`, prototypes (light), async |
| **Vanilla JS: You Might Not Need a Framework** — Maximiliano Firtman | DOM, events, `fetch`, modules, History API |

If Deep JS Foundations is too cold: **Getting Started with JavaScript, v3** (Web Dev Simplified), then Kyle. Alternate on-ramp already in this repo: **Complete Intro to Web Development, v3** — Brian Holt (JS portion).

Skip basic syntax you already know. Do not skip closures, `this`, or the event loop.

**Browser list you must actually use:** query/traverse/update DOM, events + delegation, forms + constraint validation, `fetch` + JSON, `async`/`await`, ES modules, `localStorage`, `history.pushState` / `popstate`.

**Project — vanilla ticket app** (`projects/ticket-app/02-vanilla/`)

No React. No HTMX. Mock JSON or `localStorage` is fine.

Must include: list, detail, create/edit, delete, search, filter, pagination or load-more, loading/error states, modal, toast, responsive UI.

The point is to feel state and DOM updates in your hands.

---

## Phase 3 — TypeScript

Keep this short. You want types on data and functions, not a type-system hobby.

**FEM:** **TypeScript 5+ Fundamentals, v4** — Mike North

Cover: basic types, interfaces, aliases, unions, narrowing, function types, generics, optional properties, inference.

Slow down on: optional properties and type erasure. A Swift `String?` is checked at runtime. A TS optional is not.

Skip Intermediate TypeScript until you have a real pain.

**Project:** type ticket records, form input, and the API module. Do not rewrite the whole UI layer unless it helps.

---

## Phase 4 — Architecture without a framework

Use the vanilla app. Do not start over. Do not build a virtual DOM.

**FEM:** **The Hard Parts of UI Development** — Will Sentance

Watch this for *why* state → view is hard. Stop when you understand data-binding and why full DOM replacement hurts. **Do not implement his VDOM as the ticket app.**

**Refactor toward:**

- App state vs UI state (modal open) vs server state vs derived state (filtered list)
- One place that owns data; render functions that read it
- Modules: `api`, `state`, `render`, `events` — not one 800-line file
- Event delegation instead of a listener per row
- URL as state (`/tickets/42?status=open`)
- Explicit loading / error / empty UI

When routing + list + form + modal all mutate the same DOM ad hoc, you have the lesson. That discomfort is the input to Phase 7 and Phase 8.

---

## Phase 5 — Spring Boot REST API

Lighter than the frontend phases. You already know Java.

**No FEM course.** Use Spring Web docs as needed.

Backend only needs:

- REST controllers + DTOs
- Validation
- JSON in/out
- Pagination, filter, sort
- Consistent error JSON
- CORS if the UI is on another origin
- Auth *concepts* (cookie vs bearer; do not boil the ocean)
- Same-origin: Spring serves static UI **or** you proxy the API

```
Browser (HTML/CSS/JS)
        ↓  JSON
Spring Boot REST
        ↓
Database
```

**No Thymeleaf. No server-rendered pages as the architecture.**

**Project:** `projects/ticket-app/03-api/` — same vanilla UI, real API. Keep mock mode if it helps you develop offline.

---

## Phase 6 — HTMX

Only after the JSON app works.

**Primary:** [https://htmx.org/docs](https://htmx.org/docs) and [https://htmx.org/examples](https://htmx.org/examples)

**Optional FEM:** **HTMX & Go** — ThePrimeagen. Use it for `hx-*` behavior. Skip Go and Go templates. Reimplement against Spring Boot.

HTMX wants HTML back, not JSON:

```
Browser --hx-get--> Spring Boot --HTML fragment--> HTMX swaps a node
```

vs vanilla:

```
Browser --fetch--> JSON --your JS--> DOM writes
```

**HTML fragments without Thymeleaf**

Keep JSON controllers. Add fragment endpoints that return `text/html`.

Practical options (pick one, stay boring):

1. HTML files under `src/main/resources/fragments/` plus small Java placeholder replacement
2. Java text blocks in a dedicated `TicketFragments` class

Do **not** add Thymeleaf. Do not turn the app into a Java template-engine project.

**Cover:** `hx-get/post/put/delete`, `hx-target`, `hx-swap`, `hx-trigger`, forms, `hx-indicator`, `hx-push-url`, search/filter/pagination, light polling if useful, progressive enhancement.

**Project:** `projects/ticket-app/04-htmx/` — rebuild list, search/filter, and the create/edit form (or modal). Leave a couple of screens vanilla so the contrast stays visible.

---

## Phase 7 — Why frameworks exist

No course. Fill [notes/comparisons.md](notes/comparisons.md).

Compare **vanilla JS**, **HTMX**, and **React** (preview from Phase 0 + docs is enough) on:

| Question | Write this down |
|---|---|
| What problem does it solve? | |
| Where does state live? | |
| Who updates the DOM? | |
| How does navigation work? | |
| What is a “component”? | |
| How much JS do you write? | |
| Where did complexity move? | |
| When does it get uncomfortable? | |

Do the same for one feature you built three times later — modal is the best first example.

You are ready for Phase 8 when React sounds like a tool for a problem you have already had.
