# OCD UI

**The button is centered. The icon has other plans.**

Your agent built the page. The hero looks good. You scroll down.

The next heading is a slightly different size. The third section has discovered another font weight. There are six “Book now” buttons, apparently designed by six people who have never met.

You ask for consistency.

It adds a gradient.

OCD UI is an agent skill for the part where you start noticing things.

## What it does

It gives your coding agent a finishing pass for page composition, typography, spacing, optical alignment, and consistency across an interface. It covers both the tiny inset you cannot unsee and the section that feels wrong before you know why.

| The thing you keep noticing | What the skill asks the agent to check |
| --- | --- |
| Every section heading has its own ambitions | A shared type scale for equivalent roles |
| The font technically exists | Whether it actually fits the brief, loads correctly, and works in the real content |
| Same action, different button, different postcode | Shared variants, padding, radii, label styles, and icon gaps |
| `align-items: center` has been applied, so the case is closed | Visible text and icon balance, alongside the layout measurements |
| The counter looks fine until it reaches 100 | Changing values, longer labels, wrapping, and relevant screen sizes |
| One tiny adjustment somehow moved the whole page | Scoped fixes and a check of the result |
| A pill button sits inside a pill navbar, almost convincingly | Equal top, bottom, and trailing insets where the design calls for them |
| The hero heading has become a five-storey building | Deliberate heading wraps, sensible text width, and concise copy when editing is in scope |
| Every section has chosen its own edges and breathing room | Common content containers, responsive gutters, and consistent section spacing |
| Two matching cards cannot agree where their buttons belong | Balanced columns, matching panel geometry, and aligned actions |
| One heading has suddenly become italic and acquired a third font | Restrained font families and emphasis that serves the design |
| The eyebrow explains the heading, which explains the paragraph | Removal of redundant copy and decoration when within scope |

A hero heading can still be large. A caption can still be small. A destructive button should still look destructive. Consistency is allowed to have context.

Ordinary sections should share a type scale, rather than inventing five or ten sizes for equivalent text. Creative sections can still change the pace: oversized statements, expressive layouts, and animated typography should keep their character. The skill checks whether a difference has a purpose before trying to normalize it.

For a new site, the default is one or two font families and two or three core button styles, with deliberate size variants where needed. A wider-screen marketing hero generally benefits from one strong line or two to three composed lines. These are starting points, not reasons to break a mobile layout. Sections should share a rhythm; they do not all need the same height.

And yes, a common font can be the right font. It just needs a reason beyond “we always end up here.”

## Install

With Node.js and npm installed, run this from your project folder:

```bash
npx skills add Sandith02/ocd-ui
```

Choose your coding agent and installation options. The Skills CLI downloads the skill from this repository.

For Codex explicitly:

```bash
npx skills add Sandith02/ocd-ui --agent codex
```

Add `--global` to install for your user across projects.

No runtime dependency in your website. No API key required by the skill. Your agent and its tools keep their own costs.

<details>
<summary>I would like to install it manually, for some reason.</summary>

For local Codex CLI or IDE use, run this from your project root if the destination does not already exist:

```bash
mkdir -p .agents/skills
git clone https://github.com/Sandith02/ocd-ui.git .agents/skills/ocd-ui
```

Or use **Code → Download ZIP**, extract it, and copy the contents into `.agents/skills/ocd-ui/`. Keep `SKILL.md` directly inside that folder, with `references/`, `agents/`, and `assets/` beside it.

For use across your local projects, put the folder in `~/.agents/skills/ocd-ui/` instead. Back up an existing installation before replacing it.

</details>

## Give it something to stare at

In Codex, invoke it with `$ocd-ui`:

**Before the page develops several personalities:**

```text
Use $ocd-ui while building this page. Choose typography that fits the brief,
establish shared content widths, section spacing, a type scale, and a button
family. Keep headings deliberate and copy concise. Inspect the rendered result.
```

**After the page has developed several personalities:**

```text
Use $ocd-ui to review this page's widths, section rhythm, heading wraps,
typography, and buttons. Flag unnecessary text or decoration and accidental
differences between equivalent roles. Report findings without editing.
```

**For that one thing you cannot unsee:**

```text
Use $ocd-ui to fix this button's text and icon alignment against the reference.
Preserve the font and verify the result with a longer label.
```

**For the finishing pass you usually do yourself:**

```text
Use $ocd-ui to polish this page. Fix inconsistent button heights, nested
control insets, section widths, and unbalanced columns. Improve heading wraps
and shorten redundant marketing copy without changing its meaning. Remove
unnecessary decorative emphasis and dividers. Preserve the brand and verify
the result at desktop and mobile sizes.
```

Use your host's documented invocation method in other agents. The core instructions are host-neutral; agent-by-agent behavior has not been verified.

## Under the hood

The instructions live in [SKILL.md](SKILL.md). The supporting references cover [page composition and content restraint](references/page-composition.md), [typography](references/typography.md), [component relationships](references/component-patterns.md), and [visual consistency](references/visual-consistency.md).

The agent reads the existing design and code, checks the relevant relationships, makes scoped changes when asked, and verifies what it can.

Browser or screenshot tools are needed for visual inspection; this skill does not supply them. Source code alone cannot prove that an icon looks centered. A screenshot alone cannot explain which CSS rule committed the crime.

It also asks the agent to stop when the issue is resolved. There is a point where you are just moving it left and right.

## Is it actually good?

Early version. Installation has been tested, and the instructions have passed basic structure and source-review checks. Visual improvements have not been benchmarked across models.

Try the same task in fresh sessions with the same model and tools, once with the skill and once without. Compare the screenshots, changes, and regressions. Include a component that already looks right. Leaving it alone is also a result.

Useful cases include an unevenly inset navbar CTA, repeated buttons with accidental height differences, an awkwardly wrapped hero, and sections with drifting gutters. Include deliberate exceptions too: a full-bleed image, a shorter logo strip, and meaningful italic emphasis. Check whether the agent fixes the drift while preserving those choices and keeping longer labels usable.

No promise of pixel perfection. We have all met `line-height`.

## Contributing

Found something it missed? Open an issue with the component, expected result, agent/model, and what happened. A small reproducible example and screenshots help. Use examples you have permission to share.

Pull requests should explain the problem and how the revised instructions were tested. “Feels better” can start the conversation. Show us where.

## License

[MIT](LICENSE). Created by [Sandith Sithmaka Thenuwara](https://github.com/Sandith02).

You may now inspect the spacing in this README.
