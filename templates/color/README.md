# Color Reskin Samples

**Look up colors here, not structure.**

The source of truth for rendering code, geometry and animation is always the four galleries in the root of `templates/`. The color samples are reskinned versions of them, node for node on the same data and motion. Copying structure from here is a detour and easy to drift.

The source of truth for the built-in preset color values is `color-presets.js`. The scattered notes in the sample headers (ink-addition factor, palette order) are only self-description; the rules themselves are in `SKILL.md`, Section 6.5. The agent may choose a preset automatically from the data structure and the use case, and the user does not need to trigger color first. One HTML file or one set of deliverables may use only one color system, and mixing presets is forbidden. After receiving the finished work, the user can keep adjusting the colors, but contrast, visual hierarchy and data semantics must be rechecked.

## Custom is not a fourth built-in preset

When the user explicitly provides a brand color, a hex value or a complete palette, you may build a `CUSTOM` palette for that deliverable by the role rules in `SKILL.md`. It does not appear here, because no single custom sample can hold for every user. A custom palette must not borrow colors from the three built-in presets to fill out its roles, and must not be written back to `color-presets.js`, unless the user explicitly asks to fix the brand color as a project-level preset.

The four Treemap implementations are already in the Basics gallery: Mono groups by parent title bands and whitespace; Porcelain uses lightness for ordered parent groups; Palm uses hue for top-level categories; Wire gives only one leaf the fluorescent orange.

## The three presets

| File | Color system | Color logic | Fits |
| - | - | - | - |
| `*-porcelain.html` | Celadon blue | Single-hue lightness ladder | Ordered data, single series |
| `*-palm.html` | Palm green | Hue = category | Unordered categories ≤4 (5–6 barely) |
| `*-wire.html` | Editorial red | Grayscale + one fluorescent orange | Almost any occasion that needs one focal point |

Each preset has four galleries (basics / glance / lupi / maps), 12 in total, with no gaps. The map samples are only useful when the user explicitly asks for a map.

archive (terracotta gray-green) is archived and no longer a candidate. It and palm are both "hue = category", so their functions overlap.

## The three interactive large charts

`big-circular` / `big-force` / `big-threads` exist only in porcelain and palm, with no wire version.

Reason: wire is already black-and-gray grayscale plus one fluorescent orange, and it differs from the original Mono large charts only in the accent color, so building it would be nearly a duplicate. For a wire-style large chart, use the originals in the root of `templates/` directly.

These three are **dark-background charts**, and their color logic differs from the light cards. The card background is pressed darker, and an 8-step single-hue ladder from bright to dark encodes "how far from the core" (bright = core), not categories. The color values are in the `DARK` block of each preset in `color-presets.js`.

Why hue is not used for categories: these three need 5 / 8 / three-column tier structures, which exceeds the capacity limit of the palm green-yellow range (≤6). Following the rule of Gate 1 in SKILL.md, only a single-hue lightness ladder is possible.

The hover highlight of `big-threads` changes opacity (the line is always `DK8[0]`) and does not use `DARK.HL`.
