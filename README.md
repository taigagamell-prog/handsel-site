# handsel-site

Static marketing site for Handsel. Verified Scope 3 Category 7 employee
commuting data for US employers.

Three pages, one stylesheet, no framework, no build step.

## Run locally

Any static server works. With Python installed:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000

## Deploy

Vercel, connected to this repo. Push to `main` and it deploys.

Project settings: framework preset **Other**, build command **empty**, output
directory **empty**.

## Before launch

- [ ] Formspree form ID pasted into `index.html` (replace `REPLACE_WITH_FORM_ID`)
- [ ] Legal entity name and registered address filled in `privacy.html`
- [ ] Reviewer callout removed from `privacy.html`
- [ ] `hello@handseldata.com` mailbox live and receiving
- [ ] Domain pointed, Cloudflare records set to DNS only (grey cloud)
- [ ] Form submission tested from a phone on cellular
- [ ] Privacy notice reviewed by counsel

## Editing

Read `CLAUDE.md` first. It covers the positioning, the regulatory facts that
must not be misstated, the banned claims, the voice rules and the colour token
that is reserved.
