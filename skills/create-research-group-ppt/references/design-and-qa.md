# Design system and quality assurance

## Adaptive design baseline

Use a 16:9 canvas with a clean white background, dark-gray primary text, and restrained deep-blue accents. Maintain strong hierarchy, generous margins, and academic restraint. Build an original clean master; do not retain `Made with GAMMA` or other third-party template branding.

Treat this as a design language, not a fixed template. Vary layout according to content:

- use process diagrams for workflows and dependencies;
- use before-after structures for method or formula changes;
- use plots and experimental figures for quantitative evidence;
- use annotated formulas for mathematical changes;
- use tables only for genuine repeated-field comparison;
- use cards sparingly for short categories or decision summaries.

Avoid decks where most slides reuse the same table, card grid, or text-heavy layout. Preserve consistent typography, spacing, color, and chapter navigation while allowing page-specific composition.

## Design tendencies

- `严谨学术型`: prioritize definitions, formulas, controlled comparisons, and precise annotations.
- `视觉讲解型`: prioritize mechanisms, process diagrams, experimental figures, and progressive explanation.
- `决策讨论型`: prioritize questions, evidence, options, risks, and next decisions.
- `自定义`: follow user-specified palette, density, reference slides, or composition while preserving readability and evidence integrity.

Recommend one tendency after the report type is chosen, but require confirmation or adjustment before production.

## Visual rules

- Keep titles concise and conclusion-oriented.
- Make the main takeaway visible without reading speaker notes.
- Use Chinese labels in diagrams and charts unless an official name must remain unchanged.
- Do not fabricate decorative data, plots, citations, or icons that imply evidence.
- Preserve figure aspect ratios and legibility.
- Avoid tiny body text, excessive borders, dense full-slide tables, and uncontrolled color proliferation.
- Include section dividers for multi-project reports.
- Keep projects visually consistent but structurally separate.

## Required QA

Render every slide and inspect at full size. Check:

1. the approved presentation artifact opens successfully and remains editable: `.pptx` by default, or offline `.html` when explicitly requested;
2. slide count and order match the approved outline;
3. every substantive claim maps to the evidence ledger;
4. status wording distinguishes verified, implemented, planned, blocked, rejected, and uncertain work;
5. every material workflow or formula change has before, after, rationale, core difference, and impact;
6. Chinese terminology and first-use bilingual expansion follow the content rules;
7. formulas are legible, notation-consistent, and correctly highlighted;
8. speaker notes exist on every substantive slide when the approved format supports them; otherwise the pre-approved limitation and agreed substitute are recorded;
9. no text, shape, image, or chart overflows the canvas;
10. no empty placeholders, clipped text, accidental overlaps, or unreadable labels remain;
11. no third-party template branding remains;
12. layouts show appropriate variation without losing visual consistency;
13. files are saved to the agreed output location and existing decks remain untouched.
14. the evidence map contains one row for every slide, uses all required columns, and gives accurate task locators and local artifact paths;
15. the QA report contains every required check with an explicit `PASS`, `FAIL`, or `NOT RUN` result.

## QA report format

Record each check as `PASS`, `FAIL`, or `NOT RUN`. For `FAIL`, state the defect and whether it was fixed. For `NOT RUN`, state why and name any substitute inspection. Do not convert substitute evidence into a false pass.
