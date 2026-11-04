# CLAUDE.md — a module of the Interactive Pathology Teaching Platform

This repository is one module (a single `index.html`): **Granulomatous and Parasitic Diseases** (module key `granuloma`,
storage prefix `gp_`, build `1.0`). Built 2026-11-04 from the user's own syllabus "Chapter 6: Granulomatous and Parasitic
Diseases" (pp. 116–153) **as it is — NOT condensed** (like Inflammation (New) and Neoplasia (New)), plus the practical book
Exercises 14–17, with the app code of `third-year-med/neoplasia-new`. Served at
`https://third-year-med.github.io/Granulomatous-and-parasitic-diseases/` (the repository name has a capital G).

The platform's decisions, the checklist for modules, the deployment steps, the testing workflow and the lessons learned are
in the platform repository: `third-year-med/Interactive-pathology-platform` → `CLAUDE.md` and `docs/HANDBOOK.md`
(rebuilds: `docs/REBUILD.md`).

- The course data in `index.html` is encrypted with this module's OWN content key, which lives only in the user's Code.gs
  (`CONTENT_KEYS.granuloma`; env `GP_CONTENT_KEY` in a session). Never commit a key or an unencrypted copy of the course.
- The `<script id="platform-nav">` block is maintained in the platform repo (`modules/platform-nav.js`) and written here
  with `tools/module-release.js refresh` — do not edit it by hand.
- Stable IDs: topics t01–t13 in the syllabus order (granuloma; TB organism; TB host response; TB spread and types; syphilis;
  leprosy; sarcoidosis; rhinoscleroma; actinomycosis and mycetoma; schistosomiasis — bladder; schistosomiasis — intestine,
  liver, spleen, lung; filariasis and toxoplasmosis; hydatid) + **t14 Practical Pathology** (s1401–s1411); sections sNNMM,
  questions q001–q181, cases c01–c10, syllabus figures `fig6_1`…`fig6_31` (embedded, credit "Course syllabus … p. N"),
  atlas pictures `gp-img-NNN` (Wikimedia Commons, licence per file). The practical topic is **t14** (the app code's two
  "How to answer a practical" references point at t14).
- Delivered to the user directly, never committed: `granuloma-assessment-bank.json` (🔒 91 items `aqb_gp_NNN[letter]` from the
  user's MCQ book Q173–293 with the book's answer key), `granuloma-practical-pictures.json` (26 syllabus photographs
  `gp-prac-01…26` → t14 sections), `granuloma-practical-cases.json` (13 practicals `gp-pr-01…13`), `granuloma-spotter-questions.json`
  (52, `gp-sp-NN`) and `granuloma-ospe-stations.json` (14, `gp-os-NN`).
- Test changes on the real page with the platform repo's e2e test "Granulomatous and Parasitic Diseases module (granuloma)"
  (`GP_CONTENT_KEY` in the environment) and `node test/module-smoke/smoke.js` before pushing.
