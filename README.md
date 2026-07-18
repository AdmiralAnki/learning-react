# React Learning — Progress Tracker

Single source of truth for docs + progress. No decentralized copies — this repo is the only place anything lives.

## Setup (one-time)

1. Create a **private** repo on GitHub, e.g. `learning-react`.
2. Locally:
   ```bash
   git clone git@github.com:<you>/learning-react.git
   cd learning-react
   ```
3. Drop these files into the repo root:
   - `phase-0-mental-model.md`
   - `react-learning-roadmap-v3-fem.md` (current plan — Frontend Masters edition)
   - `README.md` (this file — acts as your dashboard)
4. Create folders as you go:
   ```
   /notes/          → your own written notes per phase (phase-1-notes.md, phase-2-notes.md, ...)
   /projects/        → actual project code, one subfolder per project
   ```
5. Commit and push:
   ```bash
   git add .
   git commit -m "Initial roadmap setup"
   git push
   ```

## On any second machine (home/work)

```bash
git clone git@github.com:<you>/learning-react.git   # first time only
git pull                                             # every session, before you start
# ... do work, edit checkboxes below, add notes/code ...
git add .
git commit -m "Phase 2 day 3: closures + this binding"
git push                                             # every session, before you close laptop
```

**Rule: always `pull` before starting, always `push` before stopping.** Since you're the only one editing, there's no real merge-conflict risk as long as you follow this — no need for branches unless you want them.

## Progress Checklist

Check items off directly in this file (`- [x]`), commit, push. GitHub renders checkboxes natively so you can see progress at a glance in the browser too, from any device.

### Phase 0 — Mental Model
- [ ] Read phase-0-mental-model.md fully

### Phase 1 — HTML/CSS (Week 1)
- [ ] FEM: Getting Started with CSS, v2 (Jen Kramer)
- [ ] FEM: CSS Grid & Flexbox course (Jen Kramer)
- [ ] Semantic HTML + forms
- [ ] CSS box model, cascade, specificity
- [ ] Flexbox (Flexbox Froggy completed)
- [ ] Grid (CSS Grid Garden completed)
- [ ] Responsive design / media queries
- [ ] **Project:** static portfolio page

### Phase 2 — JS Differences (Week 2)
- [ ] FEM: Deep JavaScript Foundations, v3 (Kyle Simpson)
- [ ] Syntax quirks (destructuring, spread/rest, template literals)
- [ ] Closures confirmed
- [ ] `this` binding understood
- [ ] Array/object functional methods
- [ ] Promises / async-await / event loop
- [ ] Modules (import/export)
- [ ] **Project:** vanilla JS to-do app

### Phase 3 — TypeScript (Week 3)
- [ ] FEM: TypeScript 5+ Fundamentals, v4 (Mike North)
- [ ] Basic types, interfaces, type aliases
- [ ] Function typing
- [ ] Generics
- [ ] Union types
- [ ] Optional properties + runtime nil-safety gotcha understood
- [ ] **Project:** port to-do app to TS

### Phase 4 — Tooling
- [ ] Node/npm/pnpm basics
- [ ] Vite project scaffolded
- [ ] React DevTools installed

### Phase 5 — React + TS Fundamentals (Week 4–5)
- [ ] FEM: Complete Intro to React, v9 (Brian Holt)
- [ ] FEM: Intermediate React, v6 (Brian Holt)
- [ ] JSX/tsx basics
- [ ] Components + typed props
- [ ] useState
- [ ] Events (typed)
- [ ] Conditional rendering + lists/keys
- [ ] useEffect
- [ ] Forms (controlled, typed)
- [ ] Lifting state up
- [ ] Context API
- [ ] Custom hooks
- [ ] **Project:** counter app
- [ ] **Project:** to-do app v3 (React+TS)
- [ ] **Project:** API-driven app
- [ ] **Project:** multi-step form

### Phase 6 — Production Ecosystem (Week 6–7)
- [ ] FEM: state management course (check current catalog title)
- [ ] FEM: performance course (React 19 features)
- [ ] React Router
- [ ] Zustand (or Redux Toolkit)
- [ ] TanStack Query
- [ ] Tailwind / CSS Modules
- [ ] Vitest + React Testing Library
- [ ] React Hook Form
- [ ] Deploy to Vercel/Netlify
- [ ] JWT storage tradeoffs understood
- [ ] **Capstone:** microservices project frontend

### Phase 7 — Next Steps
- [ ] Next.js basics
- [ ] Performance (memo/useMemo/useCallback)
- [ ] Accessibility pass
- [ ] Component library integrated

## Notes Log

Add a dated entry each session — even one line. Useful for momentum and for picking back up after a gap.

```
2026-07-18: Set up repo, read Phase 0 doc.
```
