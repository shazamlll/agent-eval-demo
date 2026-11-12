# Agent Eval Demo

Interactive demonstration of the evaluation methodology I use as a Senior SDET:
retrieval and generation eval datasets, deterministic checks, independent semantic
review, input decontamination, and dataset version freezing.

**Live demo:** https://shazamlll.github.io/agent-eval-demo/

## What this is

A single self-contained page (`index.html`, no build step, no dependencies) that
runs four pieces of the methodology in the browser:

1. **Retrieval eval** — tasks are requirements; gold answers are existing test cases,
   recalled and confirmed. Score: recall per task and overall, plus exact-match tasks.
2. **Generation eval** — a generated test case is scored twice: deterministic checks
   (preconditions, assertions, only valid IDs referenced, acceptance criteria covered)
   and an independent semantic review (task completion, tool use, prohibited actions).
3. **Input decontamination & leakage check** — paste a requirement; the checker flags
   it if the input itself names a gold answer ID.
4. **Dataset version freeze** — a frozen version stays reproducible; changes go into
   the next draft version.

## What is synthetic, and what is real

- **All sample data on the page is synthetic** — invented for this demonstration, in
  a fictional online-bookstore domain. It is not production data.
- **The methodology and the scale are real.** In my work I built a retrieval set of
  ~20 tasks / ~100 gold answers and a generation set of ~10 tasks / ~40 gold answers
  from archived requirements, with input decontamination, leakage checks, and a frozen
  test-case library version. Those datasets are internal and are not included here.

## Scope

Covered here: dataset construction, deterministic checks, semantic review,
decontamination, versioning.

Out of scope here: automated judge rubrics, pass thresholds, and CI eval gates —
those are not part of this demo.

## Run it

Open https://shazamlll.github.io/agent-eval-demo/ — or clone and open `index.html`
directly in a browser.

## Author

Zhenghao Li — Senior SDET, Hangzhou, China.
