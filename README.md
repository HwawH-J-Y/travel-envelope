# Travel Envelope Skill

`travel-envelope` is a Codex skill for turning travel photos into vintage envelope collages. It keeps the destination photo visible as a full-bleed background and arranges selected memories inside a paper envelope with varied, nonrepeating treatments.

## What it does

- Selects a scenic source photo as a flat, full-bleed background.
- Derives the envelope paper color from the background palette.
- Uses clean borderless cutouts for people, food, and recognizable objects.
- Mixes restrained treatments such as Polaroids, film strips, torn prints, stamps, slides, and matte photos without repeating the same subject across separate elements.
- Keeps the envelope around 58–68% of the canvas width so the scenery remains visible.
- Uses an asymmetrical internal layout, with the principal person offset from the centerline.
- Allows subtle decorative postmarks and compact destination typography.
- Adds one or two small destination-specific accents when fewer than roughly five useful foreground elements are available.

## Install

Copy the `travel-envelope` directory into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R travel-envelope ~/.codex/skills/travel-envelope
```

Restart Codex if the skill does not appear immediately.

## Use

Upload the original travel photos and ask Codex to use `$travel-envelope`.

Example:

```text
Use $travel-envelope to turn these London photos into one portrait travel collage.
Use the park photo as the background and title the envelope “London”.
```

The skill expects original travel photos. Finished collages can be supplied as style references, but their people, objects, landmarks, and text are not reused as source content.

## Output style

The default result is a portrait 3:4 composition with:

- a recognizable scenic background;
- a centered open envelope slightly below the middle;
- an independent flat collage layer with no floor contact or background-perspective relationship;
- framed photos behind, borderless cutouts in the middle, and smaller details near the pocket;
- a quiet destination title or `Travel Journal` treatment on the envelope front.

Image generation is not pixel-exact compositing. The skill asks the model to preserve identity and source appearance, but deterministic cutout software is more appropriate when unchanged source pixels are required.

## Files

- `travel-envelope/SKILL.md` — skill instructions
- `travel-envelope/agents/openai.yaml` — Codex display metadata
