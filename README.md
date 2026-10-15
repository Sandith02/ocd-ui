# OCD UI

An AI agent skill for deliberate typography, precise alignment, and consistent UI.

OCD UI helps agents notice the details that make an interface feel unfinished: equivalent section headings with different sizes, near-duplicate button styles, poorly matched font choices, and text or icons that look off-center.

Use it while building or to review an existing interface. It guides the agent through the existing design system, source code, rendered result, scoped corrections, and verification. It works with frontend code regardless of framework; it is not a React component library or a CSS runtime.

## Status

Early experimental version. The skill structure has been validated, but visual improvements have not been benchmarked across models. Results depend on the model, tools, and references. Review its suggestions; pixel-perfect output is not guaranteed.

## Requirements

- A coding agent that can load SKILL.md instructions.
- Source access for implementation changes.
- Browser or screenshot tools for visual inspection. The skill does not install or supply those tools.

There is no runtime package to add to your website and no API key required by this skill. Your agent and any optional tools retain their own costs and access requirements.

## Install in Codex CLI or IDE

From your project root, if the destination does not already exist:

```bash
mkdir -p .agents/skills
git clone https://github.com/Sandith02/ocd-ui.git .agents/skills/ocd-ui
```

Or install manually:

Download the repository using **Code → Download ZIP**, extract it, and copy its contents into `.agents/skills/ocd-ui/` inside your project. `SKILL.md` must be directly inside that folder, with `references/`, `agents/`, and `assets/` beside it. Do not leave an extra repository folder between `ocd-ui/` and `SKILL.md`.

For availability across your local projects, use `~/.agents/skills/ocd-ui/` instead. Keep any existing installation backed up before replacing it.

Invoke it explicitly:

```text
Use $ocd-ui to review this button's text and icon balance.
Report findings before changing anything.
```

```text
Use $ocd-ui to fix this counter's alignment against the reference.
Preserve the font and check single-, double-, and triple-digit values.
```

```text
Use $ocd-ui while building this component from my reference.
Check the rendered typography and alignment before finishing.
```

For page-wide consistency:

```text
Use $ocd-ui to review the typography and buttons across this page.
Find accidental differences between equivalent roles. Keep the hero hierarchy
and meaningful button variants. Explain proposed changes before editing.
```

For font direction during a new build:

```text
Use $ocd-ui while building this page. Choose typography that fits the brief,
establish a reusable type scale and button family, and inspect the result.
```

For other hosts, follow their documented skill installation process. The core instructions are host-neutral; compatibility with other hosts has not been verified.

## What it checks

- Font choices suited to the brief, font loading, weights, line boxes, and wrapping.
- Consistent role-based type scales across equivalent sections.
- Shared button variants, padding, radii, label styles, and icon spacing.
- Container geometry, padding, shared edges, gaps, and baselines.
- Visible text/icon balance beyond element bounding boxes.
- Relevant viewport and content variants after a change.

Consistency means matching equivalent roles, not making every heading the same size or every button identical. Brand fonts, intentional asymmetry, responsive sizing, and meaningful variants stay intact. Common fonts are not automatically bad choices.

It separates verified defects, subjective refinements, and unknowns. Screenshot-only feedback cannot establish the exact CSS cause. Source-only feedback cannot establish visual correctness.

## Evaluate it

Start from the same unchanged component and prompt in separate sessions, using the same model and tools, once with the skill and once without it. Save the resulting diffs and screenshots at matching sizes and states.

Include the three component patterns in `references/component-patterns.md`, a component with no defect, intentional asymmetry, an unloaded font, and a longer-label/mobile case. Assess whether the result addresses the actual issue, preserves design intent and usability, avoids unnecessary changes, and accurately reports verification limits. Record regressions and false positives as well as improvements. Repeat before making broad claims.

## Contributing

Open an issue with the component, expected result, agent/model used, and what went wrong. Screenshots and a small reproducible example help. Share only examples you have permission to publish. Pull requests should explain the failure they address and how the revised instructions were tested.

## License

[MIT](LICENSE). Created by Sandith Sithmaka Thenuwara.
