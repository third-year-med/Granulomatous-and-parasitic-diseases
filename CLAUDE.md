# CLAUDE.md — a module of the Interactive Pathology Teaching Platform

This repository is one module (a single `index.html`): **Granulomatous and Parasitic Diseases** (module key `granuloma`,
storage prefix `gp_`, build `1.3`). Built 2026-11-04 from the user's own syllabus "Chapter 6: Granulomatous and Parasitic
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
- Build 1.3 (2026-11-20, live): the user's lecture-note pages 49–56 added to topic 4 and the topic SPLIT — t04 "Tuberculosis — Spread and Primary Tuberculosis" (s0401, s0402, s0403, s0405), new **t15 Secondary Tuberculosis** (s0404, s0406–s0408), **t16 Intestinal Tuberculosis** (s0409, s0410), **t17 Tuberculosis of the Vertebral Spines (Pott's Disease)** (s0411, s0412); t15–t17 sit right after t04 in the topic order (t14 Practical stays last). Cancelled by the user (red marks): the granuloma drawings p. 49, the primary-complex box items 1–3, "Methods of spread" p. 50, "Tuberculous peritonitis" p. 56. Also: questions q182–q211 (t15–t17 + t04 additions), 5 glossary terms, clinical cases c11–c14, atlas pictures gp-img-015…018 (+ existing pictures attached to s0405/s0406/s0408); the learning-path units (UX_UNITS u2, UX_FLOW, UX_EXPECT_TOPIC) list t15–t17. Go live follows docs/REBUILD.md.
- Delivered to the user directly, never committed: `granuloma-assessment-bank.json` (🔒 91 items `aqb_gp_NNN[letter]` from the
  user's MCQ book Q173–293 with the book's answer key), `granuloma-practical-pictures.json` (26 syllabus photographs
  `gp-prac-01…26` → t14 sections), `granuloma-practical-cases.json` (13 practicals `gp-pr-01…13`), `granuloma-spotter-questions.json`
  (52, `gp-sp-NN`) and `granuloma-ospe-stations.json` (14, `gp-os-NN`).
- Delivered 2026-11-20 (never committed): `granuloma-assessment-bank.json` v2 (103 items: +13 from the MCQ book now covered by the lecture notes — Q191, 193–196, 199, 247, 249, 250, 252, 253, 258, 259; Q245/246 moved to t15) and `granuloma-viva-bank-additions.json` (21 questions `viva_gp_t04_n01–03`, `viva_gp_t15_01–06`, `viva_gp_t16_01–06`, `viva_gp_t17_01–06`, 7 with pictures).
- 🎓 Viva Examination (2026-11-15, patch `viva`): the bank `granuloma-viva-bank.json` (75 questions `viva_gp_tNN_NN`, 5 marks each, ≥ 5 per topic,
  18 picture questions) is delivered to the user and imported in ✏️ Edit master draft → 🎓 Viva → ⬆ Import viva bank — never committed.
- **Picture and practical rebuild (2026-11-16, build 1.2 — includes the other chat's pending 1.1 section s0103):** 22 blurred syllabus scans
  taken out of their topic sections (diagrams 6.1/6.4/6.8/6.9/6.22/6.31 and photos 6.10/6.15/6.27 kept; text references to the removed
  figures deleted), atlas gp-img-004/005 hidden; t14 = 14 cases (s1402 + s1412–s1422) and galleries s1423–s1426; s1403–s1411 retired
  (intestinal TB, cysticercosis, candidiasis, aspergillosis, rhinosporidiosis deleted by the user, with q169–q173, q175; q178/q179 edited).
  Delivered (never committed): 4 picture files (`gp-pic-NNN` topics 84, `gp-prac2-NNN` practical 156, from the user's ExpertPath/WebPath ZIP +
  8 old syllabus pictures), 14 practical cases `gp-pr2-NN` (one merged question group; replaces the 13 old), Spotter 91 `gp-sp2-NNN`
  (38 hardest in Practice), OSPE 18 `gp-os2-NN`, 🔒 bank 53 `aqb_gpp_*`.
- **Practical pictures in the topics (2026-11-16, platform rule HANDBOOK §4.4):** all 156 practical pictures also added to their Learn
  sections as `gp-tp-NNN` (same number as `gp-prac2-NNN`, caption without "Case N —"), delivered as `granuloma-pictures-topics-3.json`
  (topics 2–9, 85) and `-topics-4.json` (topics 10–13, 71) — never committed; rehearsed on the real page (156 added).
  Then (same day, user: one picture per finding) `granuloma-pictures-remove-repeats.json` removes 92 repeats (gp-pic and gp-tp) from 31
  sections — 148 imported topic pictures stay; syllabus figures and atlas untouched; rehearsed (240 → 148).
- Test changes on the real page with the platform repo's e2e test "Granulomatous and Parasitic Diseases module (granuloma)"
  (`GP_CONTENT_KEY` in the environment) and `node test/module-smoke/smoke.js` before pushing.
