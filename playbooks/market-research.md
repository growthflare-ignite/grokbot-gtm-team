# Market Research

How to find the angle for a client's campaign: interview the client, mine real demand, research each persona, and turn it all into validated pains and a test matrix.

| Used by | Market Researcher |
|---|---|
| Read with | [offers.md](offers.md), [opinions.md](opinions.md), [taste.md](taste.md), [lists.md](lists.md), [copy.md](copy.md) |

---

## Why this comes first

Value props and offers are built from validated pains. They are never written from a blank page.

A validated pain comes from three places, combined:

1. What the client knows about their customer.
2. Your own research on each persona.
3. Real data: sales call objections and public demand signals.

Real data beats invented pains. If you skip this step, the offer is a guess, and the copy can't save it.

Your job ends with a **research brief** (template at the bottom). The offer work in [offers.md](offers.md) starts from that brief.

---

## Step 1: Interview the client

### The onboarding form

The client fills it out as soon as they sign, before the onboarding call. It should ask for:

- Their industry or industries.
- Their offer, and exactly how they position it.
- Who they want to target.
- Everything they already know about their ideal customer.
- Their sales call recordings.

Tailor the form to the client's space (for example, a separate version for finance clients). A generic form that never asks how they position their offer leaves you guessing.

### The onboarding call

Go through their form answers. Ask questions. Clarify anything that was not fully explained. Then interview them about their customer.

Cover:

- Targeting: inclusions, exclusions, company size, geography.
- What a qualified lead looks like, in black and white.
- What they will and won't agree to give away for free. This gates every offer you can build. See [offers.md](offers.md).
- What their customers tried before them, and why it failed.
- The words their customers use to describe the problem.

### Sales call recordings

Ask for them every time. Farm them for real objections, pains and problems.

| Pull out | Why it matters |
|---|---|
| Objections, in the prospect's words | A guarantee or P.S. must answer a real objection, not a generic one |
| Pains they raise without being asked | These are the strongest candidates for a value prop |
| Exact phrases they use about themselves | Feeds identity mirroring in the copy |
| What they tried and got burned by | You anti-position against these 2-3 things |
| What made the deal close (or die) | Tells you what proof the market needs |

Quote the prospect directly in your notes. Paraphrasing loses the language the copy needs.

---

## Step 2: Mine demand

Find what the market already complains about, asks about, and grabs for free.

### Where to look

| Source | What it gives you |
|---|---|
| Reddit | Raw pain language, strongest for traditional SMB-owner ICPs |
| Hacker News | Strong for B2B, SaaS and technical pain |
| LinkedIn giveaway posts | What the market is receptive to. Hundreds of people commenting to grab a free asset is a demand signal |

Watch what people give away on LinkedIn in your client's market. Giveaway posts show you what the market will say yes to before you spend time building anything.

### The demand-miner tool

Repo: [github.com/growthflare-ignite/demand-miner](https://github.com/growthflare-ignite/demand-miner) (private Ignite repo, ask for an invite if you don't have access).

You give it an industry or an ICP. It finds the communities, harvests complaints, questions and giveaway posts, and uses Claude to cluster them into ranked painpoints. You don't need to know the sources up front.

```bash
npm run mine -- "<broad query>" [--mode offers|messages] [--sources reddit,hackernews] [--linkedin] [--limit 25] [--comments] [--recent | --days N]
```

| Mode | Use it for |
|---|---|
| `offers` (default) | What to **build**: ranked painpoints mapped to a lead magnet and a front-end offer, scored against the value equation |
| `messages` | What to **say**: the exact language your market uses, ranked by intensity, turned into questions and cold outbound hooks |

Run both on a new client. `offers` feeds the offer work. `messages` feeds the copywriter.

Tips:

- Add `--comments` for richer voice-of-customer. It costs more.
- Use `--recent` (90 days) when the market is moving fast.
- It runs on your own API keys. A lean run is about $0.25. A broad run with comments across all three sources is about $0.65.
- LinkedIn mining is off by default because scraping LinkedIn is against its Terms of Service. Turning on `--linkedin` means you accept that. Reddit and Hacker News alone carry the rawest pain language.

### Read the output honestly

- **Engagement is not intent.** Giveaway comments can be freebie seekers. Upvotes are attention, not budget. Treat the brief as a ranked list of hypotheses, not proof.
- **Source mix follows the ICP.** One source dominating usually means it is the more representative crowd for that audience.
- An LLM pass for research is fine. It does not replace real objection data from the client's calls.

---

## Step 3: Research each persona

Do this for every persona the client wants to target. For each one, pin down:

| Question | What you're looking for |
|---|---|
| Top pains | Specific, ideally revenue-linked. What keeps them up at night |
| Dream outcome | What they actually want, in their words |
| What failed them before | The 2-3 things they tried and dismissed |
| Their language | How they describe themselves and the problem. Not their database job title |
| Why now | Trends or pressure creating urgency right now |
| Awareness level | Do they know they have the problem? Do they know solutions exist? |
| Market sophistication | How many similar claims have they already heard? (Schwartz levels, see [offers.md](offers.md)) |
| Demand capture or generation | Do they search for this when they have the problem? Do they have budget for it? Do they know they need it before you tell them? Yes to all three is capture |

Use current sources. Cite them inline in your brief.

Identity language matters. Use the label the prospect would put in their own bio. "Most founders I talk to" lands. "Most sales guys" does not, because top reps don't think of themselves that way.

---

## Step 4: Turn findings into validated pains

A pain is validated when it comes from the prospect, not from you. Tag every pain with where it came from:

- **Client:** form, onboarding call, what they know.
- **Calls:** a sales call objection or quote.
- **Market:** demand-miner, Reddit, Hacker News, giveaway posts, persona research.

A pain with no source is an assumption. Drop it or go find the evidence.

Then check each pain:

1. Is it real and specific to this persona?
2. Is it usually revenue-linked, something they actually feel?
3. Would they care enough to reply if it were solved for free?

A frictionless offer for a pain nobody feels is still a dead offer.

---

## Step 5: Build the 5-layer test matrix

On a first launch, don't make one bet. Test broadly and in parallel across five nested layers, roughly 2-3 variations at each level:

| Layer | How many | Example |
|---|---|---|
| 1. Industry | About 3 per client | Three verticals the client has green-lit |
| 2. Persona | 2-3 per industry | Owner, head of ops, marketing lead |
| 3. Value prop | 2-3 per persona | One per validated pain |
| 4. Offer | 2-3 per value prop | Free deliverable, Loom, lead magnet |
| 5. CTA | 2-3 per offer | "worth sharing more?", "can I send you a quick video?", "is that worth a free trial?" |

Why: running all of it from the start is how the market tells you which persona, value prop, offer and CTA combination it wants. You build the strategy around what the market reveals, not around a guess. We are students of the market.

Rules for the matrix:

- **Go broad by default.** Signal-based campaigns are the exception. Only narrow when there is a genuinely strong signal, like hiring. Then aim at the most aware prospects with a harder CTA.
- **Speak to every awareness level at once.** The CTA layer is how you read awareness. Low-intent asks (a Loom, a document) win with the less aware. Hard asks (book a call, a free deliverable) win with the more aware.
- **Validate on a small batch before scaling.** Don't build a full list waterfall against an unproven angle.
- **Don't build the asset first.** Pick 6 or 7 angles from your value props and run them. Build the lead magnet only for the one prospects bite on.
- **Change one variable at a time** inside a layer once you are optimizing.
- **Judge on meetings booked, not reply count.** 50 replies where 30% book beats 5 replies where 1 books.

### Testing minimums

From our 3-campaign testing method:

- 200+ prospects per angle, same list quality.
- At least 300 emails per variant before you call it.
- Run at least 2 full weeks.

### Read the responses

| What you see | What it means |
|---|---|
| Reply rate up, meeting rate flat | Offer is intriguing but unclear. Add specificity |
| "We already have a supplier" | Reframe from service to outcome |
| "How much does it cost?" | Offer is too vague. Add proof and specificity |
| Replies fine, interested rate low | Wrong thing to the wrong person. Read a few leads' websites against your copy, then segment |

Feed objections from replies back into the brief. The research never really ends.

---

## The research brief template

Hand this to the Head of GTM for review, then to [offers.md](offers.md) work. Keep it to what the evidence supports.

```markdown
# Research brief: [client], [date]

## Client overview
[2-3 sentences: what they sell, how they position it, what they will give away free]

## Targeting
- Industries (up to 3):
- Inclusions / exclusions / company size / geography:
- Qualified lead definition:

## Personas
### Persona 1: [identity label they'd use about themselves]
- Top pains (each tagged Client / Calls / Market, with source):
  1.
  2.
  3.
- Dream outcome (their words):
- What they tried and got burned by (2-3):
- Language bank (direct quotes):
- Why now:
- Awareness level:
- Market sophistication level (1-5):
- Demand capture or generation:

### Persona 2: ...

## Objections (from sales calls and replies)
| Objection | Source | How often | Possible answer (P.S. or risk reversal) |

## Demand-miner findings
- Query and mode run:
- Top painpoints (ranked):
- Giveaways the market grabbed:
- Caveats (freebie seekers, thin sources):

## Test matrix (first launch)
| Industry | Persona | Value prop | Offer | CTA |

## Open questions for the client
-

## Sources
-
```

---

## Common mistakes

- Writing pains from a blank page instead of from calls, the client and the market.
- Never asking for sales call recordings.
- Paraphrasing objections instead of quoting them.
- Treating giveaway engagement or upvotes as buying intent.
- Building a campaign around a weak signal.
- Picking one persona and one offer and calling it a launch.
- Building the lead magnet before the angle has won.
- Judging angles on reply count instead of meetings booked.

## Before you hand off

- Onboarding form and call notes reviewed, sales calls mined.
- demand-miner run in both modes on the core query.
- Every pain tagged with a source.
- Each persona has identity language, awareness and sophistication noted.
- Test matrix filled in, roughly 2-3 per layer.
- Brief reviewed by the Head of GTM before offer work starts.
