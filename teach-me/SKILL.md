---
name: teach-me
description: Use when the user asks to be taught, walked through, or quizzed on work already done in the current session — a fix, a change, or a decision — so that they understand it, or when they run /teach-me. Not for learning an unfamiliar topic before work starts; that is blindspot. Not for an HTML explainer of a diff or PR; that is explain-diff.
---

# Teach me

Teach the user work done in this session until they can explain it themselves. The user demonstrates understanding; the teacher never declares it.

## Pick the topic

- If the user names a topic that this session worked on, teach only that topic.
- If the named topic, or the whole session, involved no work, say so, suggest blindspot for learning a new topic, and stop.
- If no topic is named and the session did one piece of work, teach that.
- If no topic is named and the session did more than one piece of work, list each piece in one line and ask which to start with. Wait for the choice.

## Keep a checklist

If the session has a scratchpad directory, create `teach-me-checklist.md` there (this skill is the user's request for that scratch file); otherwise keep the checklist in the conversation. List what the user should understand about the chosen topic, under three headings:

1. **The problem:** why it existed, and the options that were considered, if the session weighed any.
2. **The solution:** why it was solved this way, the design decisions, the edge cases.
3. **The broader context:** why it matters and what the change affects.

Tick an item only when the user answers its check question correctly. In chat, refer to items not yet taught by short name only (for example "the retry pause"); do not state their answers before the user attempts them.

## Teach one item at a time

Teach each item in four steps:

1. **Ask first.** The first message for an item is a single question asking the user to explain the item in their own words, with at most one line of framing.
2. **Fill gaps.** Name what they got right. For each gap in the current item, give a hint or a guiding question. Later items wait their turn.
3. **Drill why.** Ask why, then one deeper why. Show the code, or have the user run it, when that helps.
4. **Check.** Ask a multiple-choice question, with AskUserQuestion if it is available, otherwise in chat. Keep the options similar in length and detail, vary the position of the correct option, and reveal the answer only after the user submits.

Every question in steps 2 to 4 gets two tries. After a second miss, explain the answer and continue to the next step. If the user misses the check twice, the item stays unticked; move to the next item.

When the user asks for ELI5, ELI14, or ELII (explain like I'm an intern), match that level.

## When the user wants to stop early

If the user wants to stop while items remain unticked, the reply is: the unticked items, named in one line each, followed by one multiple-choice question that covers them. If the user answers correctly, tick only the items the question tested, then show the checklist. If the user answers wrongly or declines, stop, and state which items remain unconfirmed.

## Finish

When every item has been taught, show the checklist, and name any unticked items as unconfirmed.
