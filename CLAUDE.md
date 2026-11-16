# CLAUDE.md — a module of the Interactive Pathology Teaching Platform

This repository is one module (a single `index.html`): **Granulomatous and Parasitic Diseases** (module key `granuloma`,
storage prefix `gp_`, build `1.2`). Built 2026-11-04 from the user's own syllabus "Chapter 6: Granulomatous and Parasitic
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
- Build 1.1 (2026-11-15): section **s0103** "Classification and types of granulomatous inflammation" (the user's classification diagram, redrawn as the vector figure `fig1_class`) sits SECOND in topic t01, so it is shown as 1.2 and the old s0102 (Causes, Table 6.1) as 1.3 — IDs unchanged. Go live follows docs/REBUILD.md.
- Delivered to the user directly, never committed: `granuloma-assessment-bank.json` (🔒 91 items `aqb_gp_NNN[letter]` from the
  user's MCQ book Q173–293 with the book's answer key), `granuloma-practical-pictures.json` (26 syllabus photographs
  `gp-prac-01…26` → t14 sections), `granuloma-practical-cases.json` (13 practicals `gp-pr-01…13`), `granuloma-spotter-questions.json`
  (52, `gp-sp-NN`) and `granuloma-ospe-stations.json` (14, `gp-os-NN`).
- 🎓 Viva Examination (2026-11-15, patch `viva`): the bank `granuloma-viva-bank.json` (75 questions `viva_gp_tNN_NN`, 5 marks each, ≥ 5 per topic,
  18 picture questions) is delivered to the user and imported in ✏️ Edit master draft → 🎓 Viva → ⬆ Import viva bank — never committed.
- **Picture and practical rebuild (2026-11-16, build 1.2 — includes the other chat's pending 1.1 section s0103):** 22 blurred syllabus scans
  taken out of their topic sections (diagrams 6.1/6.4/6.8/6.9/6.22/6.31 and photos 6.10/6.15/6.27 kept; text references to the removed
  figures deleted), atlas gp-img-004/005 hidden; t14 = 14 cases (s1402 + s1412–s1422) and galleries s1423–s1426; s1403–s1411 retired
  (intestinal TB, cysticercosis, candidiasis, aspergillosis, rhinosporidiosis deleted by the user, with q169–q173, q175; q178/q179 edited).
  Delivered (never committed): 4 picture files (`gp-pic-NNN` topics 84, `gp-prac2-NNN` practical 156, from the user's ExpertPath/WebPath ZIP +
  8 old syllabus pictures), 14 practical cases `gp-pr2-NN` (one merged question group; replaces the 13 old), Spotter 91 `gp-sp2-NNN`
  (38 hardest in Practice), OSPE 18 `gp-os2-NN`, 🔒 bank 53 `aqb_gpp_*`.
- Test changes on the real page with the platform repo's e2e test "Granulomatous and Parasitic Diseases module (granuloma)"
  (`GP_CONTENT_KEY` in the environment) and `node test/module-smoke/smoke.js` before pushing.
