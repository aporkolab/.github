# An agent workflow you can copy

I use AI agents to do substantial implementation work. The useful part is the loop: a concrete brief, work that can be checked, a fresh review, and a human who can change the direction when the result misses the point.

This is a reusable recipe. Each project can use the parts it needs.

## 1. Give the task an observable finish line

Describe what someone should be able to do when the work is finished. Supply the files, examples, constraints, and existing behavior that matter. Separate a firm requirement from a suggestion.

For visual work, include an early screenshot or working slice in the acceptance checks. A passing test suite cannot tell you whether the design is the thing you asked for.

## 2. Split work at real boundaries

Parallel work helps when the pieces can be developed independently: an engine, its interface, documentation, or a review of an existing change. Give each worker a clear file scope and agree on the shared interface first.

One agent owns integration. If two tasks need to edit the same module, sequence them or change the split. More agents are not a reason to make the task larger.

## 3. Review the result with fresh context

Ask a separate reviewer to inspect the brief and the actual diff. Give them the acceptance checks and the relevant evidence, not a conclusion to endorse.

The reviewer should look for incorrect behavior, missed requirements, unsupported claims, and integration problems. Findings should name the problem, where it occurs, and how to reproduce or verify it. If there are no findings, record what was reviewed and what remains untested.

Independent review means a separate pass. It does not make an AI reviewer infallible or replace human judgment.

## 4. Check what changed

Run the project's relevant tests and checks. For a UI, try the main interaction in a browser, inspect a small screen, and check keyboard use. For documentation, follow the commands and verify the links or claims that changed.

Report actual results. Distinguish a command that passed from a check that was proposed, skipped, or blocked. Use existing coverage where it is sufficient; add a test when it protects behavior that matters.

## 5. Keep the human in charge of direction

A technically correct result can still answer the wrong question. Show a concrete result early enough to change it. The human decides whether it serves the purpose; the agents implement and verify that direction.

Merge and publication follow the repository's permissions and the agreed task scope. Do not turn an implementation request into an unrelated release or account change.

## Copyable task contract

```text
Goal
What should a user be able to do when this is finished?

Context
Relevant files, current behavior, examples, and decisions already made.

Scope
Files or components this task owns.
Boundaries shared with other work.

Requirements
Concrete behavior, compatibility, and design constraints.
Mark optional ideas as optional.

Acceptance checks
- Given [starting state], when [action], then [observable result].
- Relevant existing check: [command or procedure].
- Visual or manual check, if needed: [interaction and expected result].

Delivery
Changed files and a short explanation of the resulting behavior.
Checks performed, their results, and any remaining limitation.
Link the diff or provide a reviewable local result.

Review
Have a separate reviewer compare the result with this contract.
Resolve material findings before calling the task complete.

Authority
State the agreed scope for committing, merging, or publishing.
```

The contract is a starting point, not a form to fill out for every typo. Keep it proportional to the work.

For a concrete example of a human correction changing the outcome, see [Whack-a-Bug](whack-a-bug-case-study.md).
