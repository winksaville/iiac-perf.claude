---
name: No output after finalize
description: Never emit text after vc-x1 finalize — it won't be captured in the session commit. Put recaps/next-steps into the approval message instead.
type: feedback
originSessionId: a592c173-65d0-4f86-aeb2-c3c8ab32305a
---
Any text output *after* `vc-x1 finalize` (including friendly recaps
like "next is ...") does not get recorded into the `.claude` session
commit, because finalize squashes trailing writes then pushes.

**Why:** The user pointed out that a post-finalize recap I emitted
was lost from the session history. CLAUDE.md already says "nothing
should happen after finalize" but I had been treating that as "don't
write files," not "don't emit text." It means both.

**How to apply:**
- Treat finalize as a hard stop for the whole turn — no prose, no
  tool calls, no status lines.
- If a recap, next-step note, or summary is worth saying, put it in
  the Checkpoint-2 approval message *before* running finalize, so
  it lands in the conversation before the commit is frozen.
- After the user approves, run the push+finalize command as the
  final tool call and end the turn.
