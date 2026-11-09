---
name: debugging-workflows
description: Find and fix bugs in an existing software project. Use to investigate unexpected behavior, map unfamiliar code, explain a fix, and hand off concise findings or durable project knowledge.
---

# Debugging Workflows

Work from evidence in the user's repository. Preserve unrelated changes, follow project instructions and conventions, and keep the fix as small as possible. Do not claim a bug is fixed unless the available evidence supports it.

## Workflows

Choose the workflow that matches the request. A bug-fix task normally starts with debugging; use the other workflows when they help explain, orient, or hand off that work. Follow the linked reference when using a workflow.

### 1. Debugging

1. Read applicable `AGENTS.md` files and inspect the working tree before editing.
2. Reproduce the report when possible. Record the observed behavior, expected behavior, and the smallest useful failure evidence (error, logs, input, or steps).
3. Trace the affected path through its callers, shared helpers, configuration, and tests. Find the root cause rather than patching a symptom.
4. Make the smallest change that fixes the cause. Preserve established behavior and validate inputs at trust boundaries.
5. Add or update a focused regression check when the project has an appropriate test pattern. Run relevant existing checks; if reproduction or validation is unavailable, state that clearly.
6. Review the diff and nearby behavior. Report the cause, fix, checks run, and remaining uncertainty.

See [debugging.md](references/debugging.md) for the investigation checklist.

### 2. Project system map

Build a compact map before debugging when the codebase or affected area is unfamiliar. Inspect the entry points, relevant modules, data flow, state or storage, external boundaries, configuration, and tests. Trace only paths connected to the reported behavior. Present the map with file paths and a short explanation of how control and data move; distinguish verified structure from assumptions. Do not edit code just to produce the map.

See [project-system-map.md](references/project-system-map.md) for the map structure.

### 3. Code explainer page

Explain the relevant code in a reader-friendly page when requested. Start with the behavior and the bug's cause, then follow the execution path, important state/data changes, and the fix. Link to real repository paths and symbols, define project-specific terms, and keep the explanation scoped to the touched area. Save a page or document only when the user asks for one and the destination is clear; otherwise provide the explanation in the response.

See [code-explainer-page.md](references/code-explainer-page.md) for a page outline and review checklist.

### 4. Handoff

Prepare a concise handoff for another developer or a later session. Include the symptom, reproduction evidence, root cause, changed paths, validation performed, unresolved questions, and the next concrete step if work remains. Separate confirmed facts from hypotheses. Do not imply that incomplete work is complete.

See [handoff.md](references/handoff.md) for a compact handoff format.

### 5. Second brain

Capture reusable project knowledge that will help future debugging: architecture landmarks, naming and test conventions, known failure modes, and verified commands. Keep it concise, dated when knowledge may go stale, and linked to source files. Do not store secrets, personal data, speculative conclusions, or duplicate existing documentation. Only write persistent notes when the user requests it or the repository already has an established place for them.

See [second-brain.md](references/second-brain.md) for what to capture and where.

## Boundaries

- Preserve user changes and avoid unrelated cleanup.
- Do not broaden a bug fix into a redesign or dependency change.
- Do not run destructive operations or modify production data as part of diagnosis.
- Never invent reproduction steps, test results, or repository facts.
- If the bug cannot be reproduced, make uncertainty explicit and use the available evidence to narrow the cause.

## Completion

Summarize the cause and change, name the important files, state validation and results, and note any material risk or unchecked path.
