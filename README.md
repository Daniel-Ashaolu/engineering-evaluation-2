# Workflow Status Playground

A single-file web app demonstrating a workflow state machine with a UI to attempt transitions, receive feedback, and test edge cases.

## Approach

**State machine first.** The core logic lives in two pure data structures and one pure function:

```js
const VALID_STATUSES = new Set(['todo', 'in_progress', 'done']);

const ALLOWED_TRANSITIONS = {
  todo: ['in_progress'],
  in_progress: ['todo', 'done'],
  done: [],
};

function transition(currentStatus, targetStatus) {
  // returns { ok: true, from, to }
  //      or { ok: false, error, code }
}
```

`transition()` has no side effects — it just validates and returns a result. The UI layer calls it and decides what to do next. This makes the logic easy to test in isolation.

**Error codes** match the optional spec: `INVALID_STATUS`, `SELF_TRANSITION`, `INVALID_TRANSITION`.

**UI layout** is three panels:
- **Items** — list of work items, each with an id, name, and current status badge
- **Transition** — selected item detail + quick-select buttons for valid targets + a raw text input for intentionally testing invalid values
- **Event Log** — timestamped history of every attempted transition with outcome codes

The raw input box is the key UX decision for this challenge: it lets you type anything (`DONE`, `cancelled`, `in_progress`) to intentionally trigger validation errors, which makes the system's rules observable.

## How to Run

No build step. Open the file directly:

```bash
open workflow-playground/index.html
# or
python3 -m http.server 8080 --directory workflow-playground
```

Then visit `http://localhost:8080`.

## Key Tradeoffs

| Decision | Tradeoff |
|---|---|
| Single HTML file | Zero setup, easy to share — not how you'd ship a real app |
| Transition map as plain object | Dead simple to read/extend, but not enforced by types |
| UI renders from scratch on every state change | Simple mental model, would not scale to large item lists |
| No persistence | State resets on reload — acceptable for a playground |

## What I'd Improve With More Time

**Code structure**
- Move state machine into its own module (`workflow.js`) with exported types
- Separate UI rendering into components
- Add TypeScript for status/transition types

**Features**
- Persist items to `localStorage`
- Transition history per item (not just global log)
- Configurable transition rules (editable in the UI)
- `blocked` and `cancelled` statuses with their own valid paths
- Bulk transitions
- Keyboard shortcuts

**Testing**
- Unit tests for `transition()` against `test_cases.json`
- E2E tests for UI interactions

**Production concerns**
- REST API backing the state machine (e.g. `PATCH /items/:id/status`)
- Optimistic UI updates with rollback on server error
- Audit log stored server-side
