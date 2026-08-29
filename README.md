# SelectLingo Legal Site (GitHub Pages export)

This directory is an **exportable static site**, generated for the future
`selectlingo-legal` GitHub Pages repository. It is not part of the
SelectLingo extension build and is not served by the extension itself.

> **DO NOT PUBLISH until all legal placeholders are filled.**

The Privacy Policy and Terms of Use in this site are converted, without
substantive change, from:

- `docs/privacy/PRIVACY_POLICY_DRAFT.md`
- `docs/legal/TERMS_OF_USE_DRAFT.md`

Those Markdown files remain the legal source of truth. If you need to change
legal wording, edit the Markdown drafts first (with legal review), then
regenerate these HTML pages to match.

---

## Placeholder checklist (must be resolved before publishing)

The following placeholders currently appear in the generated pages and must
be replaced with real values before this site is made public:

- [ ] Developer/Company legal name (`[PLACEHOLDER — Developer/Company Name]`)
- [ ] Privacy contact email (`[PLACEHOLDER — Privacy Contact Email]`)
- [ ] Terms contact email (`[PLACEHOLDER — Contact Email]`)
- [ ] Support email, if one is used (not currently present in the drafts — add only if a real support address exists)
- [ ] Effective date, both pages (`[PLACEHOLDER — effective date]`)
- [ ] Last updated date, Privacy Policy (`[PLACEHOLDER — date of last update]`)
- [ ] Governing law / jurisdiction, Terms Section 18 (`[PLACEHOLDER — Governing Law / Jurisdiction]`)
- [ ] Minimum age / eligibility policy, Terms Section 3 (`[PLACEHOLDER — Minimum Age / Eligibility Policy]`)
- [ ] Children's privacy / audience policy confirmation, Privacy Policy Section 12
- [ ] International users / jurisdictional legal review, Privacy Policy Section 13
- [ ] Final published Privacy Policy URL (`[PLACEHOLDER — Website / Privacy Policy URL]`)
- [ ] Final published Terms of Use URL (`[PLACEHOLDER — Website / Terms of Use URL]`)

Every placeholder above appears verbatim in the generated HTML so it stays
visible until it is deliberately resolved — do not invent values to make
them disappear.

---

## Why `.nojekyll` is included

GitHub Pages runs content through Jekyll by default. This site has no Jekyll
dependency, uses a directory (`privacy/`, `terms/`) whose name starts with a
non-underscore character (not an issue here) but, more importantly, contains
no Liquid templating and should be served exactly as authored. The empty
`.nojekyll` file at the repository root tells GitHub Pages to skip the
Jekyll build step and serve the static files as-is, which is the correct and
simplest setting for a plain static site like this one.

---

## Expected GitHub Pages repository structure

Copy the contents of `docs/legal-site/` (not the `legal-site` folder itself)
into the root of a separate repository named `selectlingo-legal`:

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

1. Push the files to the `main` branch.
2. Go to **Settings → Pages → Build and deployment**.
3. Set **Source** to `Deploy from a branch`.
4. Set **Branch** to `main` and folder to `/ (root)`.
5. Wait for GitHub to publish the site and provide the URL.
6. Verify `https://<github-user>.github.io/selectlingo-legal/`,
   `.../privacy/`, and `.../terms/` all load correctly.

This prompt does not create the repository, push code, or configure GitHub
Pages remotely — that remains a manual step for the user.

---

## Required SelectLingo follow-up (separate prompt, after publishing)

Once the real Privacy Policy URL exists (i.e., after the placeholders above
are filled and the site is actually published), a small follow-up change is
needed in the SelectLingo extension source to set:

```ts
const PRIVACY_POLICY_URL = "";
```

to the real, live `.../privacy/` URL. Do not set this to a placeholder or
guessed URL — it must only be updated once the public page genuinely exists,
and that update should happen in its own prompt/change, not as part of this
static-site generation task.
