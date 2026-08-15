# Learning Strategy

## Core principle

Do not optimize for remembering syntax.
Optimize for building, then for knowing *what exists* and *where to look it up*.

---

## Cycle

```
Watch → Build → Break → Recall → Rebuild
```

Never binge-watch. Start coding within 10 minutes of a lesson.

After a lesson, close the video:

> Can I explain this to another Swift/Java developer?

If not, rewatch only that lesson.

---

## Time

- **70%** building
- **20%** courses
- **10%** docs / notes

Notes are for you in two weeks, not a textbook.

---

## While watching Frontend Masters

1. Watch the lesson through.
2. Build the idea in the ticket app (or a 20-line scratch file).
3. Break it: wrong URL, empty list, slow network, duplicate submit.
4. Rebuild once from memory.

Course versions change — confirm the current title on FEM before a phase.

---

## Notes — one page, not lecture transcripts

### Mental model

```md
## Event delegation

Mental model
- One listener on a parent; events bubble

Vanilla
- listEl.addEventListener("click", handler)

HTMX
- usually none; hx-delete on the row

React (later)
- onClick on the row or a child; React delegates internally
```

### Three living files

**[notes/gotchas.md](notes/gotchas.md)** — only what repeatedly trips you up.

**[notes/cheatsheet.md](notes/cheatsheet.md)** — syntax, no prose.

**[notes/comparisons.md](notes/comparisons.md)** — same feature, three ways, only when the contrast teaches something.

```md
## Modal

Vanilla JS
- Create/show a dialog; trap focus yourself; wire close + submit

HTMX
- Swap a fragment into a dialog slot; server returns the form HTML

React
- Modal is UI state (`open`). Conditional render. Focus in an effect.
```

**[notes/journal.md](notes/journal.md)** — a few lines per day.

UIKit mappings belong in gotchas or comparisons (`addTarget` → `addEventListener`). No separate essay.

---

## After every phase

Build or refactor **without** a tutorial open.

| After | Without a tutorial |
|---|---|
| HTML/CSS | Static ticket shell |
| JavaScript | Ticket CRUD in the DOM |
| TypeScript | Typed ticket + API module |
| Architecture | Modules + URL state |
| Spring API | UI talks to real JSON |
| HTMX | List + form as fragments |
| React | Same screens in React |

---

## Weekly review

- Can I explain it without notes?
- Can I build it from docs only?
- What did I Google more than twice? → `gotchas.md`
- What still feels like magic?

---

## Final rule

```
Learn → Build → Forget → Rebuild
```

Rebuilding is the point.
