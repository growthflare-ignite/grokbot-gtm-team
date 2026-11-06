# Send the work to Claude Code and Codex

Grok Bot is great at running a team: clear jobs, group chats, reliable scheduled tasks. For the work itself (research, lists, copy, campaign builds) you get better results from Claude Code and Codex reading our playbooks in this repo, and their subscriptions are cheaper than Grok Bot credits. So Grok Bot orchestrates, and Claude Code and Codex do the work.

## The handoff

Any Bot that needs something produced, or data read, hands the Head of GTM a unit of work with 5 parts:

| Part | Example |
|---|---|
| Outcome | 2 variant sets for the free-audit offer, 3 emails each, checked and scored |
| Inputs | The campaign contract, the approved research brief, the client file |
| Playbook | `playbooks/copy.md`, plus the spam-check skill |
| Limits | Draft only. No upload, launch or send. No new proof numbers. |
| Client and campaign code | `acme-dental`, `ACME-TX-DENT-1106` |

The Head of GTM refuses a unit of work with any part missing.

## How the Head of GTM runs it

1. Through Grok Bot's local execution on your Mac, it runs `git pull` in `~/repos/grokbot-gtm-team`.
2. It starts Claude Code or Codex in a persistent terminal session (tmux) inside that folder, 1 git worktree per task. Claude Code reads `AGENTS.md`, which points it at the playbooks.
3. It sends all 5 parts as 1 prompt, waits, and reads the result.
4. It brings you the file to review, with what was and wasn't checked.

Because the sessions are real terminal sessions, you can attach at any time to watch, interrupt or take over: `tmux attach`. When you have something specific to build, open your terminal and work with Claude Code directly.

## Reading data

Bots don't hold connectors to your sending platform, inbox provider or data tools. When a Bot needs numbers (the rollup, capacity, replies, results), it sends a read-only unit of work, and Claude Code reads them on your Mac through that tool's API or MCP server, with your keys from `.env`. Writes (uploading a list, building a campaign, sending a reply) are separate units of work that run only after your yes.

## Which model for which work

| Work | Tool |
|---|---|
| Research, offers, diagnosis, judgment calls | Claude Code on its most capable model |
| Copy drafting and adapting | Claude Code |
| Scripts, scrapers, automations | Codex or Claude Code |
| Lookups and data reads | Claude Code on a fast, cheap model |

Pass the full model id when you pick one. A short alias can point somewhere you didn't expect.

## Connection test

The setup prompt runs this before creating any other Bot. Both must answer.

```bash
claude -p "Reply OK and name your model" </dev/null
codex exec "Reply OK and name your model" </dev/null
```

Only use one of them? Delete the other line. The team needs at least one.

## Where it runs

On your Mac. That's where this repo, your client files, your keys and your logins are. Grok Bot reaches it through local execution, and each command asks for your approval until you allow it in the settings. Keep Claude Code and Codex logged in on the Mac itself, so your subscription tokens never pass through the chat.

## When the handoff breaks

If the Mac is asleep or offline, a login expired or a subscription hit its limit, the Bot stops and tells you which. It doesn't fall back to doing the work on Grok Bot's own model.

## No Claude Code or Codex yet?

The team still works. Delete the "hand it to the Head of GTM as a unit of work" line from a Bot's instructions, paste the playbook it needs into its instructions, and it does the work itself. You can add the handoff later, 1 Bot at a time.
