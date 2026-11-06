# Campaign contract

Copy this to `clients/<client>/campaigns/<CAMPAIGN-CODE>/campaign.md`. The Head of GTM fills it in, you approve it, and every Bot works against it. Anything this file overrides from `playbooks/opinions.md` must say so, with the reason.

## The basics

| | |
|---|---|
| Client | `<client-slug>` |
| Campaign code | `<CLIENT>-<GEO>-<SEGMENT>-<MMDD>` |
| Goal | e.g. 10 qualified meetings in 30 days |
| Owner | you |
| Status | draft / approved / building / QA / live / paused / done |
| Approved by you on | YYYY-MM-DD |

## Who we're emailing

| | |
|---|---|
| Industries | up to 3 |
| Personas and titles | 2 or 3 per industry |
| Company size | e.g. 10 to 200 employees (cap: 499) |
| Geography | |
| Exclusions | existing customers, competitors, the client's own suppression list |

## The offer and the test matrix

From the approved research brief (`research-brief.md` in this folder).

| Industry | Persona | Value prop | Offer | CTA |
|---|---|---|---|---|
| | | | | |

What the client has agreed to give away for free:

## List

| | |
|---|---|
| Target list size | |
| Sources and order | which tools, in which order, and why |
| Merge fields the copy needs | e.g. `{FIRST_NAME}`, `{COMPANY}`, `{COMPANY TYPE}` |
| Lead-count limit | stop here and ask |

## Sending

| | |
|---|---|
| Inboxes available (warmed) | |
| Daily volume per inbox | |
| Daily capacity | inboxes x volume |
| Sequence length | e.g. 3 emails |
| Days to work the list | list size x emails / daily capacity |
| New domains or inboxes needed | |

## Spend

| Item | Estimate | Limit |
|---|---|---|
| Lead data credits | | |
| Verification | | |
| Domains and inboxes | | |
| Demand mining and AI usage | | |

Every Bot estimates before a paid step and stops at the limit.

## Pre-launch QA

- [ ] List passed the list QA in `playbooks/lists.md`
- [ ] Every copy variant passed the spam check and the QA score in `playbooks/copy.md`
- [ ] Copy passed the reject-on-sight test in `playbooks/taste.md`
- [ ] Campaign build checked against the defaults in `playbooks/infrastructure.md`
- [ ] You said yes to launch on: YYYY-MM-DD

## Results and learnings

Filled in by the Head of GTM from the rollups. What won, what lost, and what the next campaign should do differently.
