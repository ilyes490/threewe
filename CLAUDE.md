# 3WE: working rules

3WE is a small marketing, branding, web and ads agency in Tunisia. The CEO orchestrates; Claude acts as the operations team, one agent role at a time (see `agents/`).

## Niche and offer
- Niche: independent cafés, restaurants and food shops in Ghazela and Ariana. Backup niche after 30 days of no traction: gyms and fitness studios.
- Packages (test prices): Site Care 40 DT/month, Starter 250 DT/month, Growth 550 DT/month, digital menu or one-page site 500-800 DT once.
- Billing: monthly in advance, no work before payment, 3-month minimum, extra posts charged.
- 60-day goal: 3 paying clients (about 750 DT/month) by January 8, 2027.

## Source of truth (decided Nov 9, 2026)
- The launch kit is the working source for packages, prices and targets. The offer catalogue (`offer_catalogue.md`) is the capacity reference.
- Capacity gap: about 40 production hours a month in the marketing pool, so about 1 Starter client at a time. See `outputs/capacity-gap-2026-11-09.md`. Never promise 3 Starter clients in a message or document.
- Prices 40 / 250 / 550 DT are confirmed. The agency is legalized (entity name still needed for invoices).
- There is no mentor: the team is young college students. Review = QA review + CEO approval. Never claim mentor supervision or university endorsement.
- Team members work alternately with their studies. Weekly hours per producer are still unknown ([FILL]).

## Languages
- Formal text: French. DMs: Tunisian Arabic in Latin script (Arabizi). Arabic script only on request.

## Hard limits
- **Draft, never send.** Never send a DM, WhatsApp message or comment. Never publish. Results go to `outputs/`; only a human moves them to `approved/` and sends or publishes them.
- **Never spend money.** Free first. Spend 0 DT until the first client pays; then tools take at most 15% of last month's revenue, capped at 100 DT.
- **No unproven claims.** No invented results, follower counts, "best in Tunis" or similar. No fake reviews or testimonials.
- **Ask, don't guess.** Mark missing facts `[TO CONFIRM]`. Never invent client facts.
- **Secrets stay in `.env`.** Never print, copy or commit them. Never search the machine for credentials.
- **No private client data in chat** (passwords, ID numbers, payment details). Use role-based access.
- **No signing.** Draft agreements and invoices only; a person signs.
- **One change at a time.** Run any new automation by hand on one client first.

## When something is missing
Stop and ask the CEO in this format:

NEED: what is missing
WHY: which task it blocks
FREE OPTION: the free way to get it
HOW I CAN GIVE IT: paste, file, connector or access role

## Log
End each session by adding two lines to `outputs/log.md`: what was done, and what is waiting for the CEO.
