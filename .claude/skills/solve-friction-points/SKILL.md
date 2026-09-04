---
name: solve-friction-points
description: Interview the owner to find the five friction points that stop their ICP from buying, get the honest answer to each, and save the pairs to brand/friction-points.md. Use when the owner wants to find friction points, map objections, work out why buyers hesitate, or says they are solving friction points.
---

# Solve Friction Points

Friction is whatever slows the buyer down or stops them between finding the owner and paying them. This skill names five of them in the buyer's own words, gets the owner's honest answer to each, and files the pairs where every hire reads.

## Before asking anything

Read brand/icp.md and brand/contrarian-take.md. If the ICP file is still a stub, stop and say so. This runs after the buyer is locked in, so offer to do that first.

If the ICP file holds pasted evidence, a client thread, reviews, buyer messages, read it closely. The friction is usually already in there: the question they asked twice, the thing they needed reassurance on, the moment they went quiet.

## Find the five

Interview one question at a time, never a wall of questions. Work from evidence toward memory:

- Point at moments in their pasted evidence and ask what was really going on there.
- What is the question every buyer asks before they say yes?
- What almost stopped your last customer from buying?
- Who did they compare you to, and what nearly won?
- What do people say when they ghost, or right before they do?
- What would their boss, partner, or spouse push back on?

Write each friction point the way the buyer would say it, first person, plain words. "I don't have time to learn another tool" is a friction point. "Time constraints" is not.

Five is the number. Fewer and you stopped too early, more and the list stops being sharp. If the owner is flowing past five, capture the extras at the bottom, unranked.

## Get the honest answer to each

Go one at a time. For each point ask: what do you actually say when a buyer raises this across the table? Push past the sales version. The marketing answer is banned here; the honest one is what their hires will need.

Answers come in three kinds. Name which kind as you go:

- Proof: something that happened that answers it. A result, a story, a number.
- Mechanism: how the offer or the process actually removes the friction.
- Unsolved: they do not have an answer yet. Mark it UNSOLVED and move on. An honestly unsolved point is worth more than a padded answer. Never invent an answer for them.

## Write it into the repo

Save to brand/friction-points.md:

- A one-line header saying what this file is and that it pairs with the ICP file.
- Five numbered pairs: the friction point in the buyer's words, then the answer with its kind (proof / mechanism / UNSOLVED).
- Extras below the five, unranked, if any came up.

Read the five pairs back to the owner in under a minute and let them correct before saving. Their words survive, cleaned but never corporatized.

## The ending, always

1. Tell them which friction point looks strongest as content ammunition and why, one or two lines.
2. Anything marked UNSOLVED gets a line noting it is a real business gap, not a writing problem.
3. Save the work to GitHub by running the github agent's save-work skill at departments/it-systems/dev-team/github-agent/skills/save-work/.

## Done when

brand/friction-points.md holds five friction points in the buyer's words, each with an honest answer or an UNSOLVED mark, the owner has heard them read back and corrected them, and the work is saved.
