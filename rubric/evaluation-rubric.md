# Evaluation Rubric (Internal)

Use this rubric to evaluate candidate submissions consistently for the Workflow Status Playground challenge.

## Scoring Scale

- **1**: Weak signal / major gaps
- **3**: Solid mid-level signal
- **5**: Strong signal for the target level

## 1) Clarity and Readability

- **1**: Code is hard to follow, unclear naming, intent not obvious.
- **3**: Mostly readable code with clear naming and understandable flow.
- **5**: Highly clear code with strong naming, concise organization, and low cognitive overhead.

## 2) Structure and Separation of Concerns

- **1**: Business logic, UI, and plumbing are tightly mixed.
- **3**: Logic and UI are reasonably separated with sensible module boundaries.
- **5**: Clean layering with clear boundaries that would scale in a production codebase.

## 3) Validation and Error Handling

- **1**: Invalid states/transitions are inconsistently handled or missing.
- **3**: Core invalid cases are handled with clear user-facing feedback.
- **5**: Validation is explicit, robust, and easy to extend with consistent error patterns.

## 4) Workflow Modeling Correctness

- **1**: Transition rules are incorrect or incomplete.
- **3**: Required statuses and transitions are implemented correctly.
- **5**: Correct and well-modeled engine that is easy to reason about and evolve.

## 5) Extensibility and Tradeoff Quality

- **1**: Design is rigid; adding a status or rule requires heavy rewrites.
- **3**: Reasonable structure; common extensions are feasible with moderate change.
- **5**: Thoughtful abstractions and clear tradeoffs for future evolution.

## 6) Communication (Solution README)

- **1**: Minimal or unclear explanation; decisions not justified.
- **3**: Clear summary of approach, tradeoffs, and run instructions.
- **5**: Crisp communication of decisions, constraints, and next-step improvements.

## 7) Engineering Maturity

- **1**: Fragile implementation and unclear operational behavior.
- **3**: Pragmatic choices with acceptable reliability for the timebox.
- **5**: Strong product engineering judgment, sensible defaults, and maintainable structure.

## Overall Recommendation Bands

- **Strong No**: Multiple categories at 1 with critical correctness or clarity gaps.
- **Mixed**: Mostly 3s, few 1s, no critical blockers; requires discussion in review.
- **Strong Yes**: Predominantly 4-5 quality outcomes (or strong 3s with clear upside and depth).
