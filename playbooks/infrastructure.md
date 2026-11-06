# Infrastructure and Deliverability

How you buy, set up, warm, size, monitor and rotate sending infrastructure so emails land in the inbox.

| | |
|---|---|
| Used by | Infrastructure & Deliverability |
| Read with | [opinions.md](opinions.md), [taste.md](taste.md), [copy.md](copy.md), [lists.md](lists.md), [inbox.md](inbox.md) |

## Your job

Every campaign has three variables: the list, the copy and the infrastructure. Your job is to take infrastructure off that list. When results are bad, the student should know it is a list problem or a messaging problem, not the inboxes.

Rules that apply to everything below:

- Your sequencer is the source of truth. Read warmup, bounces and replies there, not on the provider dashboard.
- Buying infrastructure, pausing a live campaign and changing live settings are write actions. Propose them with the numbers, then wait for the student's yes.
- Weigh provider advice carefully. Providers earn more when you replace infrastructure, buy Google or send less per inbox. When something looks wrong, ask the sequencer's support. They have no stake in the inboxes.

## Domains

### What to buy

- Never send cold from the primary domain. Send from separate, brand-adjacent sending domains. If one burns, the real brand stays clean.
- Use lookalikes of the brand name, or the brand plus a descriptor (for brand.com, something like brandadvisory.com).
- Avoid spammy prefixes like get-, try- or the-.
- Buy .com first. It has been far outperforming cheap extensions like .info and .help.
- .co is the only other extension worth trusting. Take it when it is cheaper than .com at your registrar, because the reputation is very similar.
- Keep names readable and clearly tied to the brand, since they forward to the real site.
- Confirm the exact list with the student before ordering. Registration is the step that costs money up front and is annoying to unwind.

### How many

| Situation | Domains to start |
|---|---|
| Brand new, or staying conservative | 5 |
| Push some volume from the start | 10 |
| Reach the 100,000 sends per month range | 20 |

### Buying rules

- Bulk sending domains are never renewed. They get replaced at rotation, so turn auto-renew off on every one.
- Compare first-year price only when choosing a registrar or extension. Renewal price does not matter for a domain you will not renew.
- When a provider sells domains inside its platform and handles setup end to end, the small markup is usually worth it. Bringing your own domains can add about a week before mailboxes reach the sequencer.
- When there is a sale, buy extra domains and let them sit. Aged domains help at volume, even if they have never been on infrastructure.

## Inbox providers

There are four ways to send: Outlook inboxes, Google inboxes, raw Azure tenants on Outlook, and SMTP. Skip SMTP entirely. It runs on the provider's own servers without Google's or Microsoft's reputation behind it.

### InboxKit (Azure foundation)

API first, with Azure tenants, Google and Outlook on one platform. Its dashboard shows tenant thresholds, so you can see when a sequencer sends too much.

1. Load credits.
2. Buy domains inside InboxKit, .com first, with forwarding to the client's main site. Answer the DMARC questions at checkout.
3. In the Azure section, pick the domains, enter the first and last name for the inboxes, select 100 accounts and register.
4. Wait for provisioning. Expect 3 to 8 hours.
5. Add the sequencer as a connection. Accept the recommended warmup and the default incremental strategy. Set up a separate connection for each client.
6. Multi select the mailboxes, export them to the sequencer and pick the client. Leads go into the sequencer, never into InboxKit.

Take the full 100 accounts per tenant. 100 accounts at half the sends gives the same output as 50, and keeps the choice open later. Ignore the suggestion of about 2 sends per account. The tenant costs the same at 2 or 5, so fewer sends just means buying more infrastructure.

If a new tenant starts warming with a poor reputation score, do not wait for it to turn green. Ask for a new tenant. Some of the damage from landing in spam sticks.

### Premium Inboxes (Google layer)

A reseller of Google inboxes and Outlook accounts with an easy dashboard. Use it to spread risk across a second provider.

1. Buy domains first at a registrar. You cannot buy them inside Premium Inboxes.
2. Create the account.
3. Import the domains during setup.
4. Order 2 inboxes per domain.
5. Connect to the sequencer and warm for two weeks. Then send 10 cold and 10 warmup per day, and keep warmup on the whole time.

When to add Google:

- After the offer is validated on Azure, with a client locked in long term. Treat Google as insurance.
- Earlier when the market runs on Google, like ecommerce.
- Earlier when the list is small. If Google triples the reply rate, that is triple the output from a list you cannot grow.

Do not validate an offer on Google. It can cost four or five times as much as Azure for two to three times the output at most. With a large market, put the volume on Azure. A typical mix is about 70% Azure and 30% Google.

### Private Azure (scale and backup only)

Raw Azure tenants from a small reseller. Cheap, but there is little support, no API, and setup can take an extra week. Never build the foundation on it. Use it to scale on top of a premium foundation, or as backup capacity kept in reserve.

1. Contact the reseller. They give you credits and add you to their system.
2. Buy domains in the student's own registrar account. The reseller's portal marks them up.
3. Add the domains to their platform and set the name servers they give you. A status stuck on processing means the name servers are not set. Set them, then verify.
4. Order the mailboxes. Expect about four days for a small order and up to a week for a large one.
5. Run each account at 5 cold and 5 warmup, even if the reseller suggests more. 8 warmup plus 5 cold across 100 accounts has pushed a tenant over its threshold.

A throttled tenant cools down for a couple of days, then sends as normal.

### Spread the risk, but not too far

One provider selling every inbox type is not diversification. A back end problem there hits everything at once. Every extra provider also adds renewals, subscriptions and contacts. Two or three is the practical range.

## DNS and authentication

The providers above set SPF, DKIM, DMARC and domain forwarding for you when they provision. Your job is to verify, not to hand-build.

- SPF, DKIM and DMARC: confirm they exist for every sending domain before warmup starts.
- Forwarding: every sending domain forwards to the client's real website.
- Name servers: on private Azure, set and verify them or provisioning stalls.
- MX problems: if the sequencer flags one, run the domain through MX Toolbox and raise it with provider support.
- Blocklists: check sending domains against common blocklists, including SURBL, on a regular cadence.

## Warmup

- Warm every new mailbox at least 2 weeks, up to 3, before any cold send. Do not launch until every account shows 100% in the sequencer.
- Warmup never stops. Keep it running alongside cold sends for the life of the inbox. It dilutes the non responses.
- Split total sending 50/50 between cold and warmup: 5 and 5 per Azure account, 10 and 10 per Google inbox.
- Warmup emails come from other senders on the sequencer. A low quality warmup pool drags you down.
- Warmup reputation and inbox health scores mean almost nothing. A 95 can still hide a problem. A score only tells you something when it is terrible.

## Sending capacity math

Daily capacity = inboxes x cold sends per inbox per day.

| Provider | Unit | Cold per inbox per day | Daily capacity per domain |
|---|---|---|---|
| Azure (InboxKit) | 1 tenant = 1 domain = 100 inboxes | 5 | 500 |
| Private Azure | 1 tenant = 1 domain = 99 accounts | 5 | about 500 |
| Google | 1 domain = 2 inboxes | 10, ramping to 15 | 20, up to 30 |
| Outlook accounts (Premium Inboxes) | 1 domain = 2 accounts | up to about 20 | about 40 |

Sizing:

```
Azure tenants   = Azure daily volume / 500
Google domains  = Google daily volume / 30   (plan for 20 in the first weeks)
Monthly sends   = daily capacity x 22 working days
```

| Target per day | Azure tenants (100% Azure) | Monthly capacity |
|---|---|---|
| 5,000 | 10 | about 110,000 |
| 10,000 | 20 | about 220,000 |
| 25,000 | 50 | about 550,000 |
| 50,000 | 100 | about 1,100,000 |

Scale by adding inboxes, never by pushing one inbox harder. Reputation lives at the domain and tenant level. Think of each domain as having 100 HP: 2 per day for three months uses the same HP as 5 per day for 30 to 45 days.

## Ramp at launch

Even after full warmup, do not start Azure inboxes at 5.

- Set the daily campaign limit to 5, the starting limit to 1 and the daily increase to 1. It ramps from 1 to 5 over five days.
- Leave warmup at 5.
- On inboxes warmed less than two weeks, start lower and expect to replace them sooner.

## Default campaign settings

Apply these to every campaign unless the campaign brief says otherwise.

| Setting | Default | Why |
|---|---|---|
| Format | Plain text | Heavy formatting gets filtered |
| Open tracking | Off | Tracking pixels get you filtered |
| Click tracking | Off | Same reason |
| Unsubscribe link | Off | Use a short opt-out line in the body instead, written in the email's casual voice |
| Priority | New leads before follow-ups | 60% of positive replies come from email 1 |
| Daily limit per inbox | 5 Azure, 10 to 15 Google | Confirm it in the sequencer, never assume |
| Send window | Randomized, with delays between sends | Mimics a human |
| Distribution | Spread across every inbox | Never load a few inboxes |
| Signature | Sender name, domain as plain text, not a link | Gives the reader a way to look you up |

Before launch, confirm reply routing and opt-out handling work. See [inbox.md](inbox.md).

## Short copy is a deliverability lever

- Outlook and Google read short, one-liner emails as internal and human written, so they route them to the primary inbox. Long emails read as sales heavy. Target under 60 words, ideally under 50. See [copy.md](copy.md).
- For the first two weeks on new infrastructure, strip the copy to its simplest form, then build back up. New domains have no reputation, and Outlook is stricter until you earn one. A 0.5% to 0.7% reply rate on brand new infrastructure usually comes from heavy copy, not bad inboxes.
- The red flags are copy loaded with links and copy that is very long. Minimal links in the first touch.
- Run the spam check as code before anything sends. Expand every spintax combination and check every lead value that merges into a variable. Em dashes are a hard fail. Re-run after every fix.
- The more relevant and less automated the message feels, the fewer spam reports, and the longer the infrastructure lasts.

## What to watch after launch

Read the numbers in this order:

1. Booked meetings. The north star. If meetings are on target, nothing else is urgent.
2. Reply rate, including out of office replies. An out of office proves you landed in the inbox. Use this number only to judge deliverability.
3. Human reply rate: interested plus not interested replies, divided by people contacted.
4. Bounce rate.

Benchmarks: reply rates usually sit around 1.5% to 2%, and really good offers reach 4%. Low numbers are not a crisis if meetings are booking. Positive rates depend on the sequencer: one that counts out of office replies in the base will show 8% to 10% positive where another shows 15% to 20%.

Diagnose before changing anything:

- Reply rate low: an infrastructure issue, or copy that is too spammy or sales heavy.
- Reply rate fine, interested rate low: the wrong message for the person. Hand it to the Copywriter and List Builder with examples.
- Do not judge an angle on fewer than 1,000 leads. Keep an offer running about 90 days before calling it.

Inbox placement tests are isolated tests, not a real sending situation. Do not treat a clean test as proof the inboxes are fine.

## Deliverability rulebook

| Signal | Threshold | Action |
|---|---|---|
| Bounce rate | Under 1% | Healthy |
| Bounce rate | 1% to 1.5% | Acceptable. Check the list was verified |
| Bounce rate | Over 1.5%, or a sudden spike | Pause the affected campaign or domain with the student's yes. Bounces mostly point at the list, so send it back to the List Builder for verification |
| Domain reply rate | Below 1% over a week | Buy replacements now. Keep sending on the old domain while the new ones warm |
| Domain reply rate | Falling across the account | Point at infrastructure first. Run a split test to prove it |
| Blocklist | Domain listed on SURBL | Stop pushing volume through it. Replace it |
| New tenant | Poor reputation score at warmup start | Ask the provider for a new tenant. Do not wait it out |
| Tenant | Throttled | Expect a cooldown of a couple of days. Check cold plus warmup is not over the threshold |
| Account | Below 100% at the end of warmup | Do not launch on it |
| Sequencer | MX record warning | MX Toolbox check, then provider support |
| Reply rate | Sharp drop across clients | Escalate to the student the same day with numbers |

### Prove it before you blame it

The only reliable way to isolate an infrastructure problem is a control and one variable.

- Split by provider: send one list 50/50 through Outlook and Google. If one performs and the other does not, it is the provider.
- Split by batch: date every batch of inboxes you order. Send half a list through each batch and compare.

## Rotation

Do not rehabilitate burnt inboxes. A week trying to fix them, two weeks warming replacements you buy anyway, and the week of poor sending add up to a month lost.

- Plan on sending domains decaying over 60 to 90 days, and replace sooner when the rulebook says so.
- Start warming replacements about 2 weeks before you retire the old set, so there is no gap.
- Keep sending on burnt inboxes while replacements warm. At 0.5% reply you still get about a third of the results of good inboxes, which beats zero.
- On a tight budget, buy new domains and have the provider swap them onto the existing tenants. Same billing cycle, new reputation, still two weeks of warmup.
- Keep a few spare Azure tenants in warmup at all times, unused. When something goes down, bring them in with no downtime.
- Changing sending names does not reset warmup. Accounts carry no reputation of their own.

Leaving a provider: never cancel and reorder at once, or every client goes two weeks without sending. Order and cancel in rounds over 30 to 45 days, and expect that month's infrastructure bill to run about 1.5 times normal.

### Rotation checklist

- [ ] Signal recorded: which domains, which rule triggered, the numbers
- [ ] Student approved the replacement order
- [ ] Replacement domains chosen with the domain rules above, auto-renew off
- [ ] Ordered on the right provider, or swapped onto existing tenants
- [ ] SPF, DKIM, DMARC and forwarding verified on every new domain
- [ ] New inboxes connected to the sequencer under the right client
- [ ] Daily limits confirmed, signature set, warmup on
- [ ] Inbox batch dated for future split tests
- [ ] Old domains still sending during the 2 week warmup
- [ ] New inboxes at 100% before they take cold volume
- [ ] Ramp set: start 1, increase 1, cap 5
- [ ] Copy stripped back for the first two weeks on the new set
- [ ] Old inboxes kept live through a grace period so in-flight replies are not lost
- [ ] Old domains retired with auto-renew confirmed off
- [ ] Spare tenant pool topped back up

## Weekly health report

Send this to the Head of GTM and the student every week, per client.

```
WEEKLY HEALTH REPORT: [client] | week of [date]

Headline: [one line, for example: healthy, or 2 domains need replacing]

Capacity
- Active inboxes: [n] across [n] domains ([provider split])
- Daily cold capacity: [n] | Sent this week: [n]
- Spare tenants warming: [n]

Results (sequencer numbers)
- Booked meetings: [n] (target [n])
- Reply rate incl. out of office: [x]%
- Human reply rate: [x]%
- Bounce rate: [x]%

Domain watch
| Domain | Batch date | Reply rate (7d) | Bounce | Status |
| [domain] | [date] | [x]% | [x]% | [healthy / watch / replace] |

Rulebook triggers this week
- [signal, threshold, action taken or proposed]

Warmup
- Inboxes below 100%: [n]
- New inboxes in warmup: [n], ready on [date]

Needs the student's yes
- [purchase, pause or setting change, with the reason and the numbers]

Next week
- [rotations due, launches on new infrastructure, split tests running]
```

## Common mistakes

- Reading deliverability off the provider dashboard instead of the sequencer
- Treating warmup scores or placement tests as proof the inboxes are fine
- Launching before two weeks of warmup, or while any account is below 100%
- Starting new inboxes at full volume the day warmup ends
- Launching new infrastructure with long, heavy copy
- Turning warmup off once campaigns are live
- Pausing all sending while replacements warm
- Blaming infrastructure without a control to prove it
- Renewing bulk domains, or leaving auto-renew on
- Building the foundation on a cheap reseller or SMTP
