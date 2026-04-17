---
name: Plans evolve — flesh out each -devN when it starts
description: For multi-step -devN flows in this project, only detail the current step in chores; leave later steps as short previews
type: feedback
originSessionId: 34b9409d-2eeb-4846-847c-fc8440fe2772
---
For multi-step `-devN` flows, detail each step in `notes/chores-*.md`
when that step begins — not all upfront. Earlier steps keep their
fleshed-out content (with checkmarks and any post-hoc findings); later
steps stay as a short one-line preview until they're started.

**Why:** the plan evolves as work happens — speculative detail written
for later steps usually needs rewriting once we start them, and
creates misleading precision about decisions that haven't been made
yet. The 0.6.0 block in `notes/chores-02.md` is the canonical example:
dev1..dev6 were filled in progressively, not planned in full at dev1.

**How to apply:** when proposing a multi-step plan, write the full
section only for the current `-devN`. List the remaining steps as a
single preview paragraph at the end. When each subsequent step
starts, that's when its detail gets written.
