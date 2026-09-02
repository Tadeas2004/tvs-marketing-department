# Time & Tool Audit — September 2026

Companion to the 2026-09-02 walk-your-business session. Source data: `business.md` and `knowledge/ucch-system-spec.md`. This is what any future hire should read before picking work off the owner's plate.

## What Got Cut, What Got Kept

**No duplicate paid subscriptions.** Claude Pro (~$20/mo, covers Claude, Claude Code, Claude Design, Claude Cowork) is the only paid tool. Nothing to cut here — the cost problem this audit expected to find wasn't there. The real dead weight was in process, not spend.

**Kept, not cut — manual Notion swipe pages** (Viral Thread Content Examples, Thread Hooks, Instagram Captions, Substack Inspiration). Flagged as candidates for cutting, but the owner corrected this: they're hand-curated viral posts, from himself and others, saved specifically as future context for an AI hire writing this kind of content. Verdict: keep, but they currently have no owner — noted in `business.md` under What's Already Written Down as reserved context for a future Threads/Substack writer hire.

**Real duplicate found — two systems both claiming to collect swipes and hooks.** `departments/marketing/research-team/researcher/skills/collect-swipes/` and `departments/marketing/content-team/copywriter/skills/write-hooks/` file into `knowledge/`, completely separate from where the live n8n scraper writes (the Viral Content Swipe File DB and Hook Vault in Notion, see `knowledge/ucch-system-spec.md`). **Resolution direction agreed with the owner:** Notion becomes the single source of truth. These skills should be rebuilt as thin connectors that write into the same Notion databases via the Notion MCP connection, instead of keeping a second, disconnected local copy. Not rebuilt yet — this is the next structural fix, not done in this session.

**Claude Cowork** — still being learned, not cut, but the owner agreed it shouldn't get more investment right now: it would add to the learning bucket that's already oversized and crowding out revenue-generating work.

**Open, unresolved:** whether the old Gumroad storefront carries any live monthly cost was asked but not answered — needs a follow-up check.

## Ranking: What's Eating the Week

The owner didn't have measured actual hours per activity, so this ranking comes from an architected target week (below), built collaboratively after flagging that the stated 30–50h/week target was not survivable alongside internship + school + sleep. These are the numbers to track actuals against going forward, not a finished measurement.

| Rank | Bucket | Hours/week |
|---|---|---|
| 1 | Client delivery (the free bakery build) | 14h |
| 2 | Content creation (script + edit + post) | 10h |
| 3 (tied) | Business admin/infra (pricing, invoicing, DM inbox, sales prep) | 4h |
| 3 (tied) | Learning — now capped and need-driven, previously unbounded | 4h |

**Why this order:** client delivery is the one thing between the owner and a paid client, so it gets the most protected hours. Content creation was the most-resented, most-starved bucket despite being the actual lead engine (30k Threads followers) — it moves up, not down. Learning was previously the single biggest time sink with no cap; it drops to a fixed, need-driven allocation ("blocked on X for the bakery build," not open tutorial-watching).

## Price on What's Left (top 3 tiers)

Hourly rate used: **$75/hr** — the low-to-mid point of the agency's own stated consulting rate ($50–150/hr per the UCCH Brand Summary), chosen conservatively since there's no client track record yet. This is a rough number; replace it once real pricing settles from paid work.

| Bucket | Hours/week | Monthly value (hrs × 4.33 × $75) |
|---|---|---|
| Client delivery | 14h | ~$4,550/mo |
| Content creation | 10h | ~$3,250/mo |
| Admin/infra | 4h | ~$1,300/mo |
| Learning (investment, same opportunity-cost math) | 4h | ~$1,300/mo |

**Total implied value of the 32h/week business block: ~$10,400/month.** That's the rough cost of running all of this solo. Every future hire that takes over one of these buckets is worth approximately its line above — this is the number a hiring decision should be measured against.

## The Architected Week (32h/week target, not the stated 30–50h)

**Why 32h, not higher:** internship (3 days × 9h incl. travel = 27h) + school (~12h, estimated, unconfirmed) + sleep (56h at 8h/night) already claims 95 of 168 hours. At the top of the stated 50h target, only 23h/week would remain for everything else — meals, chores, and the girlfriend/football/gym time the owner already named as protected. 32h leaves 41h of the remaining 73h for life, not business.

| Day type | Block | Hours | Activity | Why |
|---|---|---|---|---|
| School day (×2) | Daytime | 4h each | Client delivery | Most daytime slack — protect it for the highest-stakes work |
| Internship day (×3) | Evening | 1h each | Content ops: post, quick review, DM triage | Low energy after an 8h internship day — reactive, not deep work |
| Weekend day 1 | — | 4h | Content batch: film/script/edit backlog | Weekend energy suits production work |
| Weekend day 1 | — | 2h | Client delivery buffer | Catch-up on the top-priority bucket |
| Weekend day 2 | — | 2h | Business admin/infra | |
| Weekend day 2 | — | 4h | Time-boxed learning, need-driven only | Capped on purpose — this was the uncontrolled sink |
| Both weekend evenings | — | protected | Girlfriend / football / gym | Not touched by business hours |

Total: 32h/week business, 41h/week of the remaining free time left unclaimed for life.

## Open Questions for Next Time

- Real internship/school weekdays and confirmed school-day hours (currently estimated at ~12h/week including travel)
- Whether Gumroad still carries a monthly cost
- Rebuilding `collect-swipes` and `write-hooks` as direct Notion-database connectors
- Track actual hours against this architected week for 2–3 weeks, then re-run this audit with real numbers instead of targets
