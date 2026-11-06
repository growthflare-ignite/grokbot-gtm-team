# The rules that keep the team safe

7 Bots with access to your clients' inboxes, lead data and sending platform need a few hard rules. These are already in every Bot's instructions.

## 1) Nothing goes out without your yes

No Bot sends, launches, uploads, enrolls, buys, pays for or deletes anything without your explicit yes on that exact item. Drafts are the default output everywhere. A check passing is not a yes.

## 2) Every campaign runs on a contract

The Head of GTM writes a [campaign contract](../templates/campaign.md) for every campaign: client, campaign code, goal, ICP, offer, test matrix, list size, sending capacity, and the spend and lead-count limits. You approve it before any work starts. Bots estimate credits and spend before any paid step and stop at the limit.

## 3) The work follows the order

Research brief, then list and infrastructure in parallel, then copy, then pre-launch QA, then your yes, then launch. Nothing skips the step before it. A list doesn't get built before the angle is approved, and copy doesn't get written before the list exists.

## 4) Our rules come from the playbooks

Copy follows [copy.md](../playbooks/copy.md) and [taste.md](../playbooks/taste.md). Offers follow [offers.md](../playbooks/offers.md). Lists follow [lists.md](../playbooks/lists.md). Sending follows [infrastructure.md](../playbooks/infrastructure.md). Replies follow [inbox.md](../playbooks/inbox.md). Forgotten leads follow [reactivation.md](../playbooks/reactivation.md). [opinions.md](../playbooks/opinions.md) sits over all of them. If a decision needs a rule that isn't written down, the Bot asks you. It never fills the gap from general best practice.

## 5) Each Bot names its connectors

Grok Bot has no per-Bot connector switch: once you connect a tool, every Bot could use it. So each Bot's instructions end with the only connectors it may use, and the Head of GTM holds the team to it. Connectors are read only. Writes happen through Claude Code on your Mac, after your yes.

| Bot | Connectors |
|---|---|
| Head of GTM | Local execution on your Mac, Slack read only |
| Market Researcher | Web search, Google Drive read only when asked |
| List Builder | Web search, Google Sheets when asked |
| Copywriter | None |
| Infrastructure & Deliverability | None |
| Inbox Manager | Calendar read only |
| Lead Reactivation | EmailBison, with the client's workspace API key |

One exception: Lead Reactivation connects to EmailBison directly, so it can read the reply threads it works through. It reads, and sends only a draft you said yes to. Because Grok Bot shares connectors across Bots, every other Bot's instructions keep it off EmailBison. Your inbox provider and lead data tools are never Grok Bot connectors. Claude Code reaches them on your Mac.

## 6) One client at a time

Every unit of work names one client and one campaign code. No output mixes clients. Never put one client's campaigns, replies or results in front of another client, and never name a client in copy without their permission.

## 7) Client data stays on your Mac

Client files live in `clients/`, which git ignores. Never commit or push client data, lead lists, replies or keys to this repo. Keys live in your `.env` or your password manager, never in a Bot's instructions or in chat.

## 8) The Head of GTM routes, specialists do

The Head of GTM plans, assigns and gates. When it starts doing the research, the list or the copy itself, the lane gets messy fast.

## 9) Keep routines rare

The team starts with 1 routine: the Head of GTM's rollup every weekday at 08:30. A routine earns its place only if you read what it produces every time.

## 10) Say what wasn't checked

Every result ends with what was verified and what wasn't.
