# The Grok Bot import

A Grok Bot can create other Bots, group chats and routines from its chat. This prompt uses your Head of GTM to build the whole team in 1 go.

Before you start, clone this repo to your Mac (it's private, so Grok Bot reads it from your Mac, not from GitHub):

```bash
mkdir -p ~/repos && cd ~/repos
git clone https://github.com/growthflare-ignite/grokbot-gtm-team.git
```

1. In Grok Bot, create a new Bot and call it **Head of GTM**.
2. Give it local execution on your Mac.
3. Paste the prompt below into its chat.
4. Answer its questions. It creates the rest and tells you what it couldn't do.

```text
Set up my Grok Bot GTM team from ~/repos/grokbot-gtm-team on my Mac.

1. On my Mac, run git pull in ~/repos/grokbot-gtm-team. If it fails, stop and tell me why.
2. Read README.md, AGENTS.md, guides/rules.md, guides/claude-code-and-codex.md and every file
   in agents/.
3. Run the connection test from guides/claude-code-and-codex.md. At least one of Claude Code
   and Codex must answer with its model. If neither does, stop and tell me exactly what is
   missing.
4. Ask me these questions in 1 message, then wait for my answers:
   - My agency, what we sell and who we sell to
   - The clients I'm running campaigns for right now (just names and a one-line description;
     you'll create a clients/<client>/client.md for each from templates/client.md)
   - Which tools we use for sending, inboxes, lead data and verification (the playbooks assume
     EmailBison, InboxKit or Premium Inboxes, QuickEnrich, AI-Ark, Prospeo and MillionVerifier;
     swap the names if needed)
   - My time zone, and when I want the morning rollup (default: weekdays 08:30)
   - Which Bots I want now (default: all of them)
5. Take on the Head of GTM instructions from agents/01-head-of-gtm.md.
6. Create each Bot I picked, with its name and the instructions block from its file, adapted
   to my tool names. Keep every rule about approvals, spend, connectors and clients exactly as
   strict as written.
7. Create a group chat called Campaign Room with the Bots I picked and you.
8. Create 1 routine: you, weekdays at the time I gave, the campaign rollup. No other routines.
9. Create clients/<client>/client.md for each client I named, from templates/client.md, with
   only what I told you. Leave the rest blank for me.
10. Show me what you created, anything you couldn't create with the step I need to do in the
    app, and which keys I still need to put in ~/repos/grokbot-gtm-team/.env (from
    .env.example).

During setup, don't connect any tool, send any message or spend credits.
```

After setup, connect only the tools each Bot's instructions name, read only (Slack, web search, Google Drive and Sheets, your calendar). Your sending platform, inbox provider and data tools stay off Grok Bot: Claude Code reaches them on your Mac with the keys in your `.env`.

## Prefer to do it by hand?

Create each Bot in the app and paste the instructions block from its file in [agents/](agents/). Start with the Head of GTM and the Copywriter; the others can wait until you need them.

## When this repo changes

The Head of GTM pulls the repo before every unit of work, so playbook changes reach Claude Code on their own. If a Bot's instructions block changed, paste the new block into that Bot.
