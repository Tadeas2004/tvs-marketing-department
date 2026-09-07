# Lead Gen Playbook

Captured 2026-09-07, pre-revenue, zero clients closed, zero dollars made from the AI agency yet. This is the acquisition sequence for getting from zero to a handful of case studies and testimonials — see business.md's "How Customers Find You" for which stage is actually live right now. Not a menu to run all at once: warm outreach first, and each later stage only turns on once the one before it has produced real proof (testimonials, a case study, referrals) to carry into it.

Paid acquisition (Meta ads, Google ads) is explicitly parked until $10k+/month in revenue — a low-ticket offer upselling into the high-ticket AI consultancy/build, not before.

## Stage 1: Warm Outreach (active now)

Hormozi's "warm audience" — everyone who already knows you: friends, family, phone contacts, current email list, social DMs. Already working: a high school friend mentioned the business to their dad, who owns a well-known bakery in Brno — that turned into the first free client (see business.md). The plan is to repeat that exact pattern for 2 more free clients from the warm network, trading free or discounted work for a testimonial, a case study, and 2 referrals each.

**The opening line, in the owner's own words** (natural, human, no pretending to be more than is true):

> "Hey, so the past couple of months I've been building these automations and I'm just like super passionate about it. I'm trying really hard. I want to start a business and I'm looking to just get some experience with helping people out with my AI systems. So do you know anyone who might be interested in AI or might benefit from just having a chat with me?"

**The ACA framework for DMs/texts** (Hormozi):
- **A**cknowledge something real about them, their business, or their life
- **C**ompliment naturally
- **A**sk a question that transitions into the offer

**Warm-network assets beyond friends/family:**
- 30k Threads followers — different niche (Threads growth / personal branding), currently rebranding toward AI content, already posting a lot about Claude and AI in general
- The old lead-magnet email list (Notion templates, Threads Growth Blueprint, AI prompts) — plan to send 2-3 emails a week targeting AI, share the cal.com link, and keep the list valuable with free AI resources alongside the pitch
- Long-form Threads posts about AI, angled toward selling AI automations/agents specifically in the marketing/content space — the natural fit given the existing audience — as a way to pick up free clients willing to let content-automation work get built for them

## Stage 2: Upwork & Fiverr

Freelance platforms as a place to do low-price work and collect the first real reviews, to build momentum and proof before pitching higher-ticket work elsewhere.

## Stage 3: Cold Email

An AI-powered cold email system: scrape leads (Apify, Apollo, LeadMagic), send through a tool like Instantly, personalize at scale, hundreds of emails a day.

## Stage 4: LinkedIn + X Content

Complementary to direct outreach, not a replacement for it.

- **Giveaways:** trade AI automation templates for a keyword comment + follow — builds the lead-magnet list.
- **Authority content:** show off real work — what's been built, for the business itself or for clients.

## Stage 5: Skool & Facebook Communities

Sharing demos and relatable posts inside niche communities where the audience already has the target pain.

**Reference case study (from a Nick Saraev / Make.com automation community, not the owner's own result — a pattern to copy, not a result to claim):** someone with years of ecommerce/store-owner background noticed a real, small, specific pain — suppliers not reliably sending weekly inventory reports. They built a one-step Make.com automation that auto-sends a Friday reminder email timed to when reports are usually ready, then posted it with a screenshot, referencing a video the group's admin had already made about why AI is worth implementing. The post got well-above-average engagement; several members asked about automating other parts of their business, and the admin himself wanted to use it — even though nobody in that thread was a paying client yet, it was enough to justify following up individually with everyone who commented.

**Why this pattern works, and why it's worth repeating:** it's a broadcast post into a community full of the exact ICP, not a 1:1 warm text — a different lead channel from everything else on this list. The framing matters as much as the build: show up as an in-group peer helping peers, not an outsider pitching in.

## Stage 6: YouTube Long-Form

Live tutorials, live builds, live automation/agent walkthroughs. Cal.com link in the description. Anyone who books off a video arrives already warmed up.

## Stage 7: Google Maps Scraping → Cold Pitching

Scrape local businesses and owner contact info via Maps/Apify, feed into the cold email system or cold calling below.

## Stage 8: Short-Form (IG Reels + YT Shorts)

Same keyword-for-lead-magnet mechanic as the LinkedIn/X giveaways, run as authority reels instead: live automation/agent builds, new AI tools, Claude/ChatGPT content, AI-in-business content. Viewer comments a keyword → gets the free lead magnet in exchange for their email → becomes a newsletter subscriber (feeds Stage 10).

## Stage 9: Social DM Outreach (IG, X, LinkedIn)

Scraped-lead, automated cold DM systems — mostly LinkedIn, and best started only once the LinkedIn profile itself is in good shape, since a cold DM lands on the profile first.

## Stage 10: Newsletter / Email List

Built from everything upstream — short-form content, giveaways, keyword-comment opt-ins. A warmed lead gets a sequence toward booking a free call, then becomes a regular newsletter reader.

## Stage 11: Blog (Owned Site)

Repurposed YouTube tutorials and newsletter content. Builds SEO over time. Links to the free call.

## Stage 12: Cold Calling

Fastest, most direct method. Scrape businesses and owner phone numbers (Apify), log to Notion/Google Sheets. Good example angle: call businesses after hours — if nobody answers, that's the pain (missed after-hours prospects) and the pitch writes itself: an AI receptionist covering after-hours calls. Works for non-voice automations too, not just voice AI.

## Stage 13: Loom Cold Email + LinkedIn DM

A personalized face-to-camera video, 1-2 minutes, that opens with the prospect's own LinkedIn profile visible in the video preview/thumbnail — instant, visible personalization before they even press play. Structure:

1. Icebreaker / personalization (their profile, their business)
2. Who you help + the pain point
3. What you do — the offer, in one line
4. Timeframe + simplicity
5. Why now / the special angle
6. CTA, no pressure

**Process:** Apify + Apollo.io scrape → save to a database → record the personalized video → follow up if no response.

## Lead Magnet & Low-Ticket Product Ideas

Hormozi logic behind all of these: a good lead magnet gives a fast, specific win tied directly to the exact problem the paid offer solves — not "download our AI guide," but something that does real work for the prospect in minutes and makes the paid version the obvious next step. For an AI agency, that means *showing*, not telling, that the build capability is real.

1. **AI Opportunity Audit** — a short quiz/scorecard (Typeform, Tally, or custom) on team size, tools, repetitive tasks → personalized report: "You're losing ~11 hrs/week to manual lead follow-up — here's what that costs annually," ending in "here's the 3-agent stack that fixes this." Pre-sells the paid audit using the prospect's own numbers.
2. **A working mini-agent, not a PDF** — an actually deployed tool, e.g. "steal our free lead-qualification bot," a Claude/GPT chatbot embedded on a page that qualifies a lead live. Proof of capability, not a claim of it.
3. **Automation swipe file** — "5 n8n/Make workflows we charge clients $3K+ to build — here's the JSON." Gated behind email. Genuinely useful standalone, but most people can't customize/maintain it themselves — the wedge for the service.
4. **ROI / cost calculator** — input hourly rate, hours spent, error rate → output annual cost vs. what an AI agent would cost. Persuasive because it runs on their own inputs, not a claim.
5. **"Watch me build it" teardown** — a short Loom/YouTube: "I built a customer support agent for a [niche] business in 22 minutes, here's every step." Gate the workflow file/prompt behind an opt-in.
6. **Pre-hire checklist / RFP template** — "17 questions to ask any AI agency before signing a contract." A trust play: not selling directly, arming the prospect to evaluate vendors, written so the business obviously aces every criterion.
7. **Niche-specific prompt/agent pack** — "50 Claude prompts to automate content repurposing for personal brands." Directly relevant to the existing Threads audience; doubles as a bridge from the old info-product world into agency clients.
8. **Free call framed as an audit, not a sales call** — "15-min AI Readiness Call," deliberately not called a "consultation." Live diagnosis, immediate value, and the natural next step is building what just got diagnosed.

**Best fit given this business's actual shape (technical + existing audience):** combine #1 or #4 (a tool, not just content) with #7 (niche-specific to the existing Threads following) — low cost to build, high perceived value, and it proves the exact capability being sold.
