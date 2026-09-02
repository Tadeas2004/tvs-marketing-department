---
name: lock-your-icp
description: Run the owner through a deep, multi-round interview until one real, specific customer comes into focus, pushing back on every vague answer, then fill their Notion ICP template and write brand/icp.md with their one-liner at the top. Use when the owner wants to lock in their ICP, figure out who they sell to, define their ideal customer, or asks who am I actually selling to.
---

# Lock Your ICP

Every piece of content and copy any other skill ever writes gets aimed at the person this file describes. The job is one real, specific human in focus and one sentence that names the transformation, not a category and a vibe. This is deliberately the longest session in the brand folder. Tell the owner up front to set aside real time, and if they need to stop partway, save everything and tell them to say "keep locking my ICP" to pick it back up.

## Before asking anything

Read business.md and the audit report. Read brand/icp.md so you know what already exists; you are sharpening it, never wiping it.

Confirm their copy of the ICP Notion template exists and your Notion connection can reach it; ask for the page if you do not have it. The interview fills that template as you go. If Notion is not available right now, run everything anyway and mark the template as pending a rerun.

Then sweep for anything else the owner has saved that describes their customers: the knowledge folder, anything in brand/, pasted playbooks, old proposals, testimonials sitting in the repo. Quote what you find back during the interview; their own saved material outranks their memory.

## Open with the broken thing

Before any structured question, say this in your own words: talk to me for two minutes about the moment this business started. What was the broken thing you kept seeing that made you think somebody should fix this, and who was it broken for? Then stay quiet and let them ramble. Most of the ICP is in this answer.

## Rounds, not a checklist

This interview runs in rounds, and one pass is never enough:

1. Round one: work through the six lenses below, one question at a time.
2. Stop and analyze: read everything they said against their business file, their audit, and their saved material. Tell them what you see, including what does not add up.
3. Round two: ask the sharper questions your analysis raised. These are usually the ones that matter.
4. Keep cycling until the picture stops changing. If the owner is giving one-line answers, slow down and dig into the last thing they said instead of moving on.

Never rush to the file. The file is the last ten minutes of a long conversation.

## The six lenses

1. Who this person actually is. Someone the owner could picture, with a name if possible: a past client, someone they have talked to, someone they know who lives with the problem. If nobody real exists yet, build the person as a named hypothesis to test on the first real customer.
2. Their current state. Where they are right now, what is frustrating them, and what it costs them in hours or dollars, not vibes. This is the zero state.
3. Their dream state. What they want to be true instead, in the words they would use. This is the hero state.
4. What makes them click. The proof that actually gets their attention.
5. What does not work on them. What turns them off completely.
6. Who they are NOT. Just as important as who they are.

## Push back, every time

This is the part that makes the file worth anything. Rules:

- A category is not an answer. "Small business owners" gets pushed: which one, name a person, describe the one you would call first.
- "Everyone" is rejected outright. Ask who they would turn away.
- A vague pain gets priced. "They struggle with marketing" becomes what it costs them in a normal week.
- Push at least once on every lens, even when the answer sounds fine. The second answer is usually the real one.
- If two answers contradict each other, say so and make them pick.

Never soften the file to be polite. An ICP that flatters the owner is worthless to every hire that reads it.

## The one-liner

When the rounds are done, distill everything into one sentence, in exactly this shape:

I help [specific person] go from [specific zero state] to [specific hero state] so they can achieve [specific outcome].

Rules for it:

- Every bracket has to be specific enough that a stranger could picture it. If any slot could describe a competitor's customer just as well, it is not done, push again.
- Build it out loud with the owner and rerun it until they would say it on a real call without flinching.
- The zero state comes from lens two, the hero state from lens three, the outcome is what the hero state buys them. If those do not line up, the interview missed something, go back.

If this sentence is not dialed in, they do not have a positioning problem, they have an unanswered business question, and this session is where it gets answered. It goes at the very top of the Notion template and brand/icp.md both.

## Fill the Notion template

Work through their duplicated ICP template through the Notion connection, section by section, and fill every part of it from the interview in the owner's words: the profiles, the personas, whatever sections the template holds. Where the template asks for something the interview did not cover, ask the owner now rather than leaving a blank or inventing one. When it is full, tell the owner to open it and look, this is their buyer laid out visually.

## Beef it up with their notebook

If the NotebookLM connection is set up (the notebooklm command works), ask the owner which notebook holds customer material, testimonials, call notes, market research, and interrogate it: what frustrations repeat across these sources, what exact words do customers use for the problem, what almost stopped them from buying. Fold the answers in as quotes.

If the connection is not set up yet, skip this without ceremony. A later lesson installs it, and this skill is worth rerunning after, the profile sharpens every pass.

## Write it into the repo

Update brand/icp.md with these sections, keeping anything already there that survived the interview: The One Liner, at the very top. The One Person. Current State and What It Costs. Dream State. What Makes Them Click. What Turns Them Off. Who They Are Not. Their Words, real quotes from real customers or their saved material, marked with where each came from. Add a line pointing at the Notion template page so future sessions know where the visual lives.

The repo file is what every hire reads before writing; the Notion page is where the owner sees it. Both stay in sync, and a change to one gets written to the other.

Read it back in under a minute and let the owner correct before saving. Their words throughout, cleaned but never corporatized.

## The ending, always

1. Say their one-liner back to them one last time, then tell them the one thing about this person they seemed to not know until today.
2. Remind them of the standing rule in one line: one ICP per piece of content, and every hire reads this file before writing anything.
3. Save the work to GitHub by running the github agent's save-work skill at departments/it-systems/dev-team/github-agent/skills/save-work/.

## Done when

The one-liner sits at the top of both the Notion template and brand/icp.md and the owner would say it on a real call, the template is filled section by section, the file describes one specific person they could call by name, every section survived pushback and at least two full rounds, real words are quoted with sources, the owner heard it read back and corrected it, and the work is saved.
