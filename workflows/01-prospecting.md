# Workflow 01: Prospecting (every Monday)

1. **Coordinator** reads `prospects/prospects.csv` and lists who is due for message 1, day-3 or day-7 follow-up.
2. **Prospecting** scores new rows against the 5 gaps and keeps those scoring 3 or more.
3. **Prospecting** drafts each message in Arabizi and French from the gap the CEO wrote, using `templates/outreach-messages.md`, and saves to `outputs/prospects-[date].md`.
4. **QA review** checks for placeholders left in, invented facts and unproven claims.
5. **CEO** sends the messages by hand and updates the Status column.

Rule: after message 3, stop. Set the status to "Revisit in 2 months".
