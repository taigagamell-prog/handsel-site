# Handsel site: working notes for Claude Code

Read this before editing anything in this repo.

## What this is

A three page static marketing site for Handsel. No framework, no build step, no
dependencies. Vercel serves the files as they are. Keep it that way unless there
is a reason that survives being said out loud.

## What Handsel sells

Verified employee commuting data for **Scope 3 Category 7**, sold to US
mid-market employers preparing for California SB 253 reporting.

The offer today is a fixed-scope services engagement at $15,000 to $18,000: a
Category 7 report, the calculation workbook that produced it, and the evidence
file underneath. It is a services business, not a product. There is no app, no
signup and no free tier, and the site must not imply any of those exist.

The buyer is a sustainability lead, ESG director, controller or CFO at a US
employer. They are buying **defensibility in front of an assurance provider**,
not enthusiasm about climate. Write for someone who will forward the page to
their auditor.

## Out of scope: do not put these on the site

These are real parts of the longer plan but are deliberately absent from public
material right now. Do not reintroduce them:

- The UK deposit return scheme / producer verification line. Cut.
- The rewards marketplace, points ledger, serialised codes and redemption. Parked.
- Any subscription pricing or platform product. Not yet real.
- Anything about funding, investors or a round. Handsel is bootstrapped and
  there is no raise.
- Team pages, headcount, or "we" framing that implies a company larger than it
  is. It is a solo operation. Understatement is safer than invention.

## Facts to keep straight

Getting the regulation wrong is the single worst error available here, because
the entire pitch is that Handsel is careful. Verify before changing any of this.

- California **SB 253** is law. CARB has adopted initial regulations covering
  Scope 1 and Scope 2 reporting.
- **Scope 3 is still pre-rulemaking as of August 2026.** CARB has published
  options and taken comment. There is no final Scope 3 rule. Never write as
  though there is.
- Scope 3 reporting is expected to begin in **2027**, with a November 10
  deadline in the reporting year, covering the preceding fiscal year. State this
  conditionally, not as settled fact.
- CARB is weighing three phase-in approaches: no phase-in (all relevant
  categories), a sectoral phase-in, and a category phase-in limited to five
  categories. The five in that option are Category 1 (purchased goods and
  services), Category 3 (fuel and energy-related activities), Category 5
  (waste), Category 6 (business travel) and **Category 7 (employee commuting)**.
- Accurate framing: Category 7 is in scope under two of the three options. Do
  not upgrade that to "required".

### Banned claims

- **Never cite the "48% of employers" survey statistic or the "WRI 88%" figure.**
  Both are unverifiable. They have been removed once already.
- Never claim compliance with a final Scope 3 rule.
- Never claim a client, a case study, a logo or a testimonial that does not
  exist.
- Never state a specific market size or growth figure without a live source in
  the same edit.

## The argument that actually works

Not "the rules are coming". The rules might change. The durable argument is
that **commuting data cannot be reconstructed after the fact**. There is no
invoice trail and no supplier to ask. If the first reports cover FY2026, that
data is being generated now, and a survey fielded in 2027 asking staff to recall
2026 is a guess. That argument holds whichever way CARB rules. Lead with it.

## Voice

- **Never use em dashes.** Not in copy, not in comments, not anywhere. Use a
  period, a comma, a colon or a rewrite.
- Short declarative sentences. Concrete nouns. Opinionated.
- No hedging, no "in today's landscape", no "seamless", "leverage", "empower",
  "unlock", "robust", "cutting edge", "we're excited to". If a sentence could
  appear on any B2B site, delete it.
- Admit uncertainty where it exists. The regulatory status section is a trust
  asset, not a liability. Do not sand it down.
- Understate. This is an audit-adjacent buyer. Enthusiasm reads as risk.

## Brand

Ink-led. Restrained. Should read like a professional services firm rather than
a climate startup.

| Token | Value | Use |
|---|---|---|
| `--ink` | `#10151a` | Text, buttons, rules |
| `--ink-2` | `#37424d` | Body copy in prose |
| `--ink-muted` | `#5d6771` | Secondary text, nav |
| `--paper` | `#fcfcfa` | Page background |
| `--surface` | `#f4f4f0` | Callouts |
| `--rule` | `#e3e3dd` | Borders |
| `--sealed` | `#1b6b47` | **Reserved. See below.** |

**Green is reserved.** `--sealed` marks the verified or sealed state and nothing
else. It is currently used only on the "aggregates of ten or more" indicator. Do
not use it for links, buttons, headings, hovers, icons or decoration. If you
find yourself wanting green for emphasis, use ink.

Type is Inter, weights 400, 500 and 600 only. No display face, no italics for
emphasis, no all-caps except the mono eyebrow labels.

## Files

```
index.html         Landing page. Hero, timing argument, deliverable,
                   process, privacy floor, regulatory status, contact form.
methodology.html   The credibility asset. Written to be handed to an
                   assurance provider unedited. Versioned in the eyebrow.
privacy.html       Two parts: site visitors, and survey respondents.
                   Contains placeholders that must be filled before launch.
styles.css         Shared. Single source of truth for the design system.
vercel.json        Clean URLs and security headers.
favicon.svg        Ink square, letterform H.
robots.txt         Privacy page excluded from indexing.
sitemap.xml        Update if a page is added.
```

## Before this goes live

1. Replace `REPLACE_WITH_FORM_ID` in `index.html` with the real Formspree ID.
2. Fill `[LEGAL ENTITY NAME]` and `[REGISTERED ADDRESS]` in `privacy.html`, and
   delete the yellow reviewer callout above them.
3. Confirm `hello@handseldata.com` actually exists and receives mail before
   linking it anywhere public.
4. Have the privacy notice reviewed by counsel before the first engagement. It
   is drafted, not lawyered.
5. Submit the form from a phone on cellular and confirm delivery.

## Deploy

Push to `main`. Vercel builds and deploys automatically. There is no build
command and no output directory: framework preset is "Other" and both fields
are blank.

DNS lives at Cloudflare. Vercel records must be set to **DNS only**, the grey
cloud, not proxied. Proxying Vercel through Cloudflare causes redirect loops and
certificate failures.

## Open questions

- Domain is `handseldata.com`. The name Handsel has a live intent-to-use
  application at the USPTO by another party in class 35 (serial 99551033,
  Notice of Allowance July 2026, Statement of Use due around January 2027). If
  that application matures, a rename may be needed. Backup name is Prova, not
  yet cleared. Do not invest heavily in name-specific assets before then.
- No legal entity is confirmed yet. The privacy notice and any SOW depend on it.
