# Typography and component consistency

## Inventory by role

Inspect the shared design tokens and component definitions before counting individual declarations. For a page-wide review, group representative elements by role: display heading, section heading, card title, body, caption, navigation, and button label. Record the actual family, size, weight, line height, and letter spacing at the same viewport where tools permit it. Account for responsive and fluid sizing before calling values inconsistent.

Example: equivalent section headings use 32px, 33px, and 35px without a deliberate reason. If the design token for section headings is 32px, propose reusing it. A 64px hero and a 14px caption are not evidence of inconsistency. Without an established target, propose a role mapping instead of silently declaring the most frequent value correct.

Treat the number of unique values as a diagnostic clue, not a quality score. A complex application can legitimately need many sizes. Compare intent and use, not only numerical similarity.

Build a compact role-to-token mapping for ordinary sections and check it across the page. Equivalent headings should reuse one heading treatment, ordinary paragraphs one body treatment, and comparable card titles or labels their own shared treatments. Match weight, line height, and responsive rules as well as size so the reading rhythm remains consistent. Consolidate unjustified one-off values at their call sites rather than creating a token for every existing variation.

Example: five ordinary sections use body sizes of 15px, 16px, 17px, 18px, and 20px at the same viewport without distinct roles. Reuse the established body treatment. Keep a deliberately larger introduction or editorial quote as an explicit role, rather than forcing it into body styling. Five to ten sizes distributed across valid roles are different from five to ten sizes for equivalent content.

Before changing a shared text token, check whether creative sections consume it. Preserve their deliberate overrides or give the exceptional role a scoped treatment when needed. Never let a global consistency fix silently resize a statement heading or break animated typography.

## Font direction

For a new interface, use the brief and references to determine the intended character before selecting fonts. Inspect project assets and existing families first. Explain a proposed face in terms of its visible properties and use in the actual content, rather than vague claims such as 'premium' or 'modern'. Consider heading/body compatibility, language coverage, available weights, and loading cost.

Default to one family or a complementary heading/body pair. A third or fourth decorative family needs a clear role; consolidate accidental additions when typography changes are in scope. Fallback fonts, language-specific faces, and a functional monospace face for code are not automatically competing decorative families. Do not count every name in a CSS fallback stack as a separate design choice.

Use upright headings and labels by default. Avoid isolated italic words, script accents, or mixed typefaces added only for visual novelty. Preserve meaningful emphasis and deliberate editorial or brand styling. If removing italic styling from semantic emphasis, preserve the meaning rather than blindly deleting the semantic element.

If a user asks to replace a generic-looking font, offer a focused choice or implement a justified choice within the authorized scope. Check the new font in real headings, paragraphs, numerals, and buttons. Recheck wrapping and geometry; changing the face changes its metrics. Never rely on a universal blacklist of common fonts or swap fonts during an alignment-only fix.

If a user-selected font appears poorly suited to the content, explain the specific conflict, such as weak body readability, unsuitable character, or missing language coverage. Implement a better fit when font replacement is authorized; otherwise propose it without overriding an explicit choice. For new builds, make a justified choice directly instead of asking the user to solve routine font selection.

## Button families

Map actions by purpose and existing variant before comparing styles. Compare equivalent primary actions together, equivalent secondary actions together, and so on. Check label role, minimum height, horizontal padding, radius, border width, icon dimensions, icon gap, and focus/disabled states.

Separate visual style from size. A simple marketing site usually needs only two or three core styles; compact navigation controls and regular CTAs may use explicit size variants. Within the same style, size, viewport, and state, single-line buttons should share the same height and geometry. A component having several unexplained heights across sections is drift, not a new variant for each instance.

Example: regular primary CTAs render at 44px, 47px, and 52px because each section sets its own padding and line height. Reuse the established regular size and remove conflicting overrides. A deliberate compact navbar CTA may remain smaller. Use minimum heights and consistent padding that allow growth for long labels or zoom rather than clipping text to preserve an exact height.

Example: two primary 'Book now' actions with the same role use different radii and padding. Reuse the existing primary variant if there is one. A destructive action or a compact toolbar icon button may legitimately differ; preserve its semantics and usability. Do not turn an actual button into a link or vice versa merely to share a class.

## Shared changes

Trace the uses of a token or component before modifying it. Prefer applying the correct existing variant at an inconsistent call site over changing a shared variant that is already correct elsewhere. If no shared system exists, introduce only the small set of reusable values needed for the current scope. Verify representative consumers after a shared change.

## Output

For a consistency finding, name the role, affected locations, observed differences, intended shared rule, and proposed adjustment. Separate accidental drift from deliberate exceptions. State when viewport, states, or font rendering could not be verified.
