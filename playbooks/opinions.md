# Opinions

What we believe about outbound: targeting, offers, copy, personalization, follow-ups, CTAs, sending defaults and human gates. A starter version for you to make your own.

| Used by | All bots (Head of GTM owns it) |
|---|---|
| Read with | [taste.md](taste.md), [market-research.md](market-research.md), [offers.md](offers.md), [copy.md](copy.md), [lists.md](lists.md), [infrastructure.md](infrastructure.md), [inbox.md](inbox.md) |

---

## Read this first: these are GrowthFlare's defaults, not yours

This file is how GrowthFlare runs cold email for clients. Use it as your starting point, then make your own copy and adapt it.

How to make it yours (from the "Use Case 5: Create a taste-opinions.md" lesson):

1. **Have Claude interview you** for 30 to 45 minutes. Question after question about how you think. Don't write from a blank page.
2. **Keep two files.** `opinions.md` is what you believe about going to market. `taste.md` is what good looks like once you've decided what to say. Keep them separate so each can change alone.
3. **Write each entry as belief, reason, exception.** Example below: "Short beats long" has all three.
4. **Date every ruling.** When your view changes, the date tells Claude and your team which call is current.
5. **Mark open questions `[NEEDS YOUR VOICE]`** and park them. Never let Claude fill the gap with general best practice.
6. **Keep your own agency's positioning out.** Your pricing, your brand word list and your own offer go in a separate positioning doc.
7. **Give your team a one-page version:** the 5 rules that matter most, the default email shape, the follow-up rule and the reject-on-sight test.

Where you disagree with a default below, change it and date it. Where you haven't decided, keep ours until you do.

---

## Rules for the bot reading this file

1. These are beliefs, not suggestions. Follow them unless a campaign file explicitly overrides one.
2. If a task conflicts with an opinion, stop and ask. Do not silently pick one.
3. If an opinion is missing for a decision you have to make, stop and ask. Do not guess, and do not average the internet.
4. This file is business wide, across every client. Client overrides live in that client's file. Campaign overrides live in that campaign's file.
5. Scope check before adding anything: does it apply to any client's campaign, or only to your own agency's positioning? If the second, it goes in your positioning doc.

---

## Targeting

- **Launch as a test matrix, not a single bet.** Test 5 nested layers in parallel, roughly 2-3 at each: industry (about 3), persona (2-3 per industry), value prop, offer, CTA. That is how the market tells you which combination it wants. We are students of the market. Detail in [market-research.md](market-research.md).
- **Build the matrix from validated pains.** Combine what the client knows (onboarding form, onboarding call, sales call recordings) with your own persona research and demand mining. Real data beats invented pains.
- **Go broad by default.** Signal-based campaigns are rarely the best direction. The exception is a genuinely strong signal, like hiring: narrow to the most aware prospects and use a harder CTA.
- **Validate on a small batch before scaling.** Don't build a full list waterfall against an unproven angle.
- **Contact count per account doesn't matter. Relevance does.** Hit as many relevant contacts at a company as you can. Five relevant people at one company is great. Don't put a CFO on a marketing offer. Detail in [lists.md](lists.md).

## The offer

- **Cold email offer is not the business offer.** This file is about the front-end thing that earns a reply. Check which layer a claim is about before calling it a conflict.
- **The strong-offer test.** It solves a pain validated from the prospect, it's easy to act on with little commitment, and it gives the most value up front for the least work. Scored with Alex Hormozi's value equation.
- **Free deliverables win.** A free slice of the service beats a sample, a teardown or a lead magnet. Lead with it if the client will agree. Start from the best offer inside what the client is willing to do.
- **Match the offer to awareness.** Less aware prospects like information (lead magnet, Loom). More aware prospects like a free deliverable or a guarantee-based offer. Testing confirms it.
- **Guarantees are supplements, not the offer.** Put them in parentheses or a P.S. Tie them to a known objection. Use them more in less sophisticated markets (local services) than sophisticated ones (e-commerce).
- **Offer is not service.** The offer is what they get. The service is what you do. Cold traffic buys offers.
- **Lead with the slice, never the whole thing.** One solution, one prospect, one pain. The full mechanism is the second step, delivered in the asset or on the call, never in the email.
- Detail in [offers.md](offers.md).

## Copy

- **Short beats long, in about 90% of cases.**
  - Reason: attention and trust both start low. A long email makes them work before they get anything back. And ESPs read short emails as more human and route them to the primary inbox.
  - Rule: under 60 words, ideally under 50. Winners average 47 words. Losers average 59.
  - Exception: it exists, but the bar is high. If the offer is too complex for a short email, offer a sales asset that does the explaining.
- **Lead with the outcome, not the problem.** Poke-the-bear is almost always wrong. If the copy has to remind them of their problem, the offer is weak. Fix the offer, don't agitate harder.
- **The default skeleton.** One value-prop line plus a soft ask, with an optional P.S. The shape is fixed. Everything inside flexes.

  ```
  {first_name}, I [built / put together] [valuable thing] that helps [type of person]
  get [result] without [pain point / objection].
  [soft ask]

  [Signature]
  P.S. [optional proof, or a risk reversal tied to a known objection]
  ```

  The "without [pain]" names the problem as something they avoid, not a wound you reopen. No separate opener, the value line is the email.
- **Framework A is the default.** That's the skeleton above. Framework B (open on a "what if [outcome]?" question) is an allowed backup test, used sparingly.
- **Subject lines:** 2-4 words, lowercase, one merge token, about 16 characters. Default `fyi {first_name}`. Plain beats clever.
- **Voice:** every email reads like a text from a friend. Industry doesn't change it. No professionalism floor for serious verticals.
- **"You/your" runs about 30% higher in winners.** Make it about them.
- **Identity mirroring.** Use the language they'd use about themselves, not a database job title.
- **Anti-position** against the 2-3 things this market already tried and got burned by.
- **Spintax spins the words, not the psychology.**
- **No em dashes, no emojis, no hashtags.** No corporate filler ("synergy", "best-in-class", "cutting-edge"). A client's real industry terms are fine.
- **No dollar figures** unless they are literally part of the offer.
- **Run every email through the spam check** before it ships. Keep one banned-word list, not two.
- Detail in [copy.md](copy.md) and [taste.md](taste.md).

## Personalization

- **A good offer beats personalization every time.** Personalization only earns its place when it makes the offer more relevant.
- **Personalized first lines are mostly a crutch for lazy list building.** "Noticed your LinkedIn post about X" is not a reason to reach out.
- **The right use: a variable inside the offer.** "If we could introduce you to {ICP} looking for {their service}, would that be worth a chat?" The token makes one offer read as if written for that slice of the list.
- **Personalization stands in for segmentation you didn't do.** A perfectly segmented list wouldn't need it. It's a scaling tool, not a flourish.
- **Signals go in the list, not the copy.** Hiring or funding tells you who belongs on the list. Don't announce it in the email.

## Follow-ups

- **Only two moves, every time:**
  1. Cut words so the value is more visible.
  2. Soften the CTA and lower the friction.
- **Every follow-up stands alone.** The prospect never scrolls up to understand it.
- **No "just following up" or "just bumping this."** That is an instant reject.
- **Plan the length.** Email 2 pulls about 50% of email 1's reply rate. Email 3 drops another 50%.

## The CTA and booking

- **Default CTA: "would that be worth sharing more?"** Swap to fit the offer: "worth sending a quick video explaining more?", "want me to send it over?", "worth hearing more?".
- **One CTA, one question, answerable in one word.** Never two.
- **No hard meeting ask and no calendar link in email 1.**
- **Be specific about what they get.** "A two minute video explaining more" beats "sharing more" on reply rate.
- **Turn the yes into a call.** Come back with a time: "do you have 15 minutes on Tuesday?"
- **Judge CTAs on meetings booked, not replies.**
- **Book on your link, not theirs.** If a prospect sends their scheduling link, steer to yours with a light, honest reason.
- **Phrase times casually, inside the next 7 days.** "Tuesday at 4pm et", not a formal date stamp.
- Detail in [inbox.md](inbox.md).

## Proof

- **Never name a client in copy,** or use one client's results in another client's campaign, without explicit permission for that asset.
- **Never share real offer copy, list sources or results** in analysis, chat or anything screenshot-able. Show structure with placeholders.

## Sending defaults

Starting campaign settings, unless a campaign brief says otherwise:

| Setting | Default |
|---|---|
| Daily email cap | 10,000 |
| New sequence starts per day | 10,000 |
| Format | Plain text only |
| Open tracking | Off |
| Unsubscribe link | Off (opt-out text in the body instead) |
| Priority | New leads before follow-ups |

- **Sequencer access is read-only by default.** Any write is a human gate.
- **List building is not standardized.** It differs too much per client. Every list still passes list QA before it goes live. Detail in [lists.md](lists.md) and [infrastructure.md](infrastructure.md).

## Where the human overrules the bot

Bots draft. A human signs off on:

- **The offer.**
- **The copy, before it goes live.**
- **Any sequencer write:** launching, unpausing, editing a live sequence.
- **QA before launch, every time.** List check, copy check (spam check plus the reject-on-sight test in [taste.md](taste.md)), and sending setup.

## Still open (make these yours)

GrowthFlare hasn't ruled on these yet. Answer them in your own interview, then replace the tag and date it.

- What proof makes a claim like "this list is clean" trustworthy to you? `[NEEDS YOUR VOICE]`
- Any other human gates beyond the four above? `[NEEDS YOUR VOICE]`
- When a campaign underperforms: list first or copy first? How many sends before you kill an angle? `[NEEDS YOUR VOICE]`
- What reply signal tells you someone is a real buyer, not just polite? `[NEEDS YOUR VOICE]`
- What do you refuse to do that most agencies still do? `[NEEDS YOUR VOICE]`
- What has never worked, no matter how many times you tried it? `[NEEDS YOUR VOICE]`
