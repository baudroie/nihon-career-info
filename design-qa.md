# 日本大学 responsive QA

final result: passed

Source truth: approved Aoyama public build 50bd52652a8fe76b131ad3096a74d4ebd53a51f6, captured at 1440x1058 and 390x1120 CSS px, density 1. Reference images: aogaku-career-info/qa/audience-ribbon/published-desktop-1440.png and published-mobile-390.png in the parent workspace.

Implementation captures: university-lp-batch/qa/nihon-{320,390,768,1440}.png. Combined comparisons: desktop-board-1/2.jpg and mobile-board-1/2.jpg. Each board includes the source in the same image; desktop panels are uniformly scaled to 720px. Native captures retained for focused review. UI state: hero after load; existing initial underline animation retained.

## Required fidelity surfaces
- Typography: original live headline and all glyph transforms unchanged. Supplementary local Noto subsets cover university kanji; CampusNote covers each campus caption. Ribbon stays on one line at all widths.
- Layout: existing header, hero, bubbles, students, lower content and closing CTA retained. Taller campus asset overlapped the caption in initial Toyo capture. Corrected new campus image scale to .88 at its baseline and moved caption to top:0; captured and compared again. Aoyama retains original campus size.
- Color: only ribbon face/tails/folds changed to the university-specific LP palette. White label contrast preserved; other colors unchanged.
- Image quality: new 1536x1024 transparent campus illustration (Aoyama reuses original 1400x933) in the same black-line/orange-tree style. White building/student interiors retained. No blank rectangle on the cream page. Campus labels are native text.
- Copy: university name, eligibility, event copy, alt text, title, description, canonical and social URL changed consistently. Existing shared LINE destination retained; no university-specific tracking URL was invented.

## Verification
Real browser at 320/390/768/1440px: horizontal document overflow 0; broken images 0. Menu opens, LINE section link closes it and changes hash to #register. Sticky header top=0. All three external CTA URLs preserved. No form submitted. Browser error log empty. All ten builds succeeded; existing packaging smoke tests passed (4/4). Shared JS and motion code are byte-identical to the accepted base. No additional animation added.

Intentional differences are university text, ribbon palette, campus drawing and the small campus-size adaptation to protect captions. No numerical fidelity score claimed.

Publishing: main /docs. QA screenshots, source photographs and original generated masters are not included in the production build.


---

# Nihon ribbon concept 3

final result: passed

Reference: selected third generated concept, exec-b6de90e5-979d-4500-b309-d3549e948a0c.png. Ribbon component is the fidelity target; surrounding existing page layout is preserved.

Implementation: curved ribbon with folded tails, white native SVG text on a common textPath, university name 60 and suffix 42 in SVG units. Existing university palette and local font retained. Accessible text is exposed once outside the decorative SVG.

Comparison: selected-ribbon-reference.png compared with refined-390.png and refined-1440.png. Same arch, university/suffix hierarchy, folded tails and white seam treatment. Existing flat fill retained rather than generated image shading. No numerical fidelity score claimed.

Round 1: extra seam triangles and cramped word spacing. Fixed seam path and added 6 SVG units of spacing; recaptured and inspected.

Final browser checks: 320/390/768/1440 CSS px, horizontal overflow 0 at every width. Ribbon lettering contained and heading separated. Campus image loaded. All three external LINE URLs preserved. Mobile menu opens; LINE section link reaches #register and closes menu. Browser error log empty. Vite production build succeeded.

Evidence: refined-{320,390,768,1440}.png and responsive.json, stored locally in this QA folder. Screenshots and reference artwork are excluded from production docs.

Scope: Nihon ribbon only. Existing hero headline, campus, bubbles, lower content and LINE destination retained.
