# Phase 0: Mental Model — Swift/iOS → Web/JS/React

You're not starting from zero. You're porting 6 years of intuition to a new platform. This doc exists so you stop translating in your head after week one.

---

## The Big Picture Mapping

| iOS/Swift World | Web World | Notes |
|---|---|---|
| Xcode + Swift compiler | Browser + JS engine (V8 etc.) | JS is interpreted/JIT-compiled, not ahead-of-time compiled like Swift |
| UIKit (imperative) | Raw DOM + vanilla JS (imperative) | You'll learn this briefly, then mostly leave it behind |
| **SwiftUI (declarative)** | **React (declarative)** | This is your real anchor point — same paradigm shift Apple made you go through already |
| `.swift` files | `.js` / `.jsx` / `.ts` / `.tsx` files | `.tsx` = TypeScript + JSX, what you'll write most |
| Storyboards/xib or SwiftUI View hierarchy | JSX / component tree | Both describe "what the UI looks like," not "how to build it step by step" |
| Swift Package Manager / CocoaPods | npm / yarn / pnpm | Same job: dependency management |
| `.xcodeproj` / `.xcworkspace` | `package.json` + bundler config (Vite) | package.json is your project's "manifest" |
| SQLite (local relational storage) | No direct equivalent for typical apps — data lives on a server, fetched via API | If you ever need local storage: `localStorage` (like `UserDefaults`, key-value only) or IndexedDB (closer to SQLite, relational-ish, async API) |
| Simulator | Browser (Chrome/Safari) + DevTools | DevTools ≈ Xcode's debugger + view hierarchy inspector combined |
| Instruments | Chrome DevTools Performance tab / React DevTools Profiler | |

---

## The Core Paradigm You Already Know

SwiftUI taught you this already, so don't relearn it — just relabel it:

```
State changes → View re-computes/re-renders → UI updates
```

React is the exact same idea:

```swift
// SwiftUI
struct CounterView: View {
    @State private var count = 0
    var body: some View {
        VStack {
            Text("Count: \(count)")
            Button("Increment") { count += 1 }
        }
    }
}
```

```tsx
// React (TypeScript)
function CounterView() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

Map it directly:
- `@State` ↔ `useState`
- `body` (computed property) ↔ the function's return statement (JSX)
- View struct ↔ Component function
- `@Binding` ↔ passing `value` + `onChange` as props (no built-in two-way binding sugar in React)
- `@EnvironmentObject` / `@ObservedObject` ↔ Context API, or a state library (Zustand/Redux)
- View modifiers chained (`.padding().background()`) ↔ CSS classes / inline styles / Tailwind utility classes

---

## Where the Real Differences Are (pay attention here)

### 1. No compiler safety net (until TypeScript)
Swift catches type errors at compile time. Raw JS catches nothing until runtime — a typo in a property name just silently returns `undefined` instead of refusing to build. This is *exactly* why you're learning TypeScript early: it restores the safety net you're used to.

### 2. `this` is not `self`
In Swift, `self` is explicit and predictable. In JS, `this` depends on *how a function is called*, not where it's defined — a genuine footgun. Arrow functions (`() => {}`) fix this by inheriting `this` from their surrounding scope, which is why modern JS/React code uses arrow functions almost everywhere. You'll hit this directly in Phase 2 — don't skim it.

### 3. Single-threaded + event loop, not GCD/actors
No dispatch queues, no `DispatchQueue.main.async`, no actors. JS runs on one thread with an event loop; async operations (network calls, timers) get queued and processed via the **microtask queue** (Promises) and **callback queue** (setTimeout etc.). `async`/`await` in JS looks like Swift's, but there's no structured concurrency, no `Task {}`, no actor isolation underneath it — it's simpler but less safe by design.

### 4. The DOM and CSS are genuinely new territory
There's no UIKit/SwiftUI equivalent to "the DOM" as a concept — it's a live tree of nodes the browser renders, and React's whole job is managing it efficiently for you (via the virtual DOM diffing). CSS layout (flexbox/grid) is conceptually similar to Auto Layout/stack views in *purpose* (arranging views) but has completely different rules and no transferable syntax. Budget real time here — this is your true "new fundamentals," not JS itself.

### 5. Data fetching has no built-in "repository pattern"
You're used to structuring apps with clear data layers (maybe Core Data/SQLite + a repository/service layer). In basic React, `fetch`/`useEffect` is the "raw" way; in production you'll use TanStack Query, which gives you caching, retries, and loading states — closer to what you'd hand-roll yourself with SQLite + a sync layer today.

---

## One-Sentence Summary to Keep in Mind

**You already know the "declarative UI + state-driven re-render" game from SwiftUI — your actual learning curve is JS-the-language (especially `this` and async), the DOM/CSS as a new UI substrate, and the web's dependency/tooling ecosystem. Everything else is vocabulary, not new concepts.**
