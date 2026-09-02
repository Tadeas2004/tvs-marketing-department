---
name: walk-your-business
description: Walk the owner through everything their business actually runs on, in three parts, and write the inventory into business.md. Use when they want to audit their business, get everything out of their head, tell claude what tools and workflows they have, or say they are walking through their whole business.
---

# Walk Your Business

The brain dump captured what the business IS. This captures what it RUNS ON: every tool, every repeating job, every asset already sitting on their machine. Nothing else in the department can help with work it does not know exists.

## Before asking anything

Read `business.md`. It already holds what they sell, roughly what a customer is worth, and a first pass at their week. Open from there, never from a blank page: "Your file says most of your week goes to client work and admin. I want the real version of that today."

If `business.md` is still a stub, say so and offer the brain dump first. This is the second conversation, not the first.

## Start by letting them talk

Before any structure, say this in your own words: "Before I ask you anything, just talk. Everything about how your business actually runs, in whatever order it comes out. Tools, people, the annoying parts, the things you keep meaning to fix. I will sort it, you just ramble."

Then stay quiet and let them go. Do not interrupt to categorize. Take it all down.

Most of what matters arrives in this ramble rather than in the questions. The three parts below are for what they did NOT think to say.

## Part one: what you run on

Every app, account, and subscription they actually use. Ask it plainly, then chase the ones people forget:

- What is open on your screen right now, and what did you have open yesterday?
- What are you paying for monthly? Check the card statement if it is faster than remembering.
- What do you log into to get paid, to talk to customers, to make something?
- Anything you pay for and do not really use?

For each one worth keeping, get: what it does for them, roughly what it costs, and whether they would miss it. Do not chase precise pricing, "about thirty a month" is enough.

## Part two: the week that actually happens

What they really do, step by step, not the resume version. Then how much of the week each piece eats.

- Walk me through last week, not a typical week. What did you actually do Monday?
- What happens every single week without fail?
- What happens when a new customer arrives? Take me from first message to money.
- What do you do that you would struggle to explain to someone else?
- Which of these eats the most hours, and which one do you resent most?

The last question is the important one. Something that eats four hours and they enjoy is not the same as something that eats one hour and they dread. Both matter, differently.

## Part three: what you already have

Documents, templates, past client work, saved prompts, half-finished things, anything on the machine or in their head they would hate to lose.

- What do you copy and paste from, or reuse, when a new job starts?
- What have you already written down anywhere, even badly?
- What did you make once for one client that would work for others?
- What is only in your head right now, that would hurt if you forgot it?

Ask where each thing lives, in plain terms: a folder, a Drive, a notes app, a specific person's inbox. A resource nobody can find is not a resource yet.

## Stop after each part

At the end of each part, read back what you captured in under thirty seconds and let them correct it. Do not save all three and read at the end. Corrections are cheap in the moment and expensive later.

If a list comes back short, say plainly that a short honest list beats a padded one, and move on. Do not pad it for them.

## Write it into business.md

Add or extend these headings, keeping everything the brain dump already wrote:

- **What You Run On**: the tools, one line each, what it does and roughly what it costs. Group them the way they described them, not alphabetically.
- **The Week**: expand what is already there with the real step-by-step, and mark roughly how much of the week each piece takes. Note which ones they resent, in their words.
- **What's Already Written Down**: every resource, with where it actually lives.

Their words throughout, cleaned but never corporatized. Keep the specifics: the actual tool names, the actual hours, the actual sentence they used about the part they hate.

## If they have no business running yet

Walk their week instead. Where the time actually goes, what they already pay for, what they have already made. That is the starting inventory and it is a real one.

## The ending, always

1. Tell them the two or three things you noticed, not a summary. Something eating a lot of the week, a tool they pay for and never mentioned again, an asset they clearly forgot they had. This is the payoff for talking for an hour.
2. Anything thin or skipped goes to `business.md` under Still to answer, so a later session can pick it up one at a time.
3. Save the work to GitHub by running the github agent's save-work skill at `departments/it-systems/dev-team/github-agent/skills/save-work/`.

## Done when

`business.md` holds what they run on, the week that actually happens with rough hours, and where everything already written down lives. No stub text survives in those sections, the gaps are logged rather than guessed, and the work is saved.
