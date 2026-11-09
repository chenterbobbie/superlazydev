# Project system map

Create a map that helps someone understand the specific behavior under investigation. Do not inventory the entire repository when a smaller path explains the issue.

## Inspect

1. Read repository and directory-level instructions.
2. Find the relevant entry point: route, command, screen, job, event handler, or public function.
3. Follow control flow and the data or state involved in the report.
4. Identify storage and external boundaries, configuration that changes this path, error handling, and related tests.
5. Verify each path and relationship in source; label unresolved inferences.

## Present

Use a short flow such as:

```text
Entry point → validation/state → domain logic → storage or external call → result/error handling
```

Name the important files beside each step. Explain only relationships that matter to the reported behavior, and point out where a failure can enter or be transformed. Keep the map factual and useful for the next debugging step.
