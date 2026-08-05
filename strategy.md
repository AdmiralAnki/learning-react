# React Learning Strategy

## Core Principle

Don't optimize for **remembering** React.
Optimize for **building** React applications.

The goal is to know *what exists* and *where to find it*, not to memorize syntax.

---

# Learning Cycle

For every topic:

```text
Watch
   ↓
Build
   ↓
Break
   ↓
Recall
```

Never binge-watch tutorials.

---

# While Watching Courses

### ✅ Watch an entire lesson first
Don't pause every minute to take notes.

### ✅ After the lesson
Close the video and ask:

> "Can I explain this to another Swift developer?"

If not, rewatch only that lesson.

### ✅ Build immediately
Start coding within 10 minutes of finishing the lesson.

---

# Notes Strategy

## Don't write lecture notes.

Instead, create **one-page summaries**.

Example:

```md
## useState

Mental Model
- Component-local state

Swift Equivalent
- @State

Gotchas
- Don't mutate directly
- Updates are asynchronous

Useful APIs
- useState()
```

---

# Keep Three Markdown Files

## 1. `gotchas.md`

Only things that repeatedly trip you up.

Example:

```md
## JavaScript

- == vs ===
- undefined vs null
- this binding
- Objects are references

## React

- Hooks only at top level
- Don't mutate state
- useEffect dependency array
- Keys matter
```

---

## 2. `swift-vs-react.md`

Map concepts between Swift and React.

| Swift | React |
|--------|--------|
| @State | useState |
| ObservableObject | Context / State Libraries |
| Struct value types | JS objects are references |
| ARC | Garbage Collection |

---

## 3. `cheatsheet.md`

Quick syntax reference only.

Example:

```css
display: flex;
justify-content:
align-items:
flex-direction:
gap:
```

No explanations.

---

# Active Recall

After every major lesson:

1. Close the course.
2. Open VS Code.
3. Rebuild from memory.
4. Google only when blocked.

---

# Weekly Time Allocation

- **70%** Building
- **20%** Watching courses
- **10%** Reading documentation

---

# After Every Phase

Build one small project **without following a tutorial**.

Examples:

- HTML/CSS → Portfolio
- JavaScript → Todo App
- TypeScript → Typed Todo
- React → Movie App

---

# Learning Journal

At the end of each day:

```md
## YYYY-MM-DD

Completed
- CSS Grid

Understood
- Grid template
- Auto-fit

Need Practice
- Grid areas

Tomorrow
- Flexbox
```

---

# Weekly Review

Ask yourself:

- Can I explain it without notes?
- Can I build something using only docs?
- What did I Google repeatedly?
- What still feels like magic?

Add repeated mistakes to `gotchas.md`.

---

# Final Rule

Your roadmap should follow this rhythm:

```text
Learn
    ↓
Build
    ↓
Forget
    ↓
Rebuild
```

Rebuilding—not rereading—is where long-term learning happens.
