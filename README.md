# ECCN Preliminary Classification

A single-file, fully self-contained web tool that walks an exporter through the
U.S. Commerce Control List (CCL) **Order of Review** (Supp. 4 to Pt. 774) to a
preliminary **ECCN / EAR99 / ITAR** determination. It has four modes — a guided
wizard, CCL search, a §772.1 "specially designed" test, and a session register.

No build step, no external dependencies, no network requests: everything —
including the `.xlsx` export — runs in the browser from one HTML file.

**Live site:** https://tunlezah.github.io/eccn/

> ⚠️ Decision support only — not a BIS ruling and not legal advice. The index is
> a curated, dated navigational aid; confirm every result against the live CCL
> before relying on it. Volatile entries carry an in-tool caveat note.

**Accuracy baseline:** the workflow and every index row were audited against the
eCFR text of the EAR (15 CFR 730–774) and ITAR (22 CFR 120–130) current as of
**12 Aug 2026**, and the index's reason-for-control codes were re-derived
programmatically from that text — see [`AUDIT.md`](AUDIT.md) for the findings
and method. ITAR/NRC cross-reference stubs are flagged as jurisdiction
redirects, not EAR results. The firearms/suppressors IFR (91 FR 46252) takes
effect 20 Nov 2026 and will require a refresh.

## Hosting

Hosted on **GitHub Pages** via `.github/workflows/pages.yml`, which publishes
`navigator.html` as the site root (`index.html`) on every push to `main` (and
the working branch).

**One-time setup (repo admin):** repository **Settings → Pages → Build and
deployment → Source: GitHub Actions**. The GitHub Actions token is not permitted
to enable Pages by itself, so this switch must be flipped once; after that,
every push deploys automatically.

## Local use

Open `navigator.html` directly in a browser — it works offline with no server.
