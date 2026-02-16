# Full-Stack Challenge

## Workflow Status Playground

### Timebox

45-60 minutes

### AI Usage

Allowed. You should understand and be able to explain everything you submit.

## Objective

Build a small web application that demonstrates a simple workflow state system and a UI to interact with it.

The goal is not visual polish. We want to understand how you model logic, structure code, and connect behavior to a user interface.

## Scenario

Each item has a `status`.

Allowed statuses:

- `todo`
- `in_progress`
- `done`

Allowed transitions:

- `todo -> in_progress`
- `in_progress -> todo`
- `in_progress -> done`

Rules:

- Self-transitions are not allowed.
- Any transition not listed above should be rejected.
- Any status value outside `todo | in_progress | done` should be rejected.

## What We'd Like to See

- Workflow transition logic implemented in code
- Minimal interface to attempt transitions
- Clear feedback for valid and invalid updates
- Structure that would make sense in a real application

You can choose your language, framework (or none), error-handling style, and file structure.

## Submission

1. Fork this repository.
2. Create a branch:

   `solution/<firstname-lastname>`

3. Place your work in:

   `solutions/<firstname-lastname>/`

4. Open a Pull Request to `main`.

Include a short `README.md` that explains:

- Your approach
- Key tradeoffs
- How to run your solution
- What you'd improve with more time

## Optional Validation Artifact

This challenge does not require tests in the prompt.

If useful, you may use `test_cases.json` in this folder as optional sample transition cases to validate your implementation in any language.

Suggested optional error codes used in that artifact:

- `INVALID_STATUS`
- `SELF_TRANSITION`
- `INVALID_TRANSITION`

## Optional Stretch Ideas

- Add a new status such as `blocked` or `cancelled`
- Make transition rules configurable
- Show transition history
- Improve UX clarity and flow
