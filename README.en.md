# Travel Envelope

[中文](README.md) | **English**

`travel-envelope` is a Codex Skill that turns travel photos into vintage envelope collages. It preserves a full scenic background while arranging memories of people, landmarks, tickets, food, and transportation inside a tactile paper envelope, making it suitable for travel journals and social media posts.

## Features

- Automatically selects a scenic photo as the full-bleed background while keeping the setting recognizable.
- Derives a pale, low-saturation envelope paper color from the background palette.
- Uses natural, borderless cutouts for people, food, and clearly outlined objects.
- Combines Polaroid-style frames, film strips, torn-edge photos, postage-stamp borders, and slide frames without repeating the same subject across separate collage elements.
- Keeps the envelope at roughly 58-68% of the canvas width by default, leaving generous room for the surrounding scenery.
- Centers the envelope while arranging its contents asymmetrically, with the main person slightly offset from the centerline.
- Supports subtle decorative postmarks and a small destination title.
- May add a few small destination-themed accents when fewer than about five useful foreground elements remain or the source material lacks variety. These accents are decorative and do not represent real photographed memories.

## Requirements

- A Codex environment that supports Skills and can call the built-in `image_gen` image-generation tool. Installing this Skill does not install or unlock the image-generation tool itself.
- Original travel photos, including at least one scenic image suitable for the background and one foreground image.
- The Skill has not yet been verified across every account and client. Other AI tools may require adaptation for their own image-generation interfaces.

## Download and Installation

The repository root is the Skill directory itself: `SKILL.md` and `agents/` are located directly at the root, with no additional `travel-envelope/` directory nested inside it. Opening or sharing the GitHub link alone does not install the Skill.

### Option 1: Ask Codex to install it

Send the following message to Codex:

```text
Please use $skill-installer to install the Skill from https://github.com/HwawH-J-Y/travel-envelope.
SKILL.md is located at the repository root. Install it as travel-envelope and preserve agents/openai.yaml.
```

### Option 2: Download the ZIP and install it manually

1. Open the [repository homepage](https://github.com/HwawH-J-Y/travel-envelope) and select **Code -> Download ZIP**.
2. Extract the ZIP file. The resulting folder is usually named `travel-envelope-main`; opening it should reveal `SKILL.md` and the `agents` folder directly.
3. Rename `travel-envelope-main` to `travel-envelope`.
4. Move the entire folder into `.agents/skills/` under your home directory. Create the directory first if it does not exist. `~` represents your home directory. On macOS, use **Go -> Go to Folder** in Finder to open `~/.agents/skills/`. On Windows, create `.agents` and `skills` folders under your user home directory.
5. If a Skill with the same name already exists, inspect or back up the old directory before deciding whether to replace it. Do not place the new folder inside the old one.

The installed directory should look like this:

```text
~/.agents/skills/
└── travel-envelope/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── README.md
    └── README.en.md
```

### Option 3: Install with Git on macOS or Linux

If Git is installed, run the following commands for a first-time installation:

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/HwawH-J-Y/travel-envelope.git ~/.agents/skills/travel-envelope
```

Git will stop if the target directory already exists, so inspect the existing installation first.

Codex should automatically discover the newly installed Skill. If it does not appear, restart Codex and confirm that `SKILL.md` is located directly inside `travel-envelope/`, without an extra nested directory. See the [official OpenAI documentation](https://learn.chatgpt.com/docs/build-skills) for Skill installation locations and loading behavior.

## Usage

After installation, upload your original travel photos and reference `$travel-envelope` in your request:

```text
Use $travel-envelope to turn these travel photos into a portrait travel-envelope journal.
The destination is London. Use the park photo as the background and title the envelope "London."
```

A finished collage may be supplied as a style reference, but its people, objects, landmarks, and text will not be extracted or reused as source material for your photos.

## Visual Style

By default, the Skill generates one portrait 3:4 collage:

- Recognizable scenery remains visible around the collage.
- An open envelope is centered slightly below the middle of the canvas.
- The envelope is an independent collage layer that does not touch the ground or share perspective with the background scene.
- Framed photos sit at the back, natural cutouts occupy the middle, and smaller objects appear near the envelope opening.
- The envelope front uses a restrained destination title or the words `Travel Journal`.

This workflow uses AI image-generation compositing rather than pixel-exact assembly. The Skill instructs the model to preserve each person's identity and the appearance of the supplied material. If the original pixels must remain completely unchanged, use deterministic cutout and layout software instead.

## Repository Files

All paths below are relative to the repository root:

- [SKILL.md](SKILL.md) - Skill instructions
- [agents/openai.yaml](agents/openai.yaml) - Display name and default prompt
- [README.md](README.md) - Chinese documentation
- [README.en.md](README.en.md) - English documentation
