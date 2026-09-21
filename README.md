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

## 下载与安装 / Download and install

本仓库根目录就是 Skill 目录：`SKILL.md` 与 `agents/` 直接位于根目录，仓库内部没有额外一层 `travel-envelope/`。仅打开或分享 GitHub 链接不会自动安装。

The repository root is the skill directory. There is no nested `travel-envelope/` folder inside it.

### 方法一：让 Codex 安装

将下面的话发送给 Codex：

```text
请用 $skill-installer 安装 https://github.com/HwawH-J-Y/travel-envelope 中的 Skill。
SKILL.md 位于仓库根目录，请将它安装为 travel-envelope，并保留 agents/openai.yaml。
```

### 方法二：下载 ZIP 手动安装

1. 打开[仓库首页](https://github.com/HwawH-J-Y/travel-envelope)，点击 **Code → Download ZIP**。
2. 解压下载的 ZIP。解压后的文件夹通常叫 `travel-envelope-main`；打开后应直接看到 `SKILL.md` 和 `agents` 文件夹。
3. 将 `travel-envelope-main` 改名为 `travel-envelope`。
4. 将整个 `travel-envelope` 文件夹放入用户主目录下的 `.agents/skills/`；目录不存在时先创建。`~` 表示你的用户主目录。macOS 的 Finder 可用“前往 → 前往文件夹”打开 `~/.agents/skills/`；Windows 可在用户主目录下创建 `.agents` 和 `skills` 文件夹。
5. 如果已经有同名 Skill，先检查或备份旧目录，再决定是否替换；不要把新文件夹套进旧的 `travel-envelope` 里面。

Download **Code → Download ZIP**, extract it, rename `travel-envelope-main` to `travel-envelope`, and move the whole folder into `~/.agents/skills/`.

安装完成后的结构应为：

```text
~/.agents/skills/
└── travel-envelope/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── README.md
```

### 方法三：Git 安装（macOS / Linux）

已安装 Git 的用户，首次安装时可以运行：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/HwawH-J-Y/travel-envelope.git ~/.agents/skills/travel-envelope
```

如果目标目录已存在，Git 会停止；请先检查现有安装。

Codex 会自动发现新安装的 Skill。如果没有出现，请重启 Codex，并确认 `SKILL.md` 直接位于 `travel-envelope/` 下，没有多套一层文件夹。安装目录与加载方式见 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills)。

### 使用条件 / Requirements

- 需要支持 Skill 且能调用内置 `image_gen` 图片生成工具的 Codex 环境。安装本 Skill 本身不会安装或解锁生图工具。
- 请上传原始旅行照片，至少包括一张适合作背景的风景照片和一张前景照片。
- 尚未在所有账号和客户端上完成验证；其他 AI 工具可能需要适配其生图接口。

This skill requires a Codex environment with the built-in `image_gen` tool. Installing the skill does not grant image-generation access.

## Use

Upload the original travel photos and ask Codex to use `$travel-envelope`.

Example:

```text
Use $travel-envelope to turn these London photos into one portrait travel collage.
Use the park photo as the background and title the envelope “London”.
```

中文示例：

```text
使用 $travel-envelope，把这些旅行照片做成一张竖版信封旅行手账。
目的地是伦敦，以公园照片为背景，信封标题写 London。
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

## Files / 仓库文件

以下路径均相对于仓库根目录（paths relative to the repository root）：

- [SKILL.md](SKILL.md) — Skill 指令 / skill instructions
- [agents/openai.yaml](agents/openai.yaml) — 展示名称和默认提示语 / Codex display metadata
- [README.md](README.md) — 下载、安装和使用说明 / download, installation, and usage guide
