# Phase 0: Web Mental Model

You're not starting from zero. You're porting UIKit/iOS intuition onto the web. Read this once, then stop translating in your head.

You know **imperative UI**: you own the views and you update them when data changes. Vanilla JS is that same job in the browser. React (declarative, closer to SwiftUI) is a later tool. This phase is the platform it sits on. You do not need SwiftUI.

---

## What happens when a browser loads a page

```
Type URL / click link
        ↓
DNS → TCP → TLS
        ↓
HTTP request  (GET /tickets)
        ↓
Server response  (HTML, or JSON, or an HTML fragment)
        ↓
Browser parses HTML → builds the DOM
        ↓
Loads CSS → CSSOM → layout → paint
        ↓
Loads JavaScript → can change the DOM after that
```

Everything later is a variation of this loop.

| Piece | Job |
|---|---|
| **HTML** | Structure and meaning |
| **CSS** | Layout and appearance |
| **JavaScript** | Behavior after the page exists |
| **DOM** | Live tree the browser renders; JS reads and writes it |
| **HTTP** | How the browser talks to a server |
| **JSON** | Common payload for APIs |
| **REST API** | HTTP + resources (`GET /tickets`, `POST /tickets`) |

Rendering, at this level: parse HTML → compute styles → layout boxes → paint pixels. You do not need the full browser-engine deep dive yet.

---

## Frontend vs backend

```
Browser                          Server
───────                          ──────
HTML / CSS / JS                  Spring Boot
DOM, events, fetch               REST controllers
What the user sees               Data, rules, persistence
        \                        /
         \______ HTTP _________/
```

You already write the right-hand side. This repo is mostly the left-hand side, plus the HTTP contract between them.

---

## Where the later tools sit

**Spring Boot** — backend. Exposes JSON (and later, small HTML fragments). Not a UI framework. **No Thymeleaf.**

**Vanilla JS** — you request JSON, then you update the DOM. You feel the state/DOM problem directly.

**HTMX** — the server returns HTML fragments; HTMX swaps them into the page. Less client JS. State leans toward the server.

**React** — you describe UI from state; React updates the DOM. Worth it once client state and UI sync become the bottleneck.

**SPA / CSR** — one page load, then JS fetches data and redraws views (vanilla SPA or React SPA).

**SSR** — server sends HTML first (Next.js later; HTMX is a lighter cousin of “server sends HTML”).

Do not pick a winner here. You will build the same ticket app three ways and compare.

---

## UIKit → web

| UIKit / iOS | Web | Notes |
|---|---|---|
| Xcode + Swift compiler | Browser + JS engine (V8 etc.) | JS is interpreted/JIT, not AOT like Swift |
| **`UIView` hierarchy** | **DOM tree** | Live objects you query and mutate |
| `UIViewController` | A screen / page module | Owns a chunk of UI + its events |
| Storyboard / xib / programmatic UI | HTML (+ later, JS that builds nodes) | Structure vs code that builds structure |
| Auto Layout / stack views | CSS Flexbox + Grid | Same job, zero shared syntax |
| `addTarget` / `IBAction` | `addEventListener` | You wire the control yourself |
| Delegation (`UITableViewDataSource`) | Callbacks, or one parent listener (event delegation) | Same idea: object A asks object B |
| `UITableView` / `UICollectionView` | Render a list into the DOM | You still produce the rows |
| `UINavigationController` | Links, or History API (`pushState`) | Stack vs URL |
| `URLSession` | `fetch` | HTTP client |
| `UserDefaults` | `localStorage` | Key-value only |
| `NotificationCenter` | `CustomEvent` / a tiny pub-sub | Optional; easy to overuse |
| SPM / CocoaPods | npm / pnpm | Dependencies |
| `.xcodeproj` | `package.json` + Vite later | Manifest + bundler |
| Simulator | Browser + DevTools | Debugger + inspector |
| Instruments | DevTools Performance | |

Vanilla JS will feel like UIKit: change the model, then poke the view.

```swift
// UIKit — you update the label
count += 1
countLabel.text = "Count: \(count)"
```

```js
// Vanilla JS — same move
count += 1;
countEl.textContent = `Count: ${count}`;
```

React (Phase 8) is the *other* model — describe the UI from state, let the library patch the DOM. That is closer to SwiftUI. You have not needed that skill in UIKit, and you will not start there.

```tsx
// React — later. You do not write the DOM update.
const [count, setCount] = useState(0);
return <p>Count: {count}</p>;
```

Until then: change data, then change DOM nodes. You already know that loop.

---

## Real differences (pay attention)

### 1. No compiler safety net (until TypeScript)
Swift catches type errors at compile time. Raw JS returns `undefined` for a typo. TypeScript (Phase 3) restores a net — but it is erased at runtime. `string | undefined` does not check the network response for you.

### 2. `this` is not `self`
`this` depends on *how* a function is called. Arrow functions inherit `this` from surrounding scope. Hit this in Phase 2. Do not skim it.

### 3. Single-threaded + event loop
No GCD, no actors. One thread. Network and timers go through the event loop (`Promises` vs `setTimeout`). `async`/`await` looks like Swift’s but has no structured concurrency underneath.

### 4. The DOM and CSS are the new substrate
The DOM is your `UIView` tree. CSS layout (flexbox/grid) has the same *job* as Auto Layout / stack views and none of the syntax. Budget real time here — this is the new fundamental, not React.

### 5. Data fetching has no built-in repository
`fetch` is raw `URLSession`. Loading, errors, retries, and cache are yours until something like TanStack Query (Phase 9).

---

## One-sentence summary

**UIKit already taught you imperative UI. Vanilla JS is that same habit in the browser. Learn HTTP, HTML, CSS, the DOM, and a Spring Boot JSON API first. HTMX and React are two later answers to “who updates the page.”**
