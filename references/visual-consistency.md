# Typography and component consistency

## Inventory by role

Inspect the shared design tokens and component definitions before counting individual declarations. For a page-wide review, group representative elements by role: display heading, section heading, card title, body, caption, navigation, and button label. Record the actual family, size, weight, line height, and letter spacing at the same viewport where tools permit it. Account for responsive and fluid sizing before calling values inconsistent.

Example: equivalent section headings use 32px, 33px, and 35px without a deliberate reason. If the design token for section headings is 32px, propose reusing it. A 64px hero and a 14px caption are not evidence of inconsistency. Without an established target, propose a role mapping instead of silently declaring the most frequent value correct.

Treat the number of unique values as a diagnostic clue, not a quality score. A complex application can legitimately need many sizes. Compare intent and use, not only numerical similarity.

## Font direction

For a new interface, use the brief and references to determine the intended character before selecting fonts. Inspect project assets and existing families first. Explain a proposed face in terms of its visible properties and use in the actual content, rather than vague claims such as 'premium' or 'modern'. Consider heading/body compatibility, language coverage, available weights, and loading cost.

If a user asks to replace a generic-looking font, offer a focused choice or implement a justified choice within the authorized scope. Check the new font in real headings, paragraphs, numerals, and buttons. Recheck wrapping and geometry; changing the face changes its metrics. Never rely on a universal blacklist of common fonts or swap fonts during an alignment-only fix.

## Button families

Map actions by purpose and existing variant before comparing styles. Compare equivalent primary actions together, equivalent secondary actions together, and so on. Check label role, minimum height, horizontal padding, radius, border width, icon dimensions, icon gap, and focus/disabled states.

Example: two primary 'Book now' actions with the same role use different radii and padding. Reuse the existing primary variant if there is one. A destructive action or a compact toolbar icon button may legitimately differ; preserve its semantics and usability. Do not turn an actual button into a link or vice versa merely to share a class.

## Shared changes

Trace the uses of a token or component before modifying it. Prefer applying the correct existing variant at an inconsistent call site over changing a shared variant that is already correct elsewhere. If no shared system exists, introduce only the small set of reusable values needed for the current scope. Verify representative consumers after a shared change.

## Output

For a consistency finding, name the role, affected locations, observed differences, intended shared rule, and proposed adjustment. Separate accidental drift from deliberate exceptions. State when viewport, states, or font rendering could not be verified.
