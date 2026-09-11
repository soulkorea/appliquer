# Claude Platform — Network Leverage Check

> Implements: Network Leverage evaluation dimension
> Scope: Claude only (Claude in Chrome required)
> Status: Draft — not yet validated

## Mechanism

During Step 3 — Identify Evidence of every evaluation, Claude uses
Claude in Chrome to search LinkedIn for 1st- or 2nd-degree
professional connections at the target company. This runs
automatically, without the user asking for it, as part of the
standard evidence-gathering pass — not as a separate opt-in step.

## What counts as evidence

- **1st-degree connection at the company** — Evidence. Strongest
  form of Network Leverage; the user can reach this person directly.
- **2nd-degree connection at the company** — Evidence, but weaker.
  Reachable only through a mutual connection, and reachability
  depends on whether that mutual is willing to introduce.
- **No connection found** — Unknown, not an assumed absence. LinkedIn
  search coverage is incomplete (see Risks below), so a failure to
  find a connection never becomes "no connections exist" in the
  output.

## Output

- The result of the search appears under the **Network Leverage**
  dimension in Detailed Evaluation, with a rating, the connection(s)
  found (name, degree, title if available), and confidence.
- If at least one connection is found, add a corresponding entry
  under the **Networking** category in Suggested Actions (e.g.
  reach out to the named connection, or ask a 2nd-degree connection's
  mutual for an introduction).
- If no connection is found, Network Leverage is reported as Unknown
  and no Networking action is added on that basis.

## Known risks

- **LinkedIn rate-limits and blocks automated browsing.** A search
  can fail or be blocked mid-session. When this happens, Network
  Leverage must report as Unknown — the check failing is not
  evidence of absence — and the failure must not abort or fail the
  rest of the evaluation.
- **Coverage is limited to the user's own visible network.** The
  search only surfaces what the user's LinkedIn account can see:
  people outside their 1st/2nd-degree network, connections with
  restricted visibility, and people who aren't on LinkedIn at all
  are invisible to this check regardless of whether a real-world
  connection exists.

## Out of scope (for this platform, for now)

- Any non-LinkedIn source of professional connections
- 3rd-degree or "same company alumni" style weaker signals
- ChatGPT or other platform parity (tracked separately if/when needed)
