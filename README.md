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

## Hosting

Hosted on **GitHub Pages** via `.github/workflows/pages.yml`, which publishes
`navigator.html` as the site root (`index.html`) on every push to `main`.

If the workflow cannot self-enable Pages (org/repo policy), enable it once under
repository **Settings → Pages → Build and deployment → Source: GitHub Actions**,
then re-run the workflow.

## Local use

Open `navigator.html` directly in a browser — it works offline with no server.
