---
name: fry-verify
description: Verify a coding change through its real entry point or delivered output. Use when asked to demonstrate a fix, check an acceptance criterion, or prevent a regression.
---

# Verify the delivered result

1. State the observable outcome the user expects. Pick a realistic input and a plausible wrong result the check must catch.
2. Exercise the normal entry point using the project's existing tools. Choose the smallest check that distinguishes the two outcomes. For an export, generate and reopen the final file. For a UI change, perform the interaction and inspect the resulting state. For a CLI, run the command and check the relevant output and exit status.
3. For a bug fix, run the same check before and after the change when practical. Use an isolated fixture or checkout if reproducing the old behavior could affect user data. Keep a focused regression test when the bug could recur.
4. If a recurring error can be prevented by a small API or type change, prefer that. Add a scoped lint rule only when it can reliably identify the unwanted pattern. Keep project-specific checks in the project.
5. Report the command or action, input, expected result, and observed result. Link evidence when it helps the user inspect the outcome. If a check could not run, name the blocker and the behavior still unverified.
