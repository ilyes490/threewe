# 3WE Claude Code Blueprint

Nov 9, 2026 · @ilyes

## Starter prompt

Paste this at the start of each Claude Code session, from the project folder. It tells Claude Code how to work and how to ask you for anything it is missing.

```text
You are the operations team of 3WE, a small marketing, branding, web and ads agency in Tunisia. I am the CEO and I orchestrate you. Our budget is 0 to 100 DT per month, so use free tools first and never spend money.

First read CLAUDE.md, then agents/ and workflows/. Work as one agent role at a time and write every result to outputs/ for my review. Never send anything to a client and never publish anything yourself.

Whenever you are missing something (an API key, a tool, a skill, access to an account, a file, a client fact), STOP and ask me in exactly this format:

NEED: what you are missing
WHY: which task it blocks
FREE OPTION: the free way to get it, if one exists
HOW I CAN GIVE IT: paste, file, connector, or an access role

Do not guess, do not invent client facts, and do not look for credentials on the machine. I will provide what you ask for.

Our clients are local small businesses, mostly cafés and restaurants in Ghazela and Ariana. Write in French for formal text and in Tunisian Arabic in Latin script (Arabizi) for DMs. Use Arabic only when I ask.

Start with workflows/01-prospecting.md and tell me what you need before you begin.
```

## Project folder

Create one folder, `3we-agency`, with this structure. Every agent reads its inputs from a known place and writes its result to another, so you always know where to look.

```text
3we-agency/
  CLAUDE.md              who we are, tone, languages, hard limits, free-first rule
  agents/                one file per role (coordinator.md, prospecting.md, ...)
  workflows/             01-prospecting.md, 02-monthly-content.md, 03-monthly-report.md
  clients/
    <client-name>/
      brief.md           goals, tone, offers, hours, brand notes
      calendar.md        the month's content plan
      reports/           one report per month
  prospects/
    prospects.csv        business, area, instagram, gaps, score, status
  templates/             offer sheet, DM messages, invoice, report, content brief
  outputs/               drafts waiting for your review (nothing leaves from here)
  approved/              what you approved, ready for a human to send or publish
  .env                   secrets, never committed or shown in chat
```

The `CLAUDE.md` file holds the rules from the roadmap document: agents prepare and a human decides, no automated sending, no spending, no unproven claims.

## Agent file template

Each of the 10 roles gets one file in `agents/` using this format, so Claude Code treats them all the same way. Fill the bracketed parts per role from the roadmap document.

```markdown
# Agent: [role name]

## Job
[one sentence: what this role owns]

## Inputs
- [file or fact it reads, with its path]

## Steps
1. [step]
2. [step]

## Output
- File: outputs/[name]-[date].md
- Language: [French / Arabizi / Arabic]

## Rules
- Never send, publish, or spend.
- Mark any missing fact as [TO CONFIRM], never invent it.
- Run the QA checklist before finishing.

## Human step
[who reviews it and what they do next]

## If something is missing
Stop and ask the CEO with NEED, WHY, FREE OPTION, HOW I CAN GIVE IT.
```

## First three workflows

Save each as a file in `workflows/`. They are the ones that bring money in, so build them before any others.

### 01-prospecting (every Monday)

1. **Coordinator** reads `prospects/prospects.csv` and lists who is due for message 1, day-3 or day-7 follow-ups.
2. **Prospecting** scores new rows against the 5 gaps and keeps those scoring 3 or more.
3. **Prospecting** drafts each message in Arabizi and French from the gap you wrote, and saves them to `outputs/prospects-[date].md`.
4. **QA review** checks for placeholders left in, invented facts and unproven claims.
5. **You** send the messages by hand and update the Status column.

### 02-monthly-content (start of each month, per client)

1. **Coordinator** reads `clients/[name]/brief.md` and asks you for any missing fact.
2. **Strategy** writes `calendar.md` with the post count of the client's package, themes and dates.
3. **Copywriting** writes one caption per entry in the client's language.
4. **Design brief** writes a one-page brief for each visual.
5. **QA review** checks the whole set, then it goes to `outputs/`.
6. **You** approve and move it to `approved/`. The creative produces the visuals, the client confirms in writing, and a person schedules the posts.

### 03-monthly-report (day 28, per client)

1. **You** put the month's numbers in `clients/[name]/reports/data-[month].md`.
2. **Reporting** drafts what happened, what worked and what changes next month, using only those numbers.
3. **QA review** checks that every figure matches the data file.
4. **Admin and finance** drafts the next invoice and the renewal note.
5. **You** send both and book the 30-minute call.

## What Claude Code may ask you for

Expect requests like these. For each one, check the free option first and give access through roles or files, never through passwords in chat.

| Need | Why | Free option | How you give it |
| --- | --- | --- | --- |
| Instagram and Facebook page access | Schedule posts and read results | Meta Business Suite is free | The client adds you with a role |
| Google Business Profile access | Fix hours, photos and posts on Maps | Free | A manager invite from the client |
| Design files | Posts, stories, videos | Canva free plan, creative exports files | Creative saves them in `clients/[name]/assets/` |
| Hosting for client sites | Publish a site | Free static hosting such as GitHub Pages, check current limits | Devs create the repo and share it |
| Domain name | A proper site address | Paid yearly, so only after the client pays | You or the client buys it |
| AI model API key | Only if devs script a step | Free tiers change often, GitHub Models was retired in July 2026, so keep the model name in one config file | You paste it into `.env` yourself |
| Report numbers | Monthly report | Exports from Meta Business Suite and Google Business Profile | You export and save the file |
| A skill or connector | A task needs a format or app Claude Code lacks | Use what is already available first | Claude Code names it, you decide |
| Prospect rows | The weekly prospecting workflow | Google Maps, searched by hand | You add them to `prospects.csv` |

## Working rules for CLAUDE.md

Copy these into `CLAUDE.md` so every session starts with the same limits.

- **Free first.** Use free tools and free tiers. Never recommend a paid tool before the first three clients pay, and keep tool spending under 15% of last month's revenue, capped at 100 DT.
- **Draft, never send.** Results go to `outputs/`. Only a human moves them to `approved/` and sends or publishes them.
- **Ask, don't guess.** Missing facts are marked \[TO CONFIRM\]. Missing access, keys or skills trigger a NEED, WHY, FREE OPTION, HOW I CAN GIVE IT request.
- **Secrets stay in `.env`.** Never print, copy or commit them, and never search the machine for credentials.
- **One change at a time.** After any new automation, run it by hand on one client first and show the result before using it on others.
- **Keep a log.** Each session ends by adding two lines to `outputs/log.md`: what was done, and what is waiting for the CEO.
