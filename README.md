# UI/UX Design Fundamentals — Claude Skill

A Claude Code skill that teaches AI agents professional UI/UX design rules, extracted from
["Every UI/UX Concept Explained in Under 10 Minutes"](https://www.youtube.com/watch?v=EcbgbKtOELY) by Kole Jain (Vi Media).

## What it does

When building any frontend UI — cards, landing pages, dashboards, dark mode, buttons, inputs,
overlays — this skill automatically applies 50+ design rules covering:

| Chapter | Topic |
|---------|-------|
| 1 | Affordances & Signifiers |
| 2 | Visual Hierarchy |
| 3 | Grids, Layouts & Spacing (4-point grid) |
| 4 | Typography & Font Sizing |
| 5 | Color Theory |
| 6 | Dark Mode |
| 7 | Shadows & Depth |
| 8 | Icons & Buttons |
| 9 | Feedback & States |
| 10 | Micro Interactions |
| 11 | Overlays & Image Text |

## Benchmark Results

Tested with 3 eval cases comparing with-skill vs without-skill outputs:

| Metric | With Skill | Baseline |
|--------|-----------|----------|
| Pass rate | **94.4%** (17/18) | 77.8% (14/18) |

Key improvements: blue price coloring, icon-based labels, proper dark mode surface elevation,
negative letter-spacing on headings, 2:1 button padding ratio, 4-point grid spacing.

## Install

### Claude Code (CLI)

Copy the `uiux-design-fundamentals/` folder to your skills directory:

```bash
cp -r uiux-design-fundamentals ~/.claude/skills/
```

### Claude.ai

1. Download and zip the `uiux-design-fundamentals/` folder
2. Go to Claude.ai > Settings > Capabilities > Skills
3. Click "Upload skill" and select the zip

## Skill Structure

```
uiux-design-fundamentals/
  SKILL.md                        # Core rules (loaded into context)
  references/
    css-patterns.md               # CSS code patterns (loaded on demand)
  evals/
    evals.json                    # Test case definitions
```

## License

MIT
