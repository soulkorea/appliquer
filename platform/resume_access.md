# Claude Platform — Persistent Resume Access

> Implements: Issue #34 (Enable persistent resume access)
> Scope: Claude only (Google Drive connector required)
> Status: Draft — not yet validated

## Mechanism

Appliquer is used via a **Claude Project**, not raw one-off chats.
The canonical resume is added once to the Project's Files, sourced
from Google Drive via Claude's native Drive connector. Every chat
started inside that Project has the resume in context automatically,
kept in sync with the Drive file as it's updated. No per-evaluation
retrieval logic is needed — the Brain never has to search or fetch
anything itself.

## Setup (one-time, user-side)

1. Create a Claude Project for Appliquer (e.g. "Appliquer —
   Opportunity Evaluation").
2. Set the Brain's instructions (constitution, decision engine,
   evaluation rubric, communication style) as the Project's custom
   instructions.
3. Place the resume in Google Drive, then add it to the Project's
   **Files** (Files section → "+" → Drive → select the file).
4. Any new chat inside this Project now has the resume as part of
   its knowledge, synced live to the Drive original.

## Updating the resume

The user edits the same file directly in Google Drive. Because
Project Files sync from Drive, no re-adding or re-uploading is
required — the next chat in the Project reflects the change.

## Acceptance criteria mapping

| Criterion | How it's satisfied |
|---|---|
| User can designate a canonical resume | Added once to the Project's Files |
| Appliquer retrieves it automatically | Present in every chat's context within the Project — no fetch step needed |
| No re-upload per evaluation | Project Files persist across chats |
| User can replace/update it | Edit the Drive file directly; Project Files stay in sync |
| Appliquer states which resume/version it used | Explicit Instructions addition (below), validated against a real job posting |
| Never assumes info not present | Existing Evidence/Inference/Unknowns framework (Step 3), reinforced by the fallback line in the Instructions addition below |

## Instructions addition — resume citation

Validation against a real job posting (Morgan & Morgan, Senior PM)
showed the Brain correctly read the resume but never named it in
the output. The following was added to the Project's Instructions
field, placed just after the `# Identity` block, to close that gap:

> Before the Opportunity Snapshot, include one line identifying
> which resume was used for this evaluation — file name at minimum,
> and the file's last-modified date if available from Project
> knowledge.
>
> Example:
> Evaluated against: Benjamin_Kim_Master_Resume.pdf
>
> If no resume is found in Project knowledge, state that explicitly
> and ask the user to provide one rather than proceeding on assumed
> or remembered information.

## Out of scope (for this platform, for now)

- Multiple canonical resumes / versioning history
- Any non-Drive storage backend
- Use outside a Project (plain chats without a persistent container)
- ChatGPT or other platform parity (tracked separately if/when needed)
