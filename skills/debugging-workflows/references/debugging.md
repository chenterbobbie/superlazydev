# Debugging checklist

Use this checklist to investigate a reported bug without guessing at its cause.

## Establish the failure

- Capture the exact observed and expected behavior.
- Record the smallest reproduction: steps, input, environment, and relevant output.
- Separate confirmed evidence from possible explanations.
- If the issue is intermittent or cannot be reproduced, identify what evidence is missing and continue tracing from available logs, state, or code paths.

## Trace and isolate

- Find the entry point and follow the failing value or event through its callers and shared helpers.
- Check related configuration, persistence, external services, and error handling where they affect this path.
- Search for all callers of any shared function being changed.
- Narrow the cause to the earliest incorrect assumption, state transition, or boundary.
- Consider nearby valid, invalid, empty, duplicate, and failure cases that could be affected.

## Fix and verify

- Fix the responsible layer with the smallest behavior-preserving change.
- Add a focused regression test using the repository's existing test conventions when feasible.
- Run the narrowest relevant check first, then broader checks justified by the change.
- Review the final diff and state any reproduction or validation gaps plainly.
