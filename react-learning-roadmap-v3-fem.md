# React Learning Roadmap v3 — Frontend Masters Edition

Same phase structure and timeline as v2 (6–8 weeks, compressed for 6 years Swift/iOS experience), now mapped to specific Frontend Masters courses. Course names/versions shift over time — always search FEM's site for the current version number before starting a phase, in case a newer version has replaced the one listed here.

---

## Phase 0: Mental Model (½ day)
No course — read `phase-0-mental-model.md` first.

---

## Phase 1: HTML & CSS Foundations (Week 1)

**Primary course:**
- **"Getting Started with CSS, v2" — Jen Kramer** (semantic HTML, selectors, specificity, box model, project-based — builds an actual portfolio site)

**Follow with:**
- **CSS layout course covering Grid & Flexbox — Jen Kramer** (search FEM catalog for her current Grid/Flexbox-focused course; titles get versioned)

Skip any HTML/CSS course sections aimed at absolute beginners to computers/the internet — jump straight to the CSS mechanics.

### Project
Same as before: static responsive portfolio page, no JS. (You'll likely build exactly this as part of the Jen Kramer course anyway.)

---

## Phase 2: JavaScript — The Differences Only (Week 2)

**Primary course:**
- **"Deep JavaScript Foundations, v3" — Kyle Simpson**

This is a better fit for you than a beginner JS course — it's specifically deep-dives on closures, `this`, prototypes, and async, which is exactly the "differences from Swift" list from your plan. Skip/skim any segments on basic syntax (variables, loops, functions) you already recognize from other languages; focus hard on:
- Closures module
- `this` binding module
- Async/Promises module
- Prototypes module (lighter attention — mostly historical context for modern React work)

**If Deep JS Foundations feels too advanced to start cold:** fall back to the JS portion of **"Complete Intro to Web Development, v3" — Brian Holt** first for a gentler on-ramp, then do Deep JS Foundations for the depth.

### Project
Vanilla JS + DOM to-do app, `localStorage` persistence — same as v2. Neither course above requires this project format, so treat it as your own supplementary reps.

---

## Phase 3: TypeScript (Week 3)

**Primary course:**
- **"TypeScript 5+ Fundamentals, v4" — Mike North**

Covers types, interfaces, generics, narrowing, utility types, with React/Node examples baked in — a good fit since you're heading straight into typed React next. Given your Swift background, the sections on generics and interfaces will move fast for you; slow down on:
- The "optional properties / type erasure at runtime" material — this is the part that can mislead your Swift-optional instincts (see the gotcha in your Phase 0 doc)

### Project
Port your Phase 2 vanilla JS to-do app to TypeScript.

---

## Phase 4: Tooling (2–3 days, overlap with Phase 3)

No dedicated FEM course needed — Vite/Node setup is covered inline in most of the React courses below. Just get comfortable with:
- `npm`/`pnpm`, `package.json`
- Vite scaffolding a TS + React project
- React DevTools browser extension

---

## Phase 5: React Fundamentals with TypeScript (Week 4–5)

**Primary course:**
- **"Complete Intro to React, v9" — Brian Holt**

This is currently rated as one of FEM's strongest React fundamentals courses — clean, modern patterns (hooks-first, no legacy class-component detours). Covers components, props, `useState`, events, conditional rendering/lists, `useEffect`, forms, context. Do the exercises in TypeScript even if the course default is JS — you already know TS from Phase 3, so translate as you go; this cements both at once.

**Follow immediately with:**
- **"Intermediate React, v6" — Brian Holt**

Picks up right where Complete Intro leaves off: `useReducer`, performance patterns, more advanced hooks, component/testing patterns. This is explicitly positioned as the next step after Complete Intro to React, so the two are designed to be taken back to back.

### Projects
Same four as v2 — counter, to-do v3 (React+TS), API-driven app, multi-step form — built alongside or immediately after these two courses, in TypeScript.

---

## Phase 6: Production Ecosystem (Week 6–7)

**Primary courses (pick based on what's most relevant to your capstone):**
- **A state management course covering Redux + ecosystem tooling** (search FEM catalog — there's a current course specifically on managing state at scale, framed around team/app-growth challenges, which matches your "production app for work" goal well)
- **A React performance course covering React 19 features** — hydration, suspense, resource loading, server actions (relevant once you're shipping real apps, less urgent for a first pass)

**Not always a full standalone FEM course — supplement with official docs/smaller resources:**
- React Router — check FEM catalog for current routing-specific course; if none current, use the official React Router docs
- TanStack Query — check FEM catalog; if no current course, use official TanStack Query docs (excellent on their own)
- Testing (Vitest + React Testing Library) — FEM has testing-focused courses; search catalog for current version
- Tailwind CSS — FEM has Tailwind-specific courses; search catalog

### Given your backend context
No FEM course will map directly to Keycloak/JWT specifics — that integration work is genuinely your own project territory, using official docs for whichever auth flow you pick.

### Capstone Project
Same as v2: React+TS frontend for your in-progress microservices project.

---

## Phase 7: Next Steps (ongoing)

- **Next.js course — search FEM's "React & Next.js" learning path** for the current recommended Next.js course; FEM organizes this as part of a structured path, worth following once core React is solid
- Performance deep-dive (memoization, code splitting) — same performance course flagged in Phase 6, or a dedicated one if it exists by then
- Accessibility — FEM has standalone a11y courses; add if your capstone needs it

---

## Practical Notes on Using FEM

- **Subscription:** individual plans run ~$39/month or ~$390/year — worth it only if you're consistently using it; the annual plan pays off past ~10 months of use
- **Always verify current version numbers** before starting a phase — courses get re-recorded (v3 → v4 → v9, etc.) and older versions can vanish from the catalog or use outdated patterns
- **FEM's own "React & Next.js Learning Path" and "TypeScript" learning path** bundle these courses in FEM's own recommended order — worth cross-checking against this doc once you're actually browsing the site, since their internal sequencing may shift as courses update
- Track which specific course + version you actually took in your progress tracker (see updated README below) — useful if you revisit material or a course gets superseded

---

## Revised Weekly Rhythm (unchanged from v2)

| Week | Focus | Primary FEM Course(s) |
|---|---|---|
| 0 (½ day) | Mental model | — (your own doc) |
| 1 | HTML/CSS | Getting Started with CSS, v2 + Grid/Flexbox course |
| 2 | JS differences | Deep JavaScript Foundations, v3 |
| 3 | TypeScript | TypeScript 5+ Fundamentals, v4 |
| 3 (overlap) | Tooling | — (folded into React courses) |
| 4–5 | React + TS | Complete Intro to React, v9 → Intermediate React, v6 |
| 6–7 | Production ecosystem | State management course, testing course, performance course |
| 8+ | Next.js, capstone | Next.js course (per FEM's React & Next.js path) |
