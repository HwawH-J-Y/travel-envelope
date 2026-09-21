# Travel Envelope · 信封旅行手账

**中文** | [English](README.en.md)

`travel-envelope` 是一个将旅行照片整理成复古信封拼贴的 Codex Skill。它保留完整的风景背景，把人物、地标、票据、美食和交通等回忆错落地收进纸质信封，适合旅行记录和社媒发图。

## 功能

- 自动选择风景照片作为铺满画面的背景，保留可辨认的景色。
- 从背景配色中提取灵感，生成浅淡、低饱和的信封纸色。
- 对人物、食物和轮廓清晰的物件使用自然无白边抠图。
- 搭配拍立得、胶片条、撕边照片、邮票边框或幻灯片框，同一主体不在不同拼贴元素中重复。
- 信封宽度默认约占画面的 58–68%，为周围风景留出空间。
- 信封居中，内部采用不对称构图，让主要人物略微偏离中线。
- 支持淡雅的装饰邮戳和小尺寸目的地标题。
- 素材不足约五个有效前景元素或类型单一时，可少量补充目的地装饰物；这些装饰不代表真实拍摄的回忆。

## 使用条件

- 需要支持 Skill 且能调用内置 `image_gen` 图片生成工具的 Codex 环境。安装本 Skill 不会安装或解锁生图工具。
- 上传原始旅行照片，至少包括一张适合作背景的风景照片和一张前景照片。
- 尚未在所有账号和客户端上完成验证；其他 AI 工具可能需要适配其生图接口。

## 下载与安装

本仓库根目录就是 Skill 目录：`SKILL.md` 与 `agents/` 直接位于根目录，仓库内部没有额外一层 `travel-envelope/`。仅打开或分享 GitHub 链接不会自动安装。

### 方法一：让 Codex 安装

将下面的话发送给 Codex：

```text
请用 $skill-installer 安装 https://github.com/HwawH-J-Y/travel-envelope 中的 Skill。
SKILL.md 位于仓库根目录，请将它安装为 travel-envelope，并保留 agents/openai.yaml。
```

### 方法二：下载 ZIP 手动安装

1. 打开[仓库首页](https://github.com/HwawH-J-Y/travel-envelope)，点击 **Code → Download ZIP**。
2. 解压 ZIP。解压后的文件夹通常叫 `travel-envelope-main`，打开后应直接看到 `SKILL.md` 和 `agents` 文件夹。
3. 将 `travel-envelope-main` 改名为 `travel-envelope`。
4. 将整个文件夹放入用户主目录下的 `.agents/skills/`；目录不存在时先创建。`~` 表示用户主目录。macOS 的 Finder 可用“前往 → 前往文件夹”打开 `~/.agents/skills/`；Windows 可在用户主目录下创建 `.agents` 和 `skills` 文件夹。
5. 如果已经有同名 Skill，先检查或备份旧目录再决定是否替换，不要把新文件夹套进旧文件夹。

安装完成后的结构应为：

```text
~/.agents/skills/
└── travel-envelope/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── README.md
    └── README.en.md
```

### 方法三：Git 安装（macOS / Linux）

已安装 Git 的用户，首次安装时可以运行：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/HwawH-J-Y/travel-envelope.git ~/.agents/skills/travel-envelope
```

如果目标目录已存在，Git 会停止；请先检查现有安装。

Codex 会自动发现新安装的 Skill。如果没有出现，请重启 Codex，并确认 `SKILL.md` 直接位于 `travel-envelope/` 下，没有多套一层文件夹。安装目录与加载方式见 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills)。

## 使用方法

安装后上传旅行原图，在请求中指定 `$travel-envelope`：

```text
使用 $travel-envelope，把这些旅行照片做成一张竖版信封旅行手账。
目的地是伦敦，以公园照片为背景，信封标题写 London。
```

成品拼贴可以作为风格参考，但不会提取其中的人物、物件、地标或文字作为你的照片素材。

## 画面风格

默认生成一张 3:4 竖版拼贴：

- 周围保留可辨认的风景；
- 打开的信封居中并略低于画面中央；
- 信封作为独立拼贴图层，不与背景地面接触或共用透视；
- 带框照片在后、自然抠图在中、小物件靠近信封开口；
- 信封正面使用克制的目的地标题或 `Travel Journal` 字样。

这是 AI 生图合成，不是像素级精确拼接。Skill 会要求保留人物身份和素材外观；如果需要原始像素完全不变，应使用确定性的抠图和排版软件。

## 仓库文件

以下路径均相对于仓库根目录：

- [SKILL.md](SKILL.md) — Skill 指令
- [agents/openai.yaml](agents/openai.yaml) — 展示名称和默认提示语
- [README.md](README.md) — 中文说明
- [README.en.md](README.en.md) — 英文说明
