# List building

How you find the right people to email, prove the list is clean, and hand it to the campaign.

| | |
|---|---|
| Used by | List Builder |
| Read with | [opinions.md](opinions.md), [market-research.md](market-research.md), [offers.md](offers.md), [copy.md](copy.md), [infrastructure.md](infrastructure.md) |

---

## The rules that never bend

1. Every list you pull lands in one place you own first: a master sheet or a database. Dedup and suppression only work if every campaign draws from, and writes back to, the same store.
2. Every list passes QA before it touches the sending tool. No list goes straight from a provider into a campaign. There is no "just this once."
3. Every email is verified with MillionVerifier before import. Keep the good results only.
4. Estimate credits and spend before every paid pull. Pull a sample first.
5. Headcount stops at 499 employees. Above that, enterprise spam filters eat the sends.
6. Never re-email existing clients, past replies, unsubscribes, or another campaign's active leads.

Why: the list is one of five variables in a campaign (list, copy, offer, the client's brand presence, infrastructure). When results are bad you need to rule the list out fast. A list that passed QA can be ruled out. A list that skipped it cannot.

---

## 1. From the research brief to list specs

The research brief and the test matrix come from [market-research.md](market-research.md). Your job is to turn each cell of the matrix into a list spec.

- A first launch is a test matrix, not a single bet: about 3 industries per client, 2 to 3 personas per industry. See [opinions.md](opinions.md).
- One list spec per industry and persona pair. Value prop, offer and CTA variants run on top of the same list, so they do not need their own lists.
- Go broad by default. A broad list of everyone in the ICP still reaches the people who would have shown a signal. They are in that list too.
- Validate the offer on a small batch before you scale volume against it. Do not build a full waterfall against an unproven angle.
- Speed beats perfection on an unproven segment. Take the quickest route, accept a slightly worse list, launch, then add steps once the segment works.
- Do not go super granular without a thesis. If a list is down to a couple hundred companies, you need a clear reason for going that narrow.

### List spec template

Fill one of these in before any pull. Save it next to the list in your master store.

```md
## List spec: [client] / [industry] / [persona]
Matrix cell: [industry #] x [persona #]
Offer it serves: [one line from offers.md]

Companies
- Industry / niche definition: [plain words, plus provider filter values]
- Geography: [countries, states, metro areas]
- Headcount: [range, max 499]
- Must have: [tech, ad activity, traffic, directory category, etc.]
- Exclude: [company types that look similar but are not a fit]

People
- Target titles and synonyms: [list]
- Seniority: [levels]
- Excluded titles: interns, coordinators, assistants, executive assistants, students, volunteers, plus [off-target titles for this offer]
- Contacts per company: all relevant ones, no cap

Qualifying signals (list only, never in the copy): [hiring, tech, ads, event, none]

Source and order
- Method: [database, Google Maps, look-alikes, followers, tech stack, event, directory]
- Sourcing order and why: [e.g. QuickEnrich, then AI-Ark for what its filters cannot express]
- Email-finding order: [e.g. Prospeo, then AI-Ark]

Merge variables the copy needs: [{FIRST_NAME}, {COMPANY}, {COMPANY TYPE}, ...]

Suppression lists to apply: [clients, past replies, unsubscribes, active leads in other campaigns, bounces]

Estimate
- Sample size pulled: [n]
- Expected total rows: [n]
- Credits needed: [n] of [balance]
- Expected spend: [amount]
- Approved by: [name, date]
```

---

## 2. Sources and methods

Pick the method from the segment, not from habit. Most databases are built on LinkedIn data, so a segment that is not on LinkedIn needs a different source.

| Segment | Method | Where the companies come from | Where the people come from |
|---|---|---|---|
| Broad B2B, on LinkedIn | Database search | QuickEnrich, AI-Ark | Same database |
| Local service businesses | Google Maps scrape | Pre-scraped Maps dataset or an Apify Maps scraper | Name permutations, then verify |
| Specialized niche the filters miss | Company look-alikes | Ocean, DiscoLike, or the AI-Ark look-alike feature | AI-Ark or QuickEnrich |
| People who care about a competitor | Competitor followers | LinkedIn company page followers (Boomerang or similar) | Enrich, then ICP check |
| Volume without picking an industry | Tech stack | Companies using a tool, such as HubSpot or Salesforce | Database |
| A client's upcoming event | Conference attendees | Attendee portal, sponsor access, public registry, event LinkedIn page | Enrich, then ICP check |
| eCommerce brands | Store database | StoreLeads (Shopify, WooCommerce) | Database |
| Marketing agencies | Directory or validated broad list | Clutch, or a broad AI-Ark list ranked for fit | AI-Ark |

### Database search
- Keywords are never perfect and industry filters are always bad, on every database. Never trust the industry filter alone.
- Search a specific company by its LinkedIn company URL. It is unique to the company.
- Exclude junior titles with the seniority filter, not only the title filter.

### Google Maps
- Use it when the regular databases come back empty for a niche, such as plumbers or cleaners.
- Two routes: download a pre-scraped dataset (quickest), or run a Maps scraper yourself (owns the process end to end). If the segment is unproven, take the quickest route.
- These files are huge. Load them into your database and filter to the target locations before anything else.
- This is the one good use for email permutations: first name, first name plus last name, first name dot last name. Three or four patterns cover roughly 80% of contacts. Do not run more. Verify every one.
- A business with no email goes on a call list.
- Personal (Gmail) and info@ style addresses are fine for local service lists or when TAM is running out. Ask your sending tool provider to approve Gmail sending before you load them.
- Do not add a LinkedIn step to a Maps list. Those leads are not on LinkedIn.

### Company look-alikes
- Seed the tool with businesses you know fit, such as the client's best case study.
- Companies first, people second: pull companies from Ocean or DiscoLike, then find the people in AI-Ark or QuickEnrich.
- If you already pay for AI-Ark, test its look-alike feature before buying another tool. Choose between Ocean and DiscoLike on entry price, not reputation.
- If a public database of companies in the industry exists (healthcare, accounting, and so on), use it as the company source and run the same people step.

### Competitor followers
- Scrape the followers of each competitor's LinkedIn company page. Best when the competitor is going through a change or a wave of distaste in the market.
- Most LinkedIn scrapers run on your own LinkedIn cookie. If something goes wrong, your account takes the hit. Know that before you run it.
- Followers include plenty of random people. Run an ICP check on every person and cut the off-target ones.
- Tell the Copywriter: never claim the prospect uses the competitor. You cannot prove it.

### Tech stack
- Technology is a broad signal. It says the company is relevant, not that it is buying this week.
- These lists run to hundreds of thousands. Keep one running in the background so volume never drops when you run out of industries.
- Other broad signals built the same way: a head of growth, a go-to-market engineer, or 3 or more SDRs.

### Conference attendees
- Sources, in order of ease: the attendee portal (first name and company, no email, so scrape and enrich), sponsor access (depends on tier), a public registry, the event's LinkedIn page followers.
- Page followers need an ICP check, the same as competitor followers.
- The list must be ready before the event. Outreach goes out before it starts, not during.

### eCommerce brands
- A small, inundated market. Every layer you add shrinks it further.
- Around 80% of a raw StoreLeads list is junk: drop shippers, bands selling merch. Classify the list with Claude Code and cut the junk.
- Revenue is not visible, so qualify by site traffic (SimilarWeb or a cheaper alternative).
- If the offer is tied to ads, use an ad intelligence tool to keep brands actively running Meta ads.
- StoreLeads is company level only. Enrich for the people afterwards.

### Marketing agencies
- Database searches return billboard firms, promo product companies and generic shops. Around 80% of agencies are big multi-service shops.
- Three routes: a broad AI-Ark list ranked 1 to 10 for fit by Claude Code; a Clutch scrape by service category (use the paid Apify scraper before building your own); or look-alikes for specialties.
- Outside agencies, ask Claude whether a directory, government database or register exists for the industry. Every segment has its own version of Clutch.

### Fingerprinting and lists
Fingerprinting is mostly a copy problem (see [copy.md](copy.md)). Your part: when a list is re-hit, the copy must change, and the list must be re-verified and refreshed (see section 6).

---

## 3. The enrichment and email-finding waterfall

A waterfall is a sequence of databases joined with stop logic: look in the first one, stop if you find the lead, otherwise move to the next. No single database has everything. A waterfall is also how you see the real TAM instead of the slice one database holds.

### Default order for a generic bulk pull
1. Your own master store. Free. Take every usable record you already own (fresh, verified recently, not suppressed) before paying a provider.
2. QuickEnrich. The cheap, broad layer. Fills the TAM.
3. AI-Ark. Real filters (industry, location, headcount band, seniority, company followers) for what QuickEnrich cannot express.
4. Prospeo. The expensive layer, and the strongest email finder.

### Email finding has its own order
1. Your master store, if the email was verified recently.
2. Prospeo.
3. AI-Ark.
4. Record the miss. Never guess an address, except the Google Maps permutations above.

### Rules for the waterfall
- The order is chosen per client and per campaign. For anything more specific than a bulk pull, decide the order from the task and write it, with the reason, into the list spec.
- At minimum, pair one cheap database with one expensive one, for example QuickEnrich with Prospeo.
- Start light. Until the offer is validated, one broad source is enough. QuickEnrich alone will get you started.
- Use your own API keys. Running Prospeo through Clay credits costs around four times as much. If you use Clay, plug in your own keys and let rows reach credit-priced providers only when your own keys come up empty.
- Contacts that come back without an email: send them down the waterfall, or route them to a LinkedIn campaign. Do not pay for them and then never work them.
- We do not use Apollo. Its data held too many people who no longer worked at the company.
- No speculative enrichment. Only find emails a campaign needs now.

### Verification with MillionVerifier
1. Export the list as a CSV.
2. Run it through MillionVerifier. Results come back good, risky or bad.
3. Keep the good results only.
4. Run personalization after verification, so you only pay for leads that passed.
5. Import the good file and map the variables.

- MX checks run by Claude are not verification. Still run MillionVerifier.
- Park catch-alls and risky results until the list and offer are proven. Then validate the catch-alls and run them in their own campaign. They often reply better because nobody else emails them.
- Bounce target: under 1%, 1.5% at most. A low bounce rate proves the list is clean. It says nothing about the health of your sending inboxes. See [infrastructure.md](infrastructure.md).

---

## 4. Relevance rules

- As many relevant contacts per company as you can find. Five relevant contacts at one company is great. There is no per-domain cap.
- The only filter is relevance to the offer. Drop every off-target title. Never put a CFO on a marketing offer.
- Never send to interns, coordinators, assistants, executive assistants, students or volunteers. They waste sends and raise unsubscribes, which tells mailbox providers the campaign is low quality.
- Headcount cap: 499 employees. Set it in the provider filter, then check it again in QA.
- Intent signals (hiring, funding, tech used, ads running, event attendance) decide who goes on the list. They never go into the copy. Find the signal, qualify with it, do not announce it.
- Do not chase perfect timing signals to rescue a weak offer. Intent lists are usually 1,000 or 2,000 leads, burn out in about two days, and pull a couple of good replies. Broad lists carry the campaign. If you are going in circles on signals, the offer needs work. See [offers.md](offers.md).

---

## 5. Dedupe and suppression

Run these against your master store, not just against the file in front of you.

| Remove | Why |
|---|---|
| Duplicate emails inside the list | Same person twice reads as spam |
| The client's existing customers | Never cold email a client's own customers |
| Anyone who replied before, on any campaign | They already gave an answer |
| Unsubscribes and opt-outs | Non-negotiable |
| Hard bounces | They do not receive email |
| Active leads in another campaign | Two campaigns hitting one person at once burns the bridge |
| Records in a re-hit cooldown | See section 6 |

- Also check the sending tool's existing leads and blocklist for that client before upload.
- Watch for parent and subsidiary duplicates: same domain, different legal names.
- Interested leads who never booked are not suppressed. They move to a retarget campaign and stay in the CRM until they say no.

---

## 6. Reusing lists (reactivation)

- Reply rates sit around 1.5% to 3%, so most of a list never responded. Every pass, a different 1% to 3% can reply.
- Re-hit a list every 60 to 90 days. Every 60 days is realistic for a small TAM. Some accounts run on 30.
- Be more conservative in small markets. Too many touches across email, LinkedIn and calls burns the bridge.
- For a big list on a proven offer, split it into three sections and run one per month, then loop.

Before every pass:
1. Re-verify the list, unless it was verified recently. Tag every stored list with its last verified date.
2. Refresh the roles. Every three months or so new people sit in the seats. Check for them at each company.
3. Make sure the copy has changed.

---

## 7. Merge-variable fields

The copy needs clean values in every field it merges. Get the field list from [copy.md](copy.md) before you build the export.

| Field | What it must look like |
|---|---|
| {FIRST_NAME} | A single, complete first name. No "N/A", no full name, no all caps, no special characters |
| {COMPANY} | The name a person would actually say, with no banned words |
| {COMPANY TYPE} | A plain category in the prospect's own words (for example "accounting firm") |
| Any custom variable | Filled for every row, or the row is dropped or the copy has a fallback |

### Run lead values through the spam check
Lead values merge at send time, after anyone has read the copy. A campaign whose copy passes can still send banned words through {COMPANY} and {COMPANY TYPE}. On one campaign, about 1 in 10 leads carried words like "Medical", "Home" or "Urgent" into the email this way.

1. Run the lead CSV through the spam check: github.com/growthflare-ignite/spam-check. Scan every column the copy merges.
2. Review every hit by hand. A mechanical fix that drops the banned word is only a first pass.
3. For company names, pick a clean version a person would recognize, for example shortening the banned part to initials.
4. For category fields like {COMPANY TYPE}, agree a replacement mapping with the Copywriter. Do not just delete the word.
5. Rows nobody can fix cleanly get dropped.

---

## 8. Estimate credits and spend before every paid pull

Never let a pull run without a number attached to it.

1. Pull a small sample first. Check that titles, companies and headcount match the spec.
2. Get the total row count from the provider's search before exporting.
3. Work out the cost from the provider's pricing. AI-Ark charges less for contacts with no contact information and more for contacts that have it. QuickEnrich is flat rate on its plans, but API credits on the entry plan are capped (25,000).
4. Check the balance in each tool before exporting.
5. Count the verification cost too: one MillionVerifier credit per address.
6. Write the estimate into the list spec. If it is above what the operator approved, stop and ask.

Ways to keep spend down:
- Draw from your master store before any provider. You pay for a contact once in AI-Ark and keep it, so a stored TAM pays off every time another campaign hits the same market.
- Verify only the batch you are about to send.
- Personalize only after verification.
- Use your own API keys, not Clay credits.
- Do not stack paid tools before the offer is validated.

---

## 9. List QA before upload

Score every list on these 8 dimensions, Pass, Warning or Fail. Then grade it. This applies to every list: database exports, scrapes, look-alikes and anything bought.

### List QA checklist

| # | Dimension | Check | Fail when |
|---|---|---|---|
| 1 | Email verification | Every address verified by MillionVerifier, good results only | Any unverified address |
| 2 | Duplicates and suppression | Deduped, and checked against the master store and the sending tool's existing leads, replies, unsubscribes and bounces | Over 1% duplicates, or any suppressed record |
| 3 | Domain relevance | Every contact on a shared domain fits the offer's persona. No numeric cap | Any off-target title on a shared domain (e.g. a CFO on a marketing offer) |
| 4 | Title relevance | Sample 20 random records against the spec's target titles and synonyms | Over 20% of the sample off-target |
| 5 | Bad titles | No interns, coordinators, assistants, executive assistants, students, volunteers | Any present |
| 6 | Catch-all density | Catch-alls removed or split into their own campaign | Warning over 5% |
| 7 | ICP alignment | Sample 20 records: industry, geography, headcount at or under 499 | Over 25% of the sample outside the spec |
| 8 | Name and field quality | First names clean, merge fields filled, spam check passed on merged values | Over 5% broken name or merge fields |

### Grading

| Grade | Criteria | Decision |
|---|---|---|
| A | All 8 Pass | Upload |
| B | 1 or 2 Warnings, no Fails | Upload |
| C | 3 Warnings, or 1 Fail on a low-impact dimension | Fix the warnings, then upload |
| D | 1 Fail on a high-impact dimension | Fix before upload |
| F | 2 or more Fails | Do not upload. Go back to the source |

- High impact: email verification, title relevance, ICP alignment.
- Low impact: name quality, catch-all density (if under 10%).
- Below a C, the list will very likely produce a positive reply rate under 1%. That burns domain reputation for nothing.

### Log every result
Save this next to the list in your master store.

```md
## List: [name]
Date: YYYY-MM-DD
Source: [tool or method]
Size: [n] records
Grade: A / B / C / D / F
1 Verification: Pass / Warning / Fail
2 Duplicates and suppression: Pass / Warning / Fail
3 Domain relevance: Pass / Warning / Fail
4 Title relevance: Pass / Warning / Fail
5 Bad titles: Pass / Warning / Fail
6 Catch-all density: Pass / Warning / Fail
7 ICP alignment: Pass / Warning / Fail
8 Name and field quality: Pass / Warning / Fail
Action taken: [uploaded / held for fixes / discarded]
Notes: [anything worth remembering]
```

---

## 10. Handoff

A list is ready to hand to the campaign when all of these are true:

- [ ] List spec filled in, with the sourcing order and the reason
- [ ] Spend estimate written down and within what was approved
- [ ] Every pulled record written to the master store
- [ ] Verified with MillionVerifier, good results only
- [ ] Deduped and suppressed against the master store and the sending tool
- [ ] Merge fields clean and spam checked
- [ ] QA graded C or better, with the result logged
- [ ] Last verified date tagged on the stored list

A list that passed QA is ready. That does not mean it is approved to import or launch. The operator approves that.
