---
name: ocd-ui
description: Build, review, or refine frontend visual finish, especially AI-generated pages. Use for misaligned nested controls, inconsistent buttons, awkward heading wraps, mismatched typography, uneven section spacing or widths, unbalanced columns, and excessive copy or decoration. Support source code, screenshots, and rendered pages while preserving design intent. Do not use for unrelated backend work.
---

# OCD UI

Perform the finishing pass that turns a collection of generated sections into a coherent interface. Make relationships deliberate at both page and component scale: common edges, balanced spacing, controlled typography, consistent controls, and concise content. Preserve the user's visual intent. Treat geometric measurements as evidence and optical balance as a contextual judgment, not a universal numeric score. Follow explicit user instructions over these defaults.

## Establish the task and evidence

1. Determine whether the user wants a review, a fix, or guidance while building. Report findings without editing for a review; implement scoped changes when a fix is requested. For a build, apply the checks during implementation and inspect the finished result.
2. Identify the component and intended reference. Distinguish reference screenshots from screenshots of a faulty implementation. Do not assume a supplied image contains a defect. Ask only when that distinction would materially change the work.
3. Read relevant components, styles, tokens, font declarations, and existing variants. Reuse the project's conventions. Preserve brand fonts, intentional asymmetry, animation, and hierarchy unless the user asks to change them.
4. Establish available evidence:
   - Source plus live rendering: inspect both implementation and visible result.
   - Screenshot only: describe visible relationships; mark causes as hypotheses. Do not infer exact CSS, font identity, or source-pixel offsets from a resized crop.
   - Source only: identify structural risks and state that optical balance remains visually unverified.
5. Use only the host's available and permitted browser or image tools. This skill supplies instructions, not browser access. Do not claim that a page was opened or a screenshot examined unless it was.

For a broad polish request, include layout, typography, and unnecessary decoration within the requested area. When copy editing is in scope, shorten redundant wording while preserving meaning. For an alignment-only request, keep wording and font choices intact. Preserve supplied final copy and brand requirements; report conflicts with the desired composition instead of silently rewriting them.

## Establish a consistent visual system

Read [references/visual-consistency.md](references/visual-consistency.md) for typography and component consistency. For whole-page work, also read [references/page-composition.md](references/page-composition.md) for widths, section rhythm, columns, heading composition, and content restraint. Read only the references relevant to a local fix.

Inventory the relevant content containers, section spacing, text roles, font families, sizes, weights, line heights, and button variants before changing them. Compare equivalent roles at the same viewport and state. Distinguish deliberate hierarchy, responsive sizing, and semantic variants from accidental drift. Use explicit references first, then established project rules; when neither provides a target, establish a small coherent system instead of treating every existing value as intentional.

- Use a shared type scale across ordinary sections: equivalent section headings, body text, card titles, and labels should each reuse their role's size, weight, line height, and responsive behavior. Investigate five or ten ad hoc sizes across comparable text instead of letting each section invent its own scale. Do not make distinct roles such as hero, section heading, and caption the same size.
- Preserve intentionally creative sections: editorial statements, oversized statistics, asymmetric layouts, and animated typography can depart from the ordinary section pattern. Identify the compositional reason before normalizing a difference. Fix a local defect without flattening the section's character; when intent is unclear, report uncertainty rather than treating uniqueness as a bug.
- Reuse the existing type scale and component variants. Consolidate near-duplicate values only when they serve the same role; do not limit a whole site to an arbitrary number of font sizes or button types.
- For new work without a system, default to one or two complementary font families and two or three core button styles, with explicit size variants only where needed. These are restraint defaults, not a reason to remove necessary semantics or established brand choices. Establish a small role-based type scale and reuse responsive values across sections.
- When font selection or replacement is in scope, explain how the face fits the brand, content, and desired character. Compare real heading and body samples. Do not choose a font merely because it is a familiar default, and do not ban a common font merely because AI often uses it. Preserve an established brand font unless the user authorizes a change.
- Keep primary, secondary, destructive, link, and icon-only actions distinguishable where needed. Match the geometry of equivalent buttons: font role, height or minimum height, padding, radius, border, and icon spacing.
- Keep headings and UI labels upright by default. Use italic or decorative emphasis only when it serves the reference, brand, or meaning; do not add it merely to make a heading look designed.
- Use a common content container and horizontal gutters for ordinary sections. Keep full-width backgrounds, deliberate full-bleed content, and constrained reading widths distinct. Establish consistent section spacing without forcing every section to an identical height.
- During implementation, use shared tokens/components rather than repeating new one-off values in each section. Avoid expanding a polish request into a component-library rewrite.

## Inspect before adjusting

Inspect at the intended display size first, then zoom for diagnosis. For live pages, wait for font loading and a stable relevant UI state. Keep before/after viewport, content, zoom, and state comparable.

Check in this order:

1. **Page composition, when in scope:** inspect the whole page and individual sections. Compare content edges, section spacing, column relationships, hero line breaks, and content density. Identify unnecessary eyebrows, dividers, and decoration. Prioritize these larger relationships before tiny icon offsets.
2. **Typography:** intended font actually rendered, available weight, fallback behavior, line height, letter spacing, wrapping, and hierarchy. Read [references/typography.md](references/typography.md) when diagnosing font or baseline issues. If font selection is in scope, choose based on brand, content, language coverage, and real rendered samples; explain replacements.
3. **Layout geometry:** parent layout, alignment properties, dimensions, border thickness, logical padding, gaps, baseline relationships, and repeated edges. For nested pills or circles, compare top, bottom, and trailing insets separately from the alignment of their contents. Measure with existing browser tools where available. Distinguish element rectangles from visible glyph and SVG-path bounds.
4. **Visible balance:** inspect text and icon mass, stacked labels next to numerals, nested controls, and apparent surrounding space. Read [references/component-patterns.md](references/component-patterns.md) for those cases. Do not equate mathematical centering with a guaranteed visual result.
5. **Resilience:** inspect the component at its smallest supported viewport and a representative larger one, plus intermediate widths around changed wrapping or layout breakpoints. Exercise relevant short/long labels, changing numeric values, and actual font fallback where practical. Check focus outlines, clipping, and pointer targets after changes. Include RTL and other languages when the project supports them.

For each candidate worth acting on, keep a short evidence note: location, observed relationship, expected rule or reference, and correction. Record actual inspected measurements when available; do not turn an unperformed checklist into a claim of verification. Leave already-correct components alone.

## Decide and fix

Classify each candidate as:

- **Verified defect:** visible clipping, unintended overlap, missing font/weight, or a measurable inconsistency against an established component rule or supplied reference.
- **Optical refinement:** a supported visual judgment that should be compared before and after.
- **Preference or unknown:** a redesign choice or uncertainty; do not present it as a bug.

Make the smallest change that addresses the cause:

- Correct layout structure, font loading, line boxes, or an asset's internal whitespace before adding compensating offsets.
- Use shared layout constraints and tokens for repeated elements. Do not impose a new spacing scale or type scale on an existing design.
- Prefer logical properties when direction matters. Do not hardcode a label width or a line break simply to make one screenshot match.
- Do not crop a glyph's descender, remove focus indicators, reduce the existing usable hit area, hide overflow, or truncate necessary content to obtain visual balance. Shorten copy only within the editorial scope established above.
- If geometry is sound and an optical adjustment still helps, use a small, local, explainable correction. Scope it to the relevant icon/font variant and verify it with alternate content. Do not apply a global transform or arbitrary offset to every icon.
- Do not install a dependency or add a runtime measurement system for a change achievable with existing CSS and assets.

## Verify and finish

After editing, inspect the same component again. Check its relevant variants and neighboring layout for regressions. After shared font, container, or spacing changes, inspect representative sections across the page, not just the original trouble spot. Recheck heading wraps and column balance after font or copy edits. Run existing focused checks when the change could affect behavior; a build alone does not verify appearance.

Use at most two refinement passes by default. Stop when the identified defect is resolved and no clear regression remains. If the remaining difference is subjective or a required reference is missing, state that instead of cycling through tiny offsets.

Report only meaningful findings or changes. For each, include location, observed relationship, supporting evidence, and proposed/applied correction. Separate visual verification from code inspection. Summarize which sizes/states were checked and what remains unverified. Say when no actionable issue is visible; never invent a finding to justify using the skill. Do not promise pixel perfection or improvement across models without evaluation.
