# Travel Envelope

**English** | [中文](README.zh-CN.md)

`travel-envelope` is a Codex Skill that turns original travel photos into a vintage envelope collage. It keeps the destination scenery recognizable and layers photos, cutouts, food, tickets, transportation, and small local details inside a tactile paper envelope for travel journals and social posts.

## Features

- Selects a scenic source photo as the full-bleed background.
- Derives a pale, low-saturation paper color from the background palette.
- Keeps the envelope within roughly 58–68% of the canvas width so the scenery remains visible.
- Treats the envelope as a floating collage layer, with no road or floor contact and no grounding shadow on the background.
- Builds a compact, asymmetrical cluster with real overlap between framed photos, film strips, cutouts, objects, and the envelope pocket.
- Preserves supplied triptychs and related portrait sequences as one film strip in their original order.
- Does not require a person. If no suitable portrait is available, the strongest supplied landmark, architecture, food, transportation, ticket, or travel object becomes the off-center focal subject.
- When fewer than five useful foreground elements are available and a destination is supplied, automatically adds one to three small destination-specific accents near the envelope opening.
- Uses a restrained destination title and optional decorative postmark without inventing dates, ticket data, or personal memories.

## Requirements

- A Codex environment that supports Skills and the built-in `image_gen` tool. Installing this repository does not install or unlock image generation.
- Original travel photos, including at least one scenic image suitable for the background and one foreground image.

## Installation

The repository root is the Skill directory. `SKILL.md` and `agents/` are located directly at the top level; there is no extra nested `travel-envelope/` folder.

### Ask Codex to install it

```text
Please use $skill-installer to install the Skill from https://github.com/HwawH-J-Y/travel-envelope.
SKILL.md is located at the repository root. Install it as travel-envelope and preserve agents/openai.yaml.
```

### Download ZIP

1. Select **Code → Download ZIP** on the repository page.
2. Extract `travel-envelope-main` and rename it to `travel-envelope`.
3. Move the folder to `~/.agents/skills/travel-envelope/`.
4. Confirm that `SKILL.md` is directly inside that folder, without another nested directory.

### Install with Git

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/HwawH-J-Y/travel-envelope.git ~/.agents/skills/travel-envelope
```

If a folder with that name already exists, inspect or back it up before replacing it. Restart Codex if the newly installed Skill does not appear.

## Usage

Upload the original travel photos and mention `$travel-envelope`:

```text
Use $travel-envelope to turn these travel photos into one portrait envelope collage.
The destination is London. Use the park photo as the background and title the envelope London.
```

A completed collage may be supplied as a style reference, but its people, objects, landmarks, and wording are not reused as source content.

## Default output

The default result is one portrait 3:4 collage with recognizable scenery, a thin nearly front-facing envelope, an off-center focal subject, layered occlusion, and a quiet destination title. A person is optional. This workflow uses AI image compositing rather than pixel-exact assembly; use deterministic cutout and layout software when the original pixels must remain unchanged.

## Repository files

- [SKILL.md](SKILL.md) — Skill instructions
- [agents/openai.yaml](agents/openai.yaml) — display name and default prompt
- [README.md](README.md) — default English documentation
- [README.zh-CN.md](README.zh-CN.md) — Chinese documentation
- [README.en.md](README.en.md) — compatibility link to the default English README
