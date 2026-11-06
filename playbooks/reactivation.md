# Lead reactivation

Find the people who replied with interest but never booked, and bring them back before you pay for another new lead.

| | |
|---|---|
| Used by | Lead Reactivation |
| Read with | [inbox.md](inbox.md), [taste.md](taste.md), [copy.md](copy.md), [lists.md](lists.md) |

## Why this exists

The list and the copy are only the front of the machine. Every campaign leaves behind people who said yes, more or less, and then nothing happened. They got busy. The reply came in on a Friday afternoon. Nobody on your side followed up. Going back through hundreds of old threads to find them is the job nobody has time for, so those leads sit there while you keep paying for new ones.

Rule from the training: do not let an interested lead go until they tell you they are not interested. Going quiet is not a no.

## Who owns what

| Job | Owner |
|---|---|
| Replies that came in today or this week | Inbox Manager ([inbox.md](inbox.md)) |
| Interested leads that went cold without booking | Lead Reactivation (this file) |
| Re-emailing a whole list every 60 to 90 days | List Builder ([lists.md](lists.md), section 6) |

## What counts as a forgotten lead

A lead is forgotten when all 3 are true:

1. **They showed interest.** Interested, asked for times, asked for the Loom or the material, asked a real question about the offer, or sent a referral to someone who never got contacted.
2. **No meeting is booked.** Check EmailBison: the lead isn't marked booked, and no time was confirmed in the thread. Booked by any route means they're out.
3. **Nobody followed up.** Either nobody ever replied to them, or our last message is more than 3 days old and they didn't answer it.

Leave out:

- Anyone who said no, asked to be removed, unsubscribed or bounced
- Anyone already booked, or who no-showed twice
- Out-of-office, auto-acknowledgments and system notices, even when the platform labels them interested
- People pitching you their own service

When the label and the words disagree, trust the words. Read the reply.

## The sweep

1. **Pick the scope.** One client. One campaign, or all of that client's campaigns. Default window: the last 180 days.
2. **Pull the replies.** Every reply in the window from the client's EmailBison workspace, with the full thread.
3. **Classify each one** with the triage categories in [inbox.md](inbox.md). Keep the interest categories only.
4. **Check bookings** in EmailBison: the lead's status, and whether a time was confirmed in the thread.
5. **Check the last touch.** Who sent the last message in the thread, and when.
6. **Apply the exclusions** above.
7. **Sort by days waiting**, longest first.

## The report

Lead with the headline, then the list.

```text
Client: [client]    Campaigns: [codes]    Window: [dates]
Replies read: [n]    Forgotten leads found: [n]
Longest wait: [n] days    Waiting over 30 days: [n]

| # | Name | Company | Campaign | Replied on | Days waiting | Last touch (who, when) | Their reply, word for word |
```

Then pick the 2 or 3 strongest. Say in one line each why the reply was a real buying signal (they asked for times, they named a problem, they asked about price or timing).

When the list goes on a screen or in a recording, names, emails and companies are personal data. Blur them, and read replies out anonymized.

## The follow-up drafts

One draft per lead. Every draft is marked **Needs approval** and goes nowhere until the person says yes to that exact draft.

Rules:

- **Reply in the original thread.** Never start a new one. The prospect sees their own words below yours.
- **Pick up from what they said.** If they asked for times, offer times. If they asked for the Loom, send the Loom. If they asked a question, answer it in one line.
- **Stand alone.** Someone who forgot the thread understands it from this email alone.
- **Make the next step easy.** 2 casual times in the next 7 days ("Tuesday at 4pm et or Thursday at 11am et"), or the material they asked for. One ask only.
- **Short.** Under about 50 words. Reads like a text from a friend.
- **No guilt, no nagging.** No "just following up", no "circling back", no apology essay for the gap, no new pitch. A short "sorry this slipped" is fine when we dropped the ball.
- **Run the spam check** on every draft before it reaches the person.
- **Nothing invented.** No prices, results, proof or capabilities that aren't in the client file.

### Templates

They asked for times and never got them:

```text
Hey [first name], sorry this slipped on our side. Still keen to show you [the thing they were interested in]?
Would [day] at [time] or [day] at [time] work?
```

They got times and went quiet:

```text
Hey [first name], are you still up for a quick chat about [the thing they asked about]?
[day] at [time] or [day] at [time] both work on our end.
```

They asked for material and never got it:

```text
Hey [first name], here's the [Loom / doc] you asked for on [topic]: [link]
Worth a quick 15 minutes to walk through it?
```

They asked a question that never got answered:

```text
Hey [first name], to answer your question: [one-line answer].
Worth a quick call to go through the rest? [day] at [time] works.
```

## After the yes

- Send each approved draft in its thread in EmailBison, from the inbox the lead wrote to.
- Move the lead into the meeting-request or info-request subsequence in the sequencer ([inbox.md](inbox.md)), so they get nudged until they book or say no.
- Update the pre CRM stage.
- Log it against the original campaign code, with "reactivated" as the source, so the rollup shows what the sweep earned.
- No reply after the subsequence: move them to long term follow up, then into the next retarget campaign for interested leads. They only go to Lost when they say no.

## How often

On call. Run a sweep when you ask for one, and always before a client's monthly review. If you find yourself asking every week, that's the signal to make it a routine, and the Head of GTM decides that with you.

## Common mistakes

- Trusting the platform's "interested" label without reading the reply
- Re-contacting someone who already booked through another link
- Re-contacting someone who said no or asked to be removed
- Starting a new thread instead of replying in the old one
- Writing a long apology or a fresh pitch instead of making the next step easy
- Showing names, emails or companies unblurred in a screenshot or video
- Sending before the person approved the exact draft
