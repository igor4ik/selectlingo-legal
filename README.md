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
- Effective date / last updated: **August 29, 2026**

## Canonical public URLs

- Legal site: `https://igor4ik.github.io/selectlingo-legal/`
- Privacy Policy: `https://igor4ik.github.io/selectlingo-legal/privacy/`
- Terms of Use: `https://igor4ik.github.io/selectlingo-legal/terms/`

---

## One remaining non-owner placeholder

Privacy Policy, Section 13 ("International users"), still contains:

```text
[PLACEHOLDER — legal review recommended before broader or commercial launch,
particularly if SelectLingo will be marketed into jurisdictions with specific
statutory privacy requirements.]
```

This is an advisory note recommending a jurisdiction-by-jurisdiction legal
compliance review (e.g., GDPR, U.S. state privacy laws) — it is not a value
that can be filled from the owner information supplied (name, contact,
governing law, age, effective date). Resolving it requires an actual legal
review decision, not a data substitution, so it has intentionally been left
in place in both the Markdown source and the generated HTML rather than
invented or silently removed.

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

## Required SelectLingo follow-up (separate prompt, after publishing)

Once the finalized site above has actually been pushed to the live
`selectlingo-legal` GitHub Pages repository and verified at
`https://igor4ik.github.io/selectlingo-legal/privacy/`, a small follow-up
change is needed in the SelectLingo extension source to set:

```ts
const PRIVACY_POLICY_URL = "";
```

to that real, live URL. Do not set this now — that update belongs to a
separate follow-up prompt (Prompt 062B), only after the live page is
verified.
