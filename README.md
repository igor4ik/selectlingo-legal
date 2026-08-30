# SelectLingo Legal Site (GitHub Pages export)

This directory is an **exportable static site** for the `selectlingo-legal`
GitHub Pages repository. It is not part of the SelectLingo extension build
and is not served by the extension itself.

Owner/legal placeholders have been filled.

Before publishing or updating GitHub Pages:

- verify the Privacy Policy and Terms HTML match their Markdown source documents;
- verify the public URLs;
- push only after manual review.

The Privacy Policy and Terms of Use in this site are converted, without
substantive change, from:

- `docs/privacy/PRIVACY_POLICY_DRAFT.md`
- `docs/legal/TERMS_OF_USE_DRAFT.md`

Those Markdown files remain the legal source of truth. If you need to change
legal wording, edit the Markdown drafts first (with legal review), then
regenerate these HTML pages to match.

---

## Final owner values applied

- Developer/company legal name: **George Poliak**
- Privacy/contact email: **george.poliak83@gmail.com**
- Support email: **george.poliak83@gmail.com**
- Governing law/jurisdiction: laws of the State of Israel; courts of
  competent jurisdiction in Israel
- Minimum age / intended audience: users aged 13 and older; users under 18
  should use SelectLingo with permission from a parent or legal guardian
- Effective date / last updated:
  - Privacy Policy: **August 30, 2026** — Prompt 065A added the pronunciation
    (Listen) disclosure, the GDPR information block in Section 13, and the
    explicit vocabulary retention rule.
  - Terms of Use: **August 29, 2026**, unchanged. Prompt 065A corrected one
    factual clause in Section 5 — pronunciation is produced by the browser's
    speech synthesis, not by Translator/LanguageDetector. That corrects a
    description; it changes no one's rights or obligations, so the effective
    date was deliberately left alone. Bump it if you would rather it moved.

## Canonical public URLs

- Legal site: `https://igor4ik.github.io/selectlingo-legal/`
- Privacy Policy: `https://igor4ik.github.io/selectlingo-legal/privacy/`
- Terms of Use: `https://igor4ik.github.io/selectlingo-legal/terms/`

---

## No placeholders remain

An earlier revision of this file recorded a `[PLACEHOLDER]` in Privacy Policy
Section 13 ("International users"). That placeholder was replaced with final
wording when Section 13 was rewritten for international users, and the note is
kept here only to explain why it is gone.

Verified during the Prompt 064 release audit: no `[PLACEHOLDER]` text remains in
`docs/privacy/PRIVACY_POLICY_DRAFT.md`, `docs/legal/TERMS_OF_USE_DRAFT.md`, or
any file in this directory, and the live pages at
`https://igor4ik.github.io/selectlingo-legal/privacy/` and `.../terms/` were
fetched and confirmed placeholder-free.

The underlying recommendation still stands, and is now tracked where it belongs
rather than as placeholder text in a published legal document: a
jurisdiction-by-jurisdiction compliance review (GDPR, U.S. state privacy laws)
remains outstanding, and a dedicated **GDPR readiness/compliance audit is the
first task after the Closed Beta phase**. Section 13's current wording makes no
compliance claim that would pre-empt it.

---

## Why `.nojekyll` is included

GitHub Pages runs content through Jekyll by default. This site has no Jekyll
dependency and no Liquid templating, and should be served exactly as
authored. The empty `.nojekyll` file at the repository root tells GitHub
Pages to skip the Jekyll build step and serve the static files as-is.

---

## Expected GitHub Pages repository structure

Copy the contents of `docs/legal-site/` (not the `legal-site` folder itself)
into the root of the separate `selectlingo-legal` repository:

```text
selectlingo-legal/
├── .nojekyll
├── README.md
├── index.html
├── privacy/
│   └── index.html
└── terms/
    └── index.html
```

Then, in that repository:

1. Copy/update the files above in the `selectlingo-legal` repository.
2. Commit the changes.
3. Push to `main`.
4. Wait for GitHub Pages to redeploy.
5. Open `https://igor4ik.github.io/selectlingo-legal/privacy/` and
   `https://igor4ik.github.io/selectlingo-legal/terms/` and confirm they
   render correctly and no unintended placeholders remain.

This prompt does not push or publish anything — the files above have only
been updated inside the main SelectLingo repository's `docs/legal-site/`
working copy.

---

## SelectLingo follow-up — done

The site has been published and the extension now links to the live pages:

- `src/onboarding/onboarding.ts` — `PRIVACY_POLICY_URL`, shown in the first-run
  privacy disclosure;
- `src/options/options.html` — the Privacy Policy and Terms of Use links in
  Settings → About.

If a canonical URL ever changes, all three references must be updated together.
