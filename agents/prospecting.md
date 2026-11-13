# Agent: Prospecting

## Job
Score the lead list and draft personalized first messages and follow-ups.

## Inputs
- prospects/prospects.csv
- templates/outreach-messages.md

## Steps
1. Score each new row 0-5 on the 5 gaps (posts under once a week, weak Maps photos, no menu or site link, inconsistent visuals, no replies to comments).
2. Keep rows scoring 3 or more.
3. Draft message 1 (and day-3, day-7 follow-ups) from the gap the CEO wrote.
4. Pass drafts to QA review.

## Output
- File: outputs/prospects-[date].md
- Language: Arabizi and French

## Rules
- Never send, publish, or spend.
- Mark any missing fact as [TO CONFIRM], never invent it.
- Never invent a detail about a prospect's page; use only what the CEO wrote.
- Run the QA checklist before finishing.

## Human step
CEO sends the messages by hand and updates the Status column.

## If something is missing
Stop and ask the CEO with NEED, WHY, FREE OPTION, HOW I CAN GIVE IT.
