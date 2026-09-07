# Ultimate Content Creator Hub — System Specification

Captured 2026-09-02 during a walk-your-business session, straight from the owner. This is a complete technical map of Tadeas's ("@creatortadeaas") Notion workspace — the Ultimate Content Creator Hub (UCCH) — plus the n8n automation layer wired into it, written so another AI system can reason about the data model, the relations between databases, and the exact read/write contract the automations have with Notion, without needing to re-discover any of it. Everything below was pulled live from the Notion workspace via the Notion MCP connection on 2026-09-02, including real schema definitions and live sample rows.

Workspace owner context: Tadeas, 21, CS student (Masaryk University), AI Engineer intern at Eviden, runs @creatortadeaas (30k+ Threads followers, 5k+ email subscribers, $5k+ in digital product sales). Building two businesses in parallel: (A) a freelance AI agent/automation agency (n8n + Claude API + Claude Code) — this repo's actual business — and (B) a creator brand selling low-ticket digital products about AI automation and content systems. The UCCH is both his actual operating system for running his content business AND the flagship "build in public" proof-of-concept of the AI-automation product he's building toward productizing.

## 1. Top-Level Architecture

The workspace root is the page "Ultimate Content Creator Hub" (1a025cd2-e540-80e0-83ed-de6102b6518a). It is laid out as a dashboard with a left navigation rail (25% column) and a main content area (75% column), organized into 6 sections:

```
Ultimate Content Creator Hub
├── Strategy & Foundation
│   ├── Brand Summary          (rich-text brand/business bible — see §2)
│   ├── Brand Identity         (mostly-empty worksheet: niche/purpose/mission/values/audience/visual identity)
│   ├── Content Pillars        (→ Pillars DB + Sub-Topics DB)
│   ├── Skill Tree             (→ Skills DB)
│   ├── Creators                (→ Creators DB  — THE SOURCE LIST FOR THE SCRAPER WORKFLOW)
│   └── Content System         (checklist of automated platforms + weekly content quotas)
├── Content Creation
│   ├── Content Manager         (→ Ultimate Content Manager DB, 4 views: Content Manager/Ideas/Calendar/Pipeline — all same data source)
│   ├── Inspiration Bank        (→ Viral Content Swipe File DB + Inspirational Content DB + Creators DB view — THE SCRAPER'S OUTPUT TARGET)
│   ├── Ideas Board             (→ Content Ideas view + Brainstorm Board DB + Archive DB)
│   ├── Platforms                (→ Social Media Platforms DB + Followers-across-platforms view)
│   └── Posting Schedule        (→ Content Posting Schedule DB)
├── Monetization
│   ├── CRM
│   ├── Finance Tracker          (Financial Overview / Accounts / Income-Expenses / Subscriptions / Income Sources / Expense Sources)
│   ├── Product Manager          (→ Products & Services DB, filtered to products)
│   ├── Service Manager          (→ Products & Services DB, filtered to services)
│   ├── Sponsorships & Affiliates
│   └── Testimonials
├── Creator Tools
│   ├── Analytics                (Followers / Views & Impressions / Top Performing Content / Other Analytics)
│   ├── AI Assistant             (ChatGPT prompt library)
│   ├── Hook Vault               (→ Hooks DB — THE HOOK LIBRARY THE n8n AGENTS READ/WRITE)
│   ├── Audio Bank               (Trending Audios + Audios DB)
│   ├── Hashtag Bank             (Hashtag Presets DB + Hashtags DB)
│   └── Resources                (Tags / Resources / Reference Materials)
├── Productivity Hub
│   ├── Tasks                    (Tasks DB + Tasks Calendar view + Completed Tasks view)
│   ├── Projects                 (Projects DB + Timeline + Deadline Calendar + Projects History)
│   ├── Goals                    (Goals DB + Key Results DB)
│   ├── Notes                    (Tags + Notes DB + All Notes)
│   └── Focus Mode               (embedded Pomodoro timer + Tasks view)
└── Backend
    └── Databases                (a flat index page listing every database in the workspace — used to map IDs, see §3)
```

Plus standalone swipe-file pages living directly under the hub root (not inside Inspiration Bank's database — these are older/manual swipe pages, effectively raw-text scratchpads of viral copy examples that predate/parallel the automated swipe file DB): Viral Thread Content Examples – All niches, Thread Hooks, Viral Thread Content Examples, Instagram Captions, Folder Organization (a suggested local folder structure for raw footage/B-roll/exports), Substack Inspiration.

## 2. Brand Summary (the context document the n8n "Fetch Brand Context" node reads)

The Brand Summary page (3bf25cd2-e540-80f7-bd22-e5f3b07bc821) is the page the n8n workflow's "Fetch Brand Context" node pulls via `getMarkdown: page`, feeding a Groq gpt-oss-120b Hook Selector agent alongside 10 candidate hooks for the viral-reel reconstruction pipeline (§5.2). These hooks are opening lines for short-form vertical video specifically — IG Reels and YouTube Shorts, spoken-to-camera/voiceover/text-on-screen — not Threads, X, LinkedIn, or any written-text platform. Rewritten 2026-09-07 to be short (~300 words, down from ~950) and hook-selection-specific, after it was found to be bloated (full pricing tiers, funnel architecture, a 9-layer internal-pipeline description — none of it relevant to judging a hook), stale (it presented the closed old digital-product business as an active track, and conflated the content audience with the agency's client ICP), and missing the format itself (nothing told the selector these are spoken video hooks, not written headlines). It now contains only:

- **Format note, stated first**: these are spoken/on-screen video hooks for Reels/Shorts only — judge each one as the first 1-3 seconds before a viewer scrolls past, not as written prose.
- **Identity**: one line — CS student, AI-eng intern at Eviden, building the AI automation agency (pre-revenue, one free case-study client in progress), the old Threads-growth digital-product business explicitly marked closed/do-not-pitch.
- **Content audience**: explicitly the existing Threads/IG followers (builders, creators, marketers, AI-curious people) — explicitly *not* the agency's SMB client ICP, which is who cold outreach targets instead.
- **Content topics**: AI tools/setup, AI agents for business, marketing/content automation, build-in-public logs, student/solo-operator life.
- **Voice rules ("Radical Authenticity")**: direct, no fluff, punchy, technical-but-accessible, never overclaims, the on-brand phrases ("I built this", "No team. No agency.", "This runs while I sleep") and the banned-language list, plus a reminder that hooks should sound spoken, not written.
- **The one rule that actually drives hook selection**: per `brand/contrarian-take.md`'s "Where It Shows Up" section, organic content is the one place the brand's "never lead with AI" sales rule does *not* apply — hooks should lead with AI and name tools, since that's what earns attention here. That rule only governs sales moments (cold outreach, price talk), not this content.
- **An explicit reject list**: no overclaiming revenue/clients/results beyond the pre-revenue reality, no reviving the old digital-product business, no flash-over-substance AI-demo hooks, no hooks that read like a written headline instead of something said on camera.

Note: `brand/voice.md` and `brand/guidelines.md` in this repo are still empty stubs (not yet built via their skills) — the Radical Authenticity rules, banned words, and on-brand phrases above currently live *only* on this Notion page. If those repo files ever get filled in, reconcile them against this page rather than letting two versions of "the voice" drift apart.

This page is the single source of truth an AI agent should read before generating any hook, caption, or script for Tadeas — and it is literally already wired into the n8n pipeline as its context node.

## 3. Full Database Schema Reference

All schemas below were pulled directly from Notion's data-source definitions (exact property names/types/options). Data source IDs (the `collection://...` UUIDs) are the stable identifiers to use for any programmatic read/write (Notion API `data_source_id`), since page URLs change but data source IDs don't.

### 3.1 Creators — `collection://1ce25cd2-e540-8067-965f-000bbb0f0c61`

This is the seed list the scraper workflow iterates over.

| Property | Type | Notes |
|---|---|---|
| Username | title | e.g. nick_saraev, mavgpt, bennettx.ai |
| Followers | number | |
| Median Views | number | The baseline the scraper multiplies by 7x to decide "viral" |
| Tier | select | S / A / B / C (a manual quality ranking) |
| Active | checkbox | whether this creator is currently being scraped |
| Last Calibrated | date | when Median Views was last recalculated |
| IG Profile URL | url | scrape target |
| Description | text | |
| Content Pillars | relation → Pillars DB | |
| Platforms | relation → Social Media Platforms DB | |
| Inspiration Bank Content | relation → Inspirational Content DB | |
| Viral Content Swipe File | relation → Viral Content Swipe File DB | back-relation — every swipe-file reel scraped from this creator shows up here |

Live sample (30 creators, all Active, all AI/automation-niche): Tier S = mavgpt (1.1M followers / 87,208 median views), nick_saraev (600K / 177,412 median views); Tier A includes alassafi.ai, brodyautomates, noevarner.ai, itsmariahbrunner, nateherkai, softgirlnocode; Tier B/C are smaller accounts.

### 3.2 Viral Content Swipe File — `collection://39525cd2-e540-8073-8037-000b7cea942f`

Lives inside the Inspiration Bank page. This is the scraper workflow's WRITE target.

| Property | Type | Notes |
|---|---|---|
| Title | title | short internal label, e.g. "ChatGPT Marketing Commands" |
| Hook | text | the transcribed opening line of the reel |
| Reel ID | text | platform reel identifier |
| URL | url | link to the original reel |
| Views / Likes / Comments / Engagement rate | number | |
| Viral Multiplier | number | = Views ÷ that creator's Median Views. Encodes the "7x median" filter rule |
| Viral Reason | text | AI-written analysis of why it went viral |
| Structure | text | breakdown of the reel's narrative structure |
| Reel Format | text | |
| Hook Delivery | select | Voiceover over Visual / Spoken + Text Match / Spoken to Camera / Text-on-Screen Only |
| Audio Type | text | |
| Caption / Caption Template | text | original + genericized/reusable version |
| Video Template | text | genericized/reusable version of the visual structure |
| Used | checkbox | whether this swipe entry has already been turned into a reconstructed reel |
| 📹 Creators | relation (1) → Creators DB | which creator this was scraped from |
| 📹 Hook Vault | relation (1) → Hook Vault DB | link to the hook once extracted into the Hook Vault |
| 📹 Social Media Platforms | relation (1) → Social Media Platforms DB | source platform |
| Hook Type | rollup (via Hook Vault relation) | pulls the Type select from the linked Hook Vault entry |

Live sample (12 most recent rows, Aug 18–24 2026): e.g. "ChatGPT Marketing Commands" — 229,840 views, 40.7x multiplier; "10 AI Projects" — 84,397 views, 25.1x; "AI Shut Up Skill" — 57,407 views, 14.1x. All `Used = NO` currently. A few rows have multipliers below 7x (3.8x, 5x, 0.5x) — either older/manual entries, borderline saves, or the live filter threshold is looser than exactly 7x in practice.

### 3.3 Ultimate Content Manager — `collection://1a025cd2-e540-8087-878b-000b9e5f0069`

The single database behind FOUR different views on the Content Manager page (Content Manager, Content Ideas, Calendar, Pipeline) and also behind the Ideas Board's "Content Ideas" view and the Tasks page's "Tasks Calendar" view. It's the master content-piece table. This is the reconstruction workflow's WRITE target ("Create Reel" node).

| Property | Type | Notes |
|---|---|---|
| Name | title | the content piece's working title |
| Status | status | grouped: Idea (to-do) → Planned / Research / Creating / Editing (in-progress) → Scheduled / Published (complete). n8n's "Create Reel" node inserts new pages with `Status = "Idea"` |
| Winning Hook | text | the selected/generated hook text — populated directly by the n8n pipeline |
| Priority | select | High / Medium / Low |
| Intention | multi_select | Build Authority / Connect / Entertain / Promote / Motivate / Educate |
| Publish Date / Published Link / Days Left | date / url / formula | |
| Platforms | relation → Social Media Platforms DB | |
| Content Type | relation (1) → Content Types DB | |
| Hashtag Preset | relation → Hashtag Presets DB | |
| Hook | relation → Hook Vault DB | link to the structured Hook Vault entry (distinct from the raw Winning Hook text field) |
| Products & Services | relation → Products & Services DB | which offer this content promotes |
| Sponsorships & Affiliates | relation → Sponsorships & Affiliates DB | |

Live evidence the automation is running: querying for `Status = 'Idea'` returns rows created 2026-09-02 and 2026-08-22, with Winning Hook text like "3 n8n Agent workflows you can deploy this afternoon" — clearly AI-reconstructed hooks in Tadeas's exact voice/formula.

### 3.4 Hook Vault — `collection://1d625cd2-e540-80df-87ad-000ba9c775f7`

The structured hook library. Read by "Fetch Viral Hooks" (`getAll: databasePage`) at the start of the n8n reconstruction workflow, and written to by the Hook Generator/Selector steps.

| Property | Type | Notes |
|---|---|---|
| Name | title | the hook text itself |
| Type | select | CHALLENGE / RANKING / TUTORIAL / FEAR / STORY / RESULT / CONTROVERSY / CURIOSITY / RELATABILITY |
| Performance | status | grouped: Not Used (to-do) → Poor / Average / Good / Amazing (complete) |
| Platforms | relation → Social Media Platforms DB | |
| Content Formats | relation → Content Types DB | |
| Related Content | relation → Ultimate Content Manager DB | which published pieces used this hook |
| Viral Content Swipe File | relation → Viral Content Swipe File DB | which scraped viral reel(s) this hook was extracted/inspired from |

### 3.5 Social Media Platforms — `collection://1a025cd2-e540-8026-8da3-000b10869eed`

Name (Instagram / TikTok / Threads / X / YouTube / Substack / Pinterest / LinkedIn), Growing Status, Current Followers, Followers Target, Follower Progress (formula), Launched At, My Account Link, Cover Image, plus relations to Content Manager, Inspiration Bank, and Creators (Mentors), and an Uploaded Content rollup.

### 3.6 Content Posting Schedule — `collection://1d125cd2-e540-803e-8427-000b4b2884a1`

(Also the "All Content" view on the Content Manager page.) Name, Day (Mon–Sun), Time, Content Type (relation), Platforms (relation).

### 3.7 Content Types — `collection://1a225cd2-e540-8030-a278-000b874dbb68`

A junction/tag table shared across Content Manager, Hook Vault, and Inspirational Content — one "format" tag (Reel / Carousel / Thread / Newsletter etc.) usable across all three.

### 3.8 Content Pillars — `collection://1ce25cd2-e540-80b4-9cb0-000b8f203a7b`

3 pillars on record: Copywriting, Social Media Marketing, Personal Branding — each with 3 linked Sub-Topics (separate Sub-Topics DB, `collection://1ce25cd2-e540-8010-9f4c-000b89b03b1f`).

### 3.9 Products & Services — `collection://1d225cd2-e540-81ae-af63-000b9d62a744`

Backs both Product Manager and Service Manager pages (filtered views of the same DB). Name, Type (Bundle/Service/Software/Community/Digital Product/Physical Product), Category, Status (Idea → Market Research → In Development → Pre-Launch → Active/Inactive), Price, Price Text (formula), Payment Model, Target Customer, Launch Date, Description, Cover Image, Related Content (relation → Content Manager).

### 3.10 Other databases (schema not fully expanded in this pass)

Profile Pictures, Bio, Typography, Color Palette (Brand Identity), Skills (Skill Tree), Sub-Topics, CRM, Financial Overview / Accounts / Subscriptions / Income Sources / Expense Sources (Finance Tracker), Sponsorships & Affiliates, Testimonials, Analytics, ChatGPT Prompts (AI Assistant), Trending/Audios (Audio Bank), Hashtag Presets / Hashtags (Hashtag Bank), Tags/Resources/Reference Materials (Resources), Tasks/Completed Tasks, Projects/Timeline/Deadline Calendar/Projects History, Goals/Key Results, Tags/Notes/All Notes, Archive, Brainstorm Board, Inspirational Content, Followers Across All Platforms.

## 4. Relation Graph (how the databases connect)

```
Creators ──(Median Views)──> [external scraper] ──writes──> Viral Content Swipe File
   │  ▲                                                          │  │
   │  └───────────────(📹 Creators relation)─────────────────────┘  │
   │                                                                 │
   └──(Platforms)──> Social Media Platforms <──(Platforms)───────────┤
                              │  ▲                                   │
                              │  └──(relation)── Hook Vault <────(📹 Hook Vault relation)
                              │                     │  ▲                 (Viral Content Swipe File relation)
                              │                     │  └── Content Types (Content Formats)
                              │                     │
                              └──(Content relation)──> Ultimate Content Manager <──(Hook relation)
                                                            │   │   │
                                            (Content Type)──┘   │   └──(Products & Services relation)
                                                                │
                                            (Hashtag Preset) ───┘
```

In words: `Creators.Median Views` is the benchmark → the scraper compares each scraped reel's Views against it → qualifying reels (Views ≥ ~7× Median Views) get written as new rows in Viral Content Swipe File, linked back to the source Creator and Platform. The reconstruction workflow reads unused (`Used = No`) Swipe File rows (and/or existing Hook Vault entries), runs them through the 4-step Gemini pipeline, and the final output is written as a brand-new page in Ultimate Content Manager with `Status = "Idea"` and Winning Hook filled in — ready for Tadeas to pick up in his normal content pipeline (Idea → Planned → Research → Creating → Editing → Scheduled → Published).

## 5. The n8n Automation Layer

Two separate n8n workflows are wired to this Notion workspace. Only the second was directly inspected (via screenshot); the first is inferred from description and corroborated by the live data in §3.1–3.3.

### 5.1 Workflow A — "Viral Reel Harvester" (scraper → swipe file)

- Source: iterates the Creators database (only rows with `Active = true`).
- For each creator, scrapes their public profile/reels (likely via an Instagram/TikTok scraping API or actor, since IG Profile URL is a field on Creators).
- Filter rule: keeps only reels where `Views ≥ 7 × Creator.Median Views` (stored per-row as Viral Multiplier).
- Analysis step (AI): for each qualifying reel, an LLM extracts Hook, Structure, Viral Reason, Hook Delivery, Audio Type, Caption/Caption Template, Video Template, plus raw stats.
- Write: creates a new page in Viral Content Swipe File, relating it back to the source Creators row and Social Media Platforms row, with `Used = false`.
- (Optionally) also creates/links a corresponding Hook Vault entry with a classified Type.

This is the "always-on ingestion" layer: it keeps the swipe file continuously stocked with fresh, proven-viral, niche-relevant examples, using each creator's own rolling median as a per-creator baseline.

### 5.2 Workflow B — "4-Step Gemini Hook→Reel Reconstruction Pipeline" (swipe file → Content Manager)

**Stage 0 — Context assembly** (runs once per execution):
1. Manual trigger.
2. Fetch Brand Context — Notion node, `getMarkdown: page` → pulls the Brand Summary page (§2).
3. Fetch Viral Hooks — Notion node, `getAll: databasePage`, returns 10 items → pulls top/candidate rows from the Viral Content Swipe File (or Hook Vault) database.
4. Aggregate Hook Data — merges brand context + the 10 fetched items into one payload.
5. Hook Selector — AI agent (Gemini, has Tools) — reads the 10 candidates + brand context and selects the best ones.
6. Parse Selected Hooks — parses the AI's raw output into structured data.

**Stage 1 — Fan-out:**
7. Split Out — splits the selection into 6 items (Hook Selector picks 6 hooks/reels to reconstruct per run).
8. Loop Over Items — iterates the 6 items one at a time.

**Stage 2 — Per-item 4-step Gemini reconstruction** (repeats once per looped item):
9. Hook Generator (AI agent, Tools) — generates a new hook variant in Tadeas's voice → Parse Generated Hooks.
10. Hook Evaluator (AI agent, Tools — **shown with a red/error border in the screenshot, meaning this node has failed at least once and may be worth checking**) — scores/critiques the generated hook → Parse Evaluated Hooks.
11. Full Reel Generator (AI agent, Tools) — takes the evaluated/approved hook and generates the full reel (script, structure, captions) → Parse Generated Reel.
12. Create Reel — Notion node, `create: databasePage` → writes the finished reconstruction into Ultimate Content Manager with `Status = "Idea"` and Winning Hook populated.
13. Loop returns to step 8 for the next item, until all 6 are processed.

There's also a disconnected standalone "Message a model" node visible in the canvas (not wired into the main flow) — likely a scratch/test node for prompt iteration.

### 5.3 End-to-end data flow (both workflows combined)

```
Creators DB (Active=true, has Median Views)
        │  scrape + filter (views ≥ ~7× median)
        ▼
Viral Content Swipe File DB  (Used=false, has Viral Multiplier, Hook, Structure, Viral Reason...)
        │  read top 10 candidates
        ▼
Fetch Brand Context (Brand Summary page)  +  Fetch Viral Hooks (10 items)
        │
        ▼
Hook Selector (Gemini AI #1)  →  selects best hooks → Split Out → 6 items
        │
        ▼  (× 6, looped)
Hook Generator (Gemini AI #2) → Hook Evaluator (Gemini AI #3) → Full Reel Generator (Gemini AI #4)
        │
        ▼
Ultimate Content Manager DB — new page, Status = "Idea", Winning Hook = <generated hook text>
        │
        ▼
Tadeas's normal manual pipeline takes over: Idea → Planned → Research → Creating → Editing → Scheduled → Published
```

## 6. Notable Observations / Open Issues

- **Idempotency risk**: nothing in the visible schema marks which Swipe File rows have already been fed through Workflow B other than the `Used` checkbox — worth confirming the reconstruction workflow actually sets `Used = true` after consuming a row. Current live data shows the most recent 12 Swipe File rows are ALL still `Used = No`, which either means Workflow B pulls from Hook Vault instead of directly from Swipe File, or `Used` isn't being written back yet — a potential bug/gap.
- **The 7x threshold isn't strictly enforced** in the data: several live Swipe File rows have Viral Multiplier well under 7 (3.8, 5, 0.5, 6.7, 6.9) — either the filter is "≥ ~7x OR other criteria," these are legacy manually-added rows, or the actual n8n filter node uses a different/looser threshold. Worth checking the actual filter expression if precision matters.
- **Hook Evaluator node has an error state** in the workflow screenshot (red border) — a likely recurring failure point, possibly a JSON-parsing/schema-validation failure against the AI's raw output before "Parse Evaluated Hooks" runs.
- **Brand Identity page is mostly empty** (niche/purpose/mission/audience fields are blank placeholders) — for brand-voice grounding, use Brand Summary instead, which is fully filled in and is already the page the n8n workflow reads.
- **Shared data sources across multiple "views"**: Content Manager / Content Ideas / Calendar / Pipeline / Tasks Calendar / All Content (Posting Schedule) are NOT separate databases — several page names correspond to the exact same underlying data source. Do not treat them as independent tables when writing automations.
- **"Hook" is ambiguous**: Winning Hook (free text field directly on Content Manager, written by the n8n pipeline) vs. Hook (a relation to the structured Hook Vault database). Any automation touching this needs to decide which one it's populating — currently live n8n writes only fill the free-text Winning Hook, not the structured Hook relation.
- All databases use Notion's newer `status` property type (grouped to-do/in-progress/complete) for pipeline-style fields (Content Manager Status, Hook Vault Performance, Products & Services Status) — behaves differently from a plain `select` when building filters/automations via the API.

## 7. Relevance to this department

This repo's `departments/marketing/research-team/researcher/skills/collect-swipes/` and `departments/marketing/content-team/copywriter/skills/write-hooks/` are lightweight manual equivalents of what Workflow A and the Hook Vault already do live, automated, in Notion. They are currently **not connected** to this real system. Wiring them together (or building a skill that reads the relevant parts of the UCCH directly) is a candidate follow-up — not done as part of this inventory session.

Compiled via the Notion MCP connection. All data source IDs, property schemas, and sample rows above are live as of 2026-09-02 and can be re-verified with `notion-fetch` on any `collection://` URL listed here.
