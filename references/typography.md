# Typography diagnosis

## Loaded face and weight

Inspect declared families, loaded resources, and rendered-font information when the browser provides it. A computed `font-family` is a preference list, not proof that the first face supplied the visible glyphs. A resolved font-loading promise alone does not prove the intended font loaded successfully. Check for resource errors or fallback. Distinguish an available weight from synthetic bold. Do not change the font because the screenshot looks slightly different across operating systems.

For variable fonts, inspect the axes actually supported by that font. Preserve intentional optical sizing and weight settings. Do not invent font features or assume every face supports the same axes.

## Line boxes and visible text

Treat line height as the height of a layout line box, not visible ink. Capitals, lowercase letters, numerals, and descenders occupy different areas inside it. Centered line boxes can look uneven beside an icon. Compare realistic labels with ascenders and descenders before adjusting.

For two-line labels next to a large numeral, identify whether the reference uses center, baseline, or another deliberate relationship. Treat the two lines as a group. Tune the intended font size and line height before considering a local optical correction. Never force all typographic relationships onto one baseline rule.

## Numerals and dynamic content

Test changing values such as 9, 10, 33, and 100 when the component supports them. Consider tabular numerals only when stable digit widths serve the design and the font supports the feature. They do not solve every group-centering issue. Preserve overflow and wrapping behavior for real content.

## Font choice when requested

Start with the existing brand and project constraints. Compare candidates in the actual component using relevant glyphs and weights, not only a font name or specimen heading. Check language coverage, source availability, loading behavior, and the project's licensing requirements before proposing adoption. Explain subjective fit as a design judgment. Do not promise one universally correct typeface.

## Accessibility and robustness

Check text remains usable with zoom and user text-spacing changes when supported by the testing environment. Avoid fixed heights or tight line heights that clip content. Do not change semantic labels, reading order, or contrast merely to balance a composition.
