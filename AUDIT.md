# Legal-Accuracy Audit — `navigator.html` (ECCN Preliminary Classification)

**Audit date:** 2026-08-17
**Baseline:** current eCFR text of 15 CFR parts 732/738/740/742/744/746/748/754/772/774 and 22 CFR parts 120/121/122 as of 2026-08-12/13 (newer than the tool's claimed rule date of 24 Jul 2026), plus Federal Register rule history verified by citation.
**Method:** 14 parallel research passes — one per subject area (Order of Review, "specially designed," CCL structure/definitions, ITAR gate, reasons-for-control map, rule history) and one per CCL category for the embedded ECCN index. Every finding below is backed by a side-by-side quote of the tool and the regulation; conflicting agent conclusions were re-verified against primary sources before inclusion.

---

## Executive summary

The tool's **workflow skeleton and citations are real and largely faithful** — Supp. No. 4 to Part 774 genuinely has six steps, the "trump" precedence language is quoted almost verbatim, §732.3(b) self-classification, the DS-4076 CJ route, the 21 USML categories, the Country Chart column names, CCATS/SNAP-R, and the ".z added Oct 2023" / "3B090 removed Oct 2023" rule dates all check out.

The problems cluster into five themes, in descending order of danger:

1. **Jurisdictional traps (ITAR-relevant).** ~20 index rows present ECCNs that are actually *ITAR cross-reference stubs* — one-line CCL entries reading "These items are 'subject to the ITAR.' See 22 CFR parts 120 through 130" with **no EAR license requirements at all** — as live EAR entries with fabricated reason-for-control codes. The entire MTCR rocket-propulsion chain (9A005–9A011, 9A104–9A119 in part), 1A102, 0D001/0E001, and 7A106/7A115/7A117 are affected. A user relying on these rows would run an EAR analysis on USML Category IV/XIX articles.
2. **A stale index baseline.** Of ~355 index rows, roughly **200 (~57%) carry at least one substantive error**: ~19 rows cite ECCNs that no longer exist (ten Category 0 nuclear entries left the CCL for NRC jurisdiction in **October 2013**; 1C352, 1C012, 0A918, 0A987, 0B986, 0C003, 3A993, 4D003 are gone), two headings are swapped (8A609↔8A620), several headings describe the wrong commodity (1C990, 9A120, 2E301↔2E201, 2B008, 3D003), and there is a **systemic NS Column 1 → Column 2 error** across Categories 1, 2, 3, 6, 8 and 9 hardware entries (independently verified against the raw eCFR text). Missing reasons-for-control are pervasive (MT, NP, CC, UN, RS-on-.z, and **every SL control**).
3. **Order-of-Review deviations.** The wizard's "conclude EAR99" flow requires exhausting only *one category + one product group of a partial index*, where Supp. No. 4 Step 6 requires the item not be described under "**any ECCN of any category of the CCL**." The §772.1 catch-and-release test is displaced out of Step 4 (where the regulation embeds it in the 600-series/9x515 *catch-all* determination), and the 600-series/9x515 screen is wrongly confined to the single category the user already picked.
4. **"Specially designed" structural error.** The tool offers all six §772.1(b) releases to *any* caught item. The (b) chapeau restricts releases to "a 'part,' 'component,' 'accessory,' 'attachment,' or 'software'" — an end item, equipment, system, or material caught under (a)(1) has **no release path**, but the tool will clear it on a (b)(5) "general purpose" answer. The (b)(3)/(b)(4) "another AT-only ECCN" restriction (Note to (b)(3)/(b)(4)) is also missing, and (a)(1) drops the USML branch of the definition.
5. **Definitional staleness.** The General Software Note summary states pre-2016 law (the current GSN is a License Exception TSU eligibility note, not a decontrol; its "public domain" branch is [Reserved] and lives at §734.3(b)(3)). The GTN summary imports public-domain/basic-research/patent carve-outs that belong to Part 734, not the GTN.

**What held up:** the six-step structure and all Supp. 4 step citations; the "trumps" language; §732.3(b); the ITAR stop page's DS-4076/DDTC routing; "21 categories"; all 16 Country Chart column shorthands; EI (§742.15), UN (§746.1(b)), CW (§742.18), SS (Part 754), SI (§742.14) cites; the 600-series and 9x515 definitions; the 0Y521 GOV-only claim; the garage-door-opener illustration; the (b)(2) fastener list; the contemporaneous-documentation notes on (b)(4)–(b)(6); the ".z added Oct 2023" and "3B090 removed Oct 2023" dates; the 4E091 hedge (see §6); BIS Interactive CCL and SNAP-R links.

---

## 1. Order of Review (Supp. No. 4 to Part 774) — wizard workflow

Regulatory baseline: Supp. No. 4 consists of an introductory paragraph (a) (USML/§734.3 scope), Steps 1–6 at (a)(1)–(a)(6), sub-steps 4.a/4.b at (a)(4)(i)–(ii), a Note to paragraph (a)(4), and "(b) [Reserved]". The tool's ".src" citations all map to real text.

| # | Sev | Finding |
|---|-----|---------|
| 1.1 | **HIGH** | **EAR99 conclusion scope.** Tool (line 1057, 1043, 1077) lets the user "conclude EAR99" after filtering one category + one product group of a curated partial index. Regulation (Step 6): *"If the item is not described under any ECCN of any category of the CCL, then the item is designated as EAR99."* Fix: require an attestation that the full CCL (all categories/groups, live text) was checked; rephrase the empty-state hint and the result card. |
| 1.2 | **HIGH** | **SD test displaced out of Step 4.** The regulation's Step 3 covers 600-series/9x515 paragraphs *"other than a 'catch-all' paragraph such as a '.x' paragraph"*; Step 4 then routes catch-alls through §772.1(a) (Step 4.a) and (b) (Step 4.b). The tool asks a bare yes/no at its 600-series gate and runs the SD test only afterwards, framed for ordinary ECCNs (step 5). A user can wrongly answer the 600-series question in either direction without ever running the catch-and-release test. |
| 1.3 | MED | **600-series/9x515 screen confined to one category.** Tool (lines 1004, 1388–1389) scopes the munitions-derived check to the already-picked category and even tells a Category-3 user to look for "9x515" entries there (9x515 exists only in Category 9). Regulation Step 3 is category-unqualified, and Step 2 contemplates plural candidate categories. |
| 1.4 | MED | **"Subject to the EAR" scope test truncated.** Supp. 4 para. (a) makes the USML an *example* of exclusive-jurisdiction exits and requires the item be "otherwise 'subject to the EAR'" (§734.3 — other agencies, published/publicly available exclusions). The tool asks only the USML question. |
| 1.5 | MED | **600-series stop page** repeats 1.2/1.3: no distinction between enumerated paragraphs and .x catch-alls (which require the §772.1 analysis before classification there). |
| 1.6 | LOW | Footer claim "asks the questions … in the order the regulation asks them" is overstated until 1.2–1.4 are fixed. |
| 1.7 | LOW | Step-5 explainer omits the Note to (a)(4): some ECCNs use "specially designed" as a **de-control** parameter, where one reviews only the (b) releases. |

Verified accurate: "six steps"; para. (a) USML-first framing incl. catch-alls; the literal "trump" sentence; Step 1/Step 2 characterizations; Step 5 "starting from the beginning of the product group"; the EAR99 residual-license warning (destination/party/end-use); §732.3(b) self-classification; eCFR links.

## 2. "Specially designed" (§772.1) — catch-and-release tool

| # | Sev | Finding |
|---|-----|---------|
| 2.1 | **HIGH** | **(b) releases offered to every caught item.** The (b) chapeau: *"A 'part,' 'component,' 'accessory,' 'attachment,' or 'software' that would be controlled by paragraph (a) is not 'specially designed' if it:"* — releases are available **only** to those five item types. The tool (lines 1285–1298) shows all six releases on any (a)(1)/(a)(2) "yes" and clears the item if any single release is "yes." An end item, equipment, system, or material caught under (a)(1) has no release path; the tool will wrongly clear it. Fix: gate Part 2 on item type (the wizard already collects it). |
| 2.2 | MED | **(b)(3)/(b)(4) AT-only self-reference missing.** Note to (b)(3)/(b)(4): the release criteria *"must be met by another ECCN controlled for AT-only reasons or an EAR99 item in addition to the AT-only ECCN being reviewed"* (the reg's own gasket/9A990 example fails (b)(3); the tool as written would release it). |
| 2.3 | MED | **(a)(1) drops the USML branch:** actual text reads "in the relevant ECCN **or U.S. Munitions List (USML) paragraph**" — material for 600-series/9x515 catch-alls controlling parts SD for defense articles. |
| 2.4 | MED | **Over-broad conclusion text** ("The item falls within the ECCN paragraph…"): SD is one parameter; the paragraph's other technical requirements (and "not elsewhere specified" conditions) must still be met, and some entries use SD to de-control. |
| 2.5 | LOW | (b)(4) narrows "not 'enumerated'" to "EAR99" (the reg's "e.g."); (b)(2) drops the "e.g." before the fastener examples; (b)(3) hint implies the *original* item loses "production" status when a changed-performance version is developed (only the new model is in "development"); step-5 "No" tile is a false dichotomy (entries can have parameters *and* SD language); "escape control" should be "not 'specially designed'" (the item may be enumerated elsewhere). |

Verified accurate: (a)(2) paraphrase (exact); "only one of these need be true"; (b)(1) CJ/CCATS-§748.3(e) framing; (b)(3) core test and the Form/Fit/Equivalent glosses; the contemporaneous-documentation requirement applied to exactly (b)(4)–(b)(6); the (b)(5) "type of commodity" gloss; (b)(6) (i)/(ii) structure; the garage-door-opener illustration (faithful to the Note to (a)(1)).

**For the ITAR-trained reviewer — §772.1 vs 22 CFR 120.41 in brief:** both share the (b) chapeau limitation (so ITAR instinct catches finding 2.1); ITAR has five releases (no analog to EAR (b)(6)); ITAR (b)(1) accepts only a CJ while the EAR adds the interagency-cleared CCATS route; EAR (b)(3)/(b)(4) add AT-only-ECCN pathways (and the "another AT-only ECCN" note) that have no ITAR counterpart — that is the one EAR-specific trap ITAR instinct will not catch, and it is the one the tool omits (2.2). §120.42's form/fit/equivalent definitions mirror the EAR's notes nearly word-for-word.

## 3. ITAR/USML gate and stop page

| # | Sev | Finding |
|---|-----|---------|
| 3.1 | MED | **Registration summary** ("Registration under 22 CFR 122 and a DDTC export authorisation are the operative requirements") omits the classic trap: §122.1(a) requires **manufacturers to register even if they never export** (one occasion of business suffices); temporary import also triggers; brokers register under part 129. |
| 3.2 | MED | **xlsx compliance record** writes "USML / ITAR check: Not described on the US Munitions List" as a bare conclusion. It is a one-click self-attestation with no CJ behind it; in an enforcement file it reads as an authoritative determination. Record it as an exporter self-determination with date, noting no CJ was obtained (22 CFR 120.12). |
| 3.3 | MED | **"Unsure" guidance** resolves doubt by self-screening into a binary; 22 CFR 120.4(a) prescribes the CJ when doubt exists, §120.12(f) confirms registration is not required to file one, and screening catch-alls requires the §120.41 SD analysis — none surfaced until after a "Yes." |
| 3.4 | MED | **"No" tile** equates "not on the USML" with "commercial or dual-use" — 600-series/9x515 items are military *and* EAR. The sub-text is right; the headline is wrong. |
| 3.5 | LOW | **USML paragraph (x)** nuance: every USML category's (x) paragraph *describes* EAR items ridable on DDTC licenses (§120.5(b)(2)); a literal reading of "described on the USML → ITAR" overreaches. |
| 3.6 | LOW | **See-through rule** unmentioned: §120.11(c) — a defense article remains ITAR-controlled after integration into a non-USML end item. One line on the result pages would close it. |
| 3.7 | LOW | Cite §120.31 (defense article) / §120.11 (USML order of review) alongside Supp. 4 para. (a); note §120.11(b)(2) (enumerated beats catch-all). |

Verified accurate: USML-first sequencing; "21 categories"; catch-all phrasing (§120.11(a)(2)); DS-4076 and pmddtc.state.gov; "BIS has no jurisdiction" headline; "appears to be a defense article" hedging.

## 4. Reasons-for-control map, series notes, GTN/GSN, definitions

| # | Sev | Finding |
|---|-----|---------|
| 4.1 | **HIGH** | **GSN summary is pre-2016 law.** Current GSN (since 81 FR 64691) is a **License Exception TSU** eligibility note ("available to all destinations, except countries in Country Group E:1") — not "product group D does not control…" — and its public-domain branch is [Reserved], pointing to §734.3(b)(3). The Cat 5 Part 2 exclusion sentence is the only accurate part. |
| 4.2 | MED | **GTN summary conflates Part 734 with the GTN.** Public-domain / basic-scientific-research / patent carve-outs are §734.3(b)(3)/§§734.7–734.10 concepts ("published," "fundamental research") — not in the EAR's GTN. The "peculiarly responsible" gloss of "required" is accurate. |
| 4.3 | MED | **SL (Surreptitious Listening) omitted entirely** from the RFC map and every index row (5A001.f.1, 5D001, 5E001 carry SL; 5A980/5D980/5E980 are SL-controlled and absent). §742.13; like EI, SL does not run through the Country Chart. |
| 4.4 | MED | **0A521 row shows AT1** — the actual entry is RS1-only ("no license exception eligibility other than … GOV under §740.11(b)(2)(ii)"), which the SERIES note itself states correctly. |
| 4.5 | LOW | Product group A's official title is "**Equipment, Assemblies and Components**" (§738.2(b)); "use" technology omits **refurbishing**; "end item" definition omits **ammunition** ("only ammunition, or fuel or other energy source"); accessories/attachments are defined by *enhancement*, not dependence; "600-series trumps" note needs the .x catch-all caveat (Step 4 analysis); 0Y521 description drops "or for foreign policy reasons"; SI's regulatory wording is "hot section technology for … commercial aircraft engines." |

Verified accurate: all 16 Country Chart column names; EI/UN/CW/SS/SI cites; FC1 = Inter-American Firearms Convention (§742.17); 600-series and 9x515 definitions (§772.1 / Supp. 4); 0Y521 GOV-only license-exception posture; category titles 1–9 and groups B–E; "software" and "material" definitions; EAR99 residual-risk note (incl. SDN via §744.8); Country Chart cite (Supp. 1 to Pt. 738); CCATS/SNAP-R currency (new host snapr.bis.gov).

## 5. The ECCN index — category-by-category

Severity key for rows: **dead** = ECCN no longer exists on the CCL; **ITAR-stub** = entry exists only as an ITAR cross-reference with no EAR license requirements; **codes** = wrong/missing reasons-for-control; **heading** = materially wrong scope.

### Category 0 (43 rows; 32 with issues)
- **Dead (11):** 0A001, 0B001, 0B002, 0B004, 0B005, 0B006, 0C001, 0C002, 0C004, 0C005 — removed **October 2013**, NRC jurisdiction under 10 CFR 110 (§774.1(b)(2) lists them); 0C003 likewise gone. Also dead: **0A918** (bayonets → now 0A501.y.6), **0A987** (superseded by 0A504), **0B986**.
- **ITAR/DOE stubs with fabricated codes:** 0D001, 0E001 (State/DDTC; DOE 10 CFR 810 for nuclear technology).
- **Wrong subject:** 0B999 is "Specific processing equipment" (AT North Korea / RS Iraq, non-chart), not firearms production equipment.
- **Wrong codes:** **0A979 is CC1, not SS** (SS in Cat 0 belongs to 0A980, horses by sea); 0A504 (FC1,RS1,CC1,UN — no NS/AT); 0A502/0A505/0A508/0A509/0E505 missing CC; 0A503 missing UN (CC is no-column, worldwide-except-Canada — same for 0A981/0A982/0A983/0E982); 0A919 missing AT1; 0A521 extra AT1.
- **Heading drift:** 0A501 still says "(non-automatic and semi-automatic)" although semi-autos were carved out to 0A506–0A508 (which the index itself lists); 0A509 covers parts for 0A506/0A507/0A508, not just shotguns; 0A505 is "Ammunition" (ordnance is elsewhere).
- **Notable missing:** 0A977/0A978 (crime-control), 0E502/0E504, the 0x604 line, 600-series B/D/E tails, 0A980.
- CATS[0] blurb: keep the firearms note; drop reactor/uranium/centrifuge examples (NRC since 2013).

### Category 1 (72 rows; 43 with issues)
- **Dead:** 1C352 (consolidated into 1C351), 1C012 (NRC, 2013). **ITAR-stub:** 1A102.
- **Wrong commodity:** **1C990** is fibrous/filamentary materials — not "detonating cord" (that's 1C992.c).
- **Systemic:** NS1→**NS2** on 1A002, 1A004–1A008, 1B001–1B003, 1C002–1C005, 1C007, 1C010, 1C011, 1D003 (1C001, 1C608, 1D001 legitimately NS1).
- **Missing codes (selection):** NP1 on 1A002/1A007/1B001/1B101/1C002/1C111/1C116/1D001/1D101/1E002; MT1 on 1B001/1C001/1C007/1C608/1D001/1E002; UN on 1A005/1A008; CB fixes across 1C350 (CB2 only), 1C351 (add CB2+CW), 1C353/1C354, 1C355 (CW,AT only — no CB), 1C395 (add CW), 1C991 (CB3); RS2 not RS1 for 1A004.d-chain (1A004/1D003/1E001); extra RS on 1A006; extra MT on 1C010; 1C298 heading inverted (covers *non*-reactor use; NP2, no AT).
- **Notable missing:** 1A001/1A003, 1A101, 1A227, 1A613, 1B115–1B119, 1B230/1B232/1B234, 1C225–1C241 gaps, 1C607, 1E101–1E104, 1E201–1E203, 1E350/1E355, 600-series tails.

### Category 2 (48 rows; 21 with issues)
- **Conflation:** **2E301** carries 2E201's heading/codes; actual 2E301 is *use* technology for 2B350–2B352 (CB2,AT1); 2E201 (nuclear use tech) missing from index.
- **2B001**: NS**2**, plus newly missing **NP1** (recent NP machine-tool rule); 2B008 heading describes items moved to 2B006; 2B232 heading pre-rewrite (now all gun types ≥1.5 km/s).
- **Missing codes:** MT1 on 2A001/2B004/2D001; NP1 on 2A226(CB2)/2B006/2B007/2B104/2B109/2B116/2D001/2D101; NP2 not NP1 on 2A290/2A291; CB**2** not CB1 on 2E001/2E002; extra NP on 2B119; extra MT on 2D002; legacy "CW" on 2B350 (CW obligations live in §742.18, not the entry).
- **Notable missing:** 2A983/2A984 (+D/E companions), 2B229/2B233, 2B018, **2B910/2D910/2E910 + 2E903** (Jan 2025 additive-manufacturing rule), 2E101/2E201/2E290, the 99x tier (2B996, 2B999, 2D992 …).

### Category 3 (41 rows; ~15 with issues)
- **Dead:** **3A993** (spectrum analyzers live in 3A992).
- **Advanced-computing RS missing:** 3A001 (RS on .z per §742.6(a)(6)(iii) + RS1 on MMICs; NS entry-level is Column 2), 3D001/3D002 (NS **Column 1**, RS for 3B001.q / dry-etch software), 3B002.c (EUV mask inspection, NS+RS Macau/D:5); 3A992/3A999 missing Pakistan RS (§742.6(a)(12), Nov 2024); 3A002 missing MT1 (.h).
- **NS column flips (opposite direction):** 3D002/3D003/3E001/3E002/3E003 are NS **Column 1**, not 2.
- **Headings:** 3D003 is now "computational lithography software for EUV masks"; 3D002's "stored-programme" phrasing obsolete.
- **Notes block:** ".z added Oct 2023" **verified correct** (88 FR 73458; the Oct 2022 rule created 3A090/4A090 but not the positive .z paragraphs — confirmed against the Jan 2023 corrections and the Apr 2024 rule's description of ".z paragraphs … from the October 2023 IFRs"); "3B090 removed Oct 2023" **correct** (88 FR 73424); the 3E001 note is outdated — RS now covers technology for 3A001.z and *all* of 3A090 (.a worldwide; .b/.c destination-scoped), not just 3A090.a.
- **Notable missing:** 3B993/3B994 (+3D992–994/3E992–994, Dec 2024), **3E905 GAAFET**, Sept 2024 quantum/900-series (3A901, 3A904, 3B903/3B904, 3C907–3C909, 3D901/3D907, 3E901), 3A069/3E069 (Jan 2025 biotech), 3A234.

### Categories 4–5 (33 rows; ~20 with issues)
- **Dead:** **4D003**.
- **SL systematically absent:** 5A001/5D001/5E001 show a phantom **RS1** instead of their actual **SL** (§742.13, all-destinations); 5x980 interception entries missing (see 4.3).
- **RS(.z) missing on:** 4A003 (also CC1, NS split), 4A004 (also NS**2**), 4A005, 4D001 (also CC1), 5A002, 5A004, 5D002, 5E002, 5A992/5D992/5E992 (RS on .z variants); 4E001 missing MT1+CC1; 5B001 NS**2**; **5B002 has a phantom EI** (actual: NS,AT only).
- **4D090 heading over-broad:** .z software is controlled in 4D001/5D002, not 4D090; ZDOTNOTE misapplied to 4A090 itself (it has no .z — it is the threshold entry).
- **4E091:** exists and is **legally in force** in the current CCL (RS worldwide §742.6(a)(13) + AT1). The Jan 15, 2025 AI-Diffusion IFR (90 FR 4544) was never formally rescinded — BIS announced non-enforcement May 13, 2025; GAO-confirmed unfinished as of Jan 2026. The tool's hedge is right in direction; update to "codified and operative; BIS non-enforcement posture since May 2025 — relying on non-enforcement is a policy-risk decision."
- **Notable missing:** 4A906/4D906/4E906 (quantum computers, Sept 2024), 4A001, 4x980 (fingerprint, CC).

### Category 6 (30 rows; 18 with issues)
- **6A611 is a pointer entry** (redirects to 3A611/7A611) with no license requirements — codes fabricated.
- **Systemic NS2:** all of 6A001–6A008 (and 6B004/6B007/6C002/6C004/6C005) are NS Column 2; NS1 in Cat 6 belongs only to 6D/6E entries.
- **Missing codes:** 6A002 (MT1, CC1, UN), 6A003 (NP1, RS1, UN; NS2), 6A005 (NP1), 6A007/6A008 (MT1), 6B008 (MT1 entire entry), 6D001 (MT1, RS1), 6D003 (RS1), 6E001/6E002 (RS1, CC1, UN), 6A991 (AT **Column 2** + §746.8 Russia), 6A998 (RS1/RS2; heading stale), 6A992/6A996 (Iraq/Pakistan RS notes; heading gaps).
- **Notable missing:** 6A202 (photomultipliers, NP), 6A293/6D201/6E202 (recent nuclear high-speed-camera additions), 6D002, 6B108, MT/NP tech chains (6D102/6D103/6E101/6E201), 6A999.

### Categories 7–8 (36 rows; 17 with issues)
- **Swapped headings:** **8A609 is "Surface vessels of war…"; 8A620 is "Submersible vessels, oceanographic…"** — the tool has them reversed.
- **ITAR-stubs shown as EAR:** 7A106, 7A115, 7A117.
- **7A005 framing obsolete:** government-use decryption GNSS receivers are now ITAR (7A005.a related-controls); only .b (adaptive antennas) remains; NS/MT/AT apply to .b. The tool's "military code decryption" search terms point users at the wrong regime. (7D005 — decryption software for satnav — exists and is missing.)
- **Missing MT1:** 7A611, 7B001, 7B003, 7D002. **NS2 not NS1:** 8A001, 8A002, 8B001, 8C001. **Headings:** 8B001 is low-noise water tunnels only; 8D002 is propeller noise-reduction software.
- **Notable missing:** **7E001/7E002/7E003** (the generic technology entries — the index jumps 7D004→7E004), 7D001, 7D005, 7B002, 7x611 companions, all 8x609/8x620 B/C/D/E companions, 8A992's §746.8 flag.

### Category 9 (52 rows; ~35 with issues)
- **ITAR-stubs shown as EAR (16 rows):** 9A005–9A009, 9A011 (→ USML IV/XIX), 9A104/9A105/9A107/9A108/9A109/9A111/9A116/9A117/9A118/9A119, and 9A010 (pointer to 9A604/9A515/USML). None has an EAR license-requirements table; all show "MT1,AT1" in the tool.
- **Fabricated/wrong headings:** **9A120** is aerosol-dispensing UAVs (not lighter-than-air vehicles); **9B003** is gas-turbine *brush-seal* production/test equipment; 9B001 heading stale; 9A110 rescoped to 9A012-UAV structures.
- **SI mis-tagged:** only **9E003** carries SI ("SI applies to 9E003.a.1 through a.8, .h, .i, and .l"); remove from 9A001/9A003/9B001.
- **Codes:** 9A001 missing MT1 (and no SI); 9A002/9A003 NS**2**; 9A004 has no MT and RS is .y-only (China/Russia/Venezuela §742.6(a)(7)); **9A012 has no RS** — and the **Jan 2026 drone rule** (91 FR, eff. Jan 20, 2026) re-tiered 9A012.a.1 to NS Column 2; 9A515/9E515/9A610 missing MT1; 9E003 has no MT; 9A991 missing UN; 9B002/9B004 missing MT1; 9D001–9D003 missing MT1.
- **Notable missing:** 9D610/9D619/9E610/9E619 (600-series software/tech — hardware is indexed, companions aren't), 9B515, 9A102, 9B010, 9E102, 9A604/9A620 lines, 9A980/9A990/9A991-family AT tier.

## 6. Rule-history and currency claims

- **"Current to 24 Jul 2026" (RULEDATE):** for the entries it contains, nothing post-dates it — but the index omits every ECCN created by the Sept 2024 (89 FR 72926), Dec 2024 (89 FR 96790) and Jan 2025 biotech (90 FR 4612) rules (28 ECCNs), and its reason-codes match pre-2023/2024 editions in the patterns above. The claim overstates coverage; the July 23, 2026 suppressors IFR (91 FR 46252 — the amendment flagged in eCFR at 91 FR 46261) delays its CCL amendments to **Nov 20, 2026**, so its absence is defensible today but is a scheduled break.
- **Verified dates:** .z paragraphs — created Oct 25, 2023 (88 FR 73458; tool correct); 3B090 removal — Oct 25, 2023 (88 FR 73424; tool correct; Dec 2024 rule further spun items into 3B993/3B994); 3A090 — created Oct 13, 2022 (87 FR 62186), .c/HBM added Dec 2024; "tightened repeatedly" is stale — Jan 2026 (91 FR 1684, H200-class case-by-case to China) and Jul 2026 (91 FR 43034, UAE) *loosened* posture.
- **4E091:** see §5 Categories 4–5 — codified and operative; non-enforcement posture; never rescinded by rulemaking.
- **SNAP-R/CCATS:** current (new host snapr.bis.gov); BIS Interactive CCL link valid.

## 7. Recommendations (in priority order)

1. **Kill the jurisdictional traps first:** convert every ITAR-stub row (Cat 9 rocket chain, 1A102, 0D001/0E001, 7A106/7A115/7A117, and Cat 0's NRC/dead rows) to explicit "subject to the ITAR → USML Cat …/DDTC" or "NRC (10 CFR 110)" redirects; fix the 8A609/8A620 swap; fix 7A005's decryption framing.
2. **Gate the SD releases by item type** per the (b) chapeau; add the (b)(3)/(b)(4) "another AT-only ECCN" note; add the USML branch to (a)(1).
3. **Restructure the wizard** to match Supp. 4: split enumerated 600/9x515 (Step 3) from catch-alls (Step 4, routed through the SD tool); run that screen across all candidate categories; add a §734.3 scope question; require full-CCL attestation before the EAR99 result.
4. **Re-derive every index row's reason codes from the current CCL** (the audit's per-row corrections are listed above; the NS-column pattern alone touches ~40 rows), add SL to the RFC map, and add the missing 2024–2025 ECCNs or state explicitly that post-2024 additions are out of scope.
5. **Rewrite the GSN summary** as License Exception TSU eligibility; re-attribute the GTN carve-outs to Part 734; update the 4E091 and 3E001 notes; sharpen the ITAR stop page (manufacturer registration, self-determination language in the xlsx, see-through rule, paragraph (x)).
6. **Institutionalize currency:** the index needs a per-rule changelog (rule date + FR cite per row) rather than a single RULEDATE, and a scheduled re-check before Nov 20, 2026 (suppressors IFR effective date).

---

## Remediation record (applied 2026-08-17, this branch)

All four remediation tracks were approved and applied to `navigator.html` in the commit accompanying this file:

1. **Index rebuilt from source.** Every row's reason-for-control codes were re-derived programmatically from the 2026-08-12 eCFR text of Supp. No. 1 to Part 774 (extraction script validated against the audit findings before use). The index grew from ~355 to 440 rows: 85 missing entries added (including the Sept 2024 quantum/AM/GAAFET, Dec 2024 SME, Jan 2025 biotech ECCNs, the SL-controlled 5x980 family, and 7E001–7E003), 12 NRC-jurisdiction rows and 6 removed-entry rows converted to flagged redirects, and ~26 ITAR/pointer stubs converted to explicit "subject to the ITAR"/cross-reference flags rendered as jurisdiction warnings, not EAR results. Swapped/wrong headings (8A609/8A620, 1C990, 9A120, 2E301, 2B008, 3D003, 7A005 and others) corrected. New non-chart code vocabulary added (SL, RS0/CC0/AT0/NS0/NP0/MT0/CB0, RUS, ITAR/NRC/DOE/REF/GONE).
2. **§772.1 tool now enforces the (b) chapeau.** A Part 0 item-type question gates the releases; end items/equipment/systems/materials caught by (a) conclude "specially designed — no release path." (a)(1) gained the USML branch; (b)(3)/(b)(4) hints carry the "another AT-only ECCN or EAR99 item" restriction; conclusions no longer overstate ("falls within the paragraph" → "must also meet the paragraph's other requirements"; released items are directed back into the Order of Review).
3. **Wizard restructured to Supp. No. 4.** Now nine steps: a §734.3 scope screen joined the USML gate (with CJ/DS-4076 guidance on "unsure"); the 600-series/9x515 check split into enumerated (Step 3) and .x catch-alls routed through the §772.1 test (Step 4), both scoped across all categories; EAR99 requires an explicit full-CCL attestation before the result renders. The ITAR stop page now covers manufacturer registration (§122.1(a)), the see-through rule (§120.11(c)), and paragraph (x) (§120.5(b)(2)); the xlsx records the USML answer as a dated exporter self-determination with no CJ obtained.
4. **Definitional text corrected.** GSN rewritten as the License Exception TSU note (81 FR 64691); GTN carve-outs re-attributed to Part 734; product group A retitled; "use"/end-item definitions completed; 4E091 note updated to codified-but-unenforced; 3E001/4E001/3A090/4A090 notes rescoped; firearms rows carry a Nov 20, 2026 suppressors-IFR caveat; RULEDATE moved to the verified baseline (12 Aug 2026).

Verified by a scripted Chromium walkthrough (all nine steps, ECCN result, EAR99 attestation flow, ITAR-stub rendering, SD chapeau gating) with zero console errors.

*Decision-support audit; not legal advice. Every finding cites the eCFR text as of 2026-08-12/13 or a dated Federal Register rule; confirm against the live CCL before edits ship.*
