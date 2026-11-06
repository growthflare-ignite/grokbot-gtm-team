# Grok Bot GTM team: working repo

Claude Code and Codex: you're running a unit of work for one of the Bots in this team. Read this first, every session.

## What you're doing

The Head of GTM sent you 5 parts: outcome, inputs, playbook, limits, and the client and campaign code. Do that outcome, inside those limits, for that one client. If a part is missing, stop and say so.

## Read before you work

1. `guides/rules.md`: the rules every Bot works by.
2. `playbooks/opinions.md`: what we believe about outbound. It sits over every other playbook.
3. The playbook named in the unit of work:
   - research and offers: `playbooks/market-research.md`, `playbooks/offers.md`
   - lists: `playbooks/lists.md`
   - copy: `playbooks/copy.md`, `playbooks/taste.md`
   - domains, inboxes, campaign builds, health: `playbooks/infrastructure.md`
   - replies: `playbooks/inbox.md`
4. The client's files: `clients/<client>/client.md` and the campaign's `clients/<client>/campaigns/<code>/campaign.md`.

If the playbooks and the campaign contract disagree, the contract wins only where it says so on purpose. If a decision needs a rule that isn't written anywhere, stop and ask. Don't fill it from general best practice.

## Hard limits

- Nothing is sent, launched, uploaded, enrolled, bought or deleted unless the unit of work says the person said yes to that exact item.
- Estimate credits and spend before any paid step. Stop at the contract's limit.
- One client only. Never read, mix or mention another client's files.
- Never invent data, counts, proof, results or customers.
- Never write a key or password to a file, a commit or a chat message. Keys come from `.env`.
- Never commit anything in `clients/`. Never push unless the person asks.

## Where things go

- Research briefs, lists, copy drafts and reports go in that campaign's folder under `clients/`.
- Every lead list also goes into the person's master lead sheet or database before anything else happens with it.

## How to finish

End every result with what you produced, where it is, what you checked, and what you didn't.
