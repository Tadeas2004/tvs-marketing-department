# Business

## What You Sell
An AI automation / AI agent / AI systems agency for small and medium businesses (SMBs) — not enterprise. Building AI systems and workflows that save businesses money or time, or make them more money. Examples: AI receptionists, AI content repurposing agents, lead qualification workflows, sales prep automation, lead generation, invoice/payment follow-up automation, automatic email sending, email categorization. Stack includes RAG, MCP, n8n, custom scripts.

Pre-revenue right now. Working the first free client to build a case study before approaching paid leads.

## The Economics
First paid project: $100–$1,000 to start, moving toward $500–$3,000 once the offer, workflows, and delivery are dialed in and there's a track record. Pricing is lower now while still learning the technology and the business itself.

Expects repeat business and upsells from happy first clients — more AI projects once trust is built. Also plans a retainer/subscription tier for keeping automations running: hosting, monitoring, tweaking for better results over time.

Downsell for people who don't want a custom build: an AI audit / consultation, $50–$500, showing a business where it could use AI. Doubles as a lower-commitment entry point that can lead into a full build later.

Capacity: solo-run, still building. Estimate 10–15 clients a month before needing to scale — fewer if retainer/ongoing work is involved, more if projects are one-time builds.

## How Customers Find You
First lead (free/warm): a high school friend whose dad owns a well-known bakery in Brno, Czech Republic. The friend's dad wants AI in his workflows but doesn't understand automation. Mentioned it to the friend, who connected them. Offered a free audit + implementation to build case study experience — next step is visiting the bakery in person to audit their manual workflows.

Beyond this, plans to test cold outreach systems directly — Google Maps scraping, cold email — rather than relying only on content/inbound.

## What You Run On
**Paid:**
- Claude Pro (~$20/mo) — covers Claude, Claude Code, Claude Design, and Claude Cowork (Anthropic's newer tool-connecting agent, still learning it)

**Free / self-hosted:**
- n8n, self-hosted on Docker on the MacBook — only runs while the laptop is on, a real gap once client workflows depend on it
- Notion — second brain (content, leads, sales, money, tasks, school) and home of the Ultimate Content Creator Hub, see `knowledge/ucch-system-spec.md`
- cal.com — booking page for free AI-audit calls with prospects
- CapCut — video editing
- Canva — design
- VS Code — dev work
- Social accounts: Threads (30k, active), Instagram (500, active), X (1.5k, inactive), YouTube/LinkedIn/Substack (not posting yet)
- Gumroad store — old Threads-business storefront, deprioritized (see Won't Do / Already Tried)

**Just started:** OSVČ registration (Czech sole-trader status), 2026-09-02. No accounting/invoicing tool yet — needed once the free client converts to paid.

## The Week
Internship (AI engineering, Spring AI framework, MCP servers, enterprise AI applications): 3 days/week, 8 hours each, plus ~30 min travel each way.
School: 2 days/week (seminars/lectures), plus ~20–30 min travel each way, plus travel between school and internship on overlapping days.
Target for the agency + this business: 30–50 hours/week on top of the above.
Also maintains life outside work: girlfriend, football, gym.

**What actually fills the 30–50 hours, in the owner's own words:** "Every week, I learn on YouTube how to build AI workflows and n8n agents and workflows. Every week, I post on threads and IG depending on how much time I spend." Concretely: watching YouTube tutorials on running an agency / building agents / n8n / MCP / RAG; running the existing n8n automations (lead-qual/sales-prep, IG reel scraper, hook/reel writer); editing reels in CapCut and posting to IG; posting 2–3 long-form Threads posts; no hands-on delivery work for the free client yet (still pre-visit with the bakery).

**Biggest time sink:** learning new technology — n8n, AI agents, MCP, RAG, how to run an agency, how to sell, how to get clients.

**What's resented:** not creating content at the scope wanted — content keeps getting crowded out by learning. In the owner's words: "I need to run my agency and also creating content, which I still don't create in the scope I want." The two things that actually move the business forward (content volume, first client delivery) are currently the things being starved by time spent learning.

## What You Hate Doing
- Manual trend/content research (already built an n8n workflow to automate viral research)
- Writing scripts for reels/TikToks/Shorts/long-form YouTube/newsletters
- Editing video (not yet sure how to automate this)
- Manual design work in Canva — wants AI-generated designs from templates matching brand, but is allergic to generic "AI slop"; anything automated must actually match voice, writing style, brand colors, and guidelines, or it's worse than doing it by hand

Only work willing to keep doing by hand: filming the actual videos. Everything downstream (research, scripting, editing, design, repurposing) should be automated.

## Won't Do / Already Tried
Built and sold a Threads-growth-focused personal brand business (~27–30k Threads followers): a $39 written course in Notion, an AI prompt kit, a free ebook lead magnet ("Digital Product Playbook"), a Threads Growth Playbook, and Notion templates — sold via a landing page and Gumroad. Made roughly $5,000 over a year from it. Conversion rate on Threads was weak relative to the audience size, and content production was fully manual (writing every post from scratch in a plain Claude chat window with no brand system, and building every Canva visual by hand) — unsustainable and low ROI.

Decision: does not want to keep selling growth courses or continue that business as-is. This is a closed chapter, not a resource to build the new AI agency's marketing on — it does not feed into the new business's content or lead system.

Also tried: X/Twitter presence (~1,600 followers, inactive ~1 year), Instagram growth (~500 followers) — neither gained real traction, largely due to the same manual-production bottleneck.

Refuses to lead marketing/sales messaging with "AI" as the product — see the contrarian take in brand/contrarian-take.md.

## What's Already Written Down
Notion is the personal second brain: content, leads, sales, money, tasks/projects, and school all live there.

**The Ultimate Content Creator Hub (UCCH)**: a full Notion workspace + two live n8n workflows that already run the content engine — a scraper that watches 30 tracked AI/automation creators and harvests any reel outperforming that creator's own median by ~7x into a Viral Content Swipe File, and a 4-step Gemini pipeline (Hook Selector → Hook Generator → Hook Evaluator → Full Reel Generator) that reconstructs 6 of those into new content ideas in the owner's voice every run. Full technical spec, schema, and known bugs (an error state on the Hook Evaluator node, the `Used` flag not being written back) documented in `knowledge/ucch-system-spec.md`. This department's `research-team/collect-swipes` and `content-team/copywriter/write-hooks` skills are lightweight manual equivalents of this and are not yet connected to it.

An n8n workflow already qualifies leads who book a call via cal.com: scrapes the lead's website (if optionally provided), writes a personalized confirmation email, logs the lead into a CRM database, and preps the owner for the call.

From the old Threads-growth business (see Won't Do / Already Tried): the actual written voice and the Threads-native multi-post hook structure (a hook post that pulls the reader into a chain of value posts) are reusable — as a template for a future Threads-specific long-form writer hire once one is stood up. Not portable to other platforms as-is; a different hook approach is needed for X, LinkedIn, etc. Nothing else from that business (the $39 course, prompt kit, playbooks, landing page, Gumroad store) is being reused — deprioritized per the earlier decision.

## Who Else They Could Pick
The market is broad: other AI automation freelancers and solo operators, and agencies, found on Fiverr, Upwork, Instagram, YouTube, LinkedIn, X, and via Google search/SEO/GEO. Specific names mentioned: altari.ai (higher-ticket, thousands of dollars per project — not a direct competitor given the SMB focus) and @codebyaown_ on Instagram (a smaller solo AI automation specialist, ~1,800 followers).

Not considered real competition: SMB owners doing it themselves with ChatGPT — they generally lack the software engineering / automation development background needed to build and maintain these systems themselves, which is the edge here.

## Still to answer
Gaps surfaced during the 2026-09-02 walk-your-business session, flagged for a later session to pick up one at a time:
- No pricing framework for quoting an AI project live on a call
- No call-prep script or sales advisory — the lead-qual n8n workflow preps data (site scrape, CRM entry, confirmation email) but nothing preps the owner for the actual conversation
- No unified inbox — genuine leads DMing on IG/Threads/X/LinkedIn/YouTube comments risk going unseen
- Wants a free/cheap cold-outreach system: scrape leads from the internet, personalize outreach
- Wants a visual-memory system so every design (social, web, ad, logo, icon) stays on-brand and builds on prior quality work instead of starting blind each time
- No Threads-specific writer hire yet in `content-team` — expected per `platform-specialists.md` (specialists are only stood up once a channel is confirmed active), and Threads clearly qualifies now
- `research-team/collect-swipes` and `content-team/copywriter/write-hooks` skills are disconnected from the live UCCH/n8n system described in `knowledge/ucch-system-spec.md` — candidate for a dedicated skill that reads the relevant parts of the Notion hub directly
