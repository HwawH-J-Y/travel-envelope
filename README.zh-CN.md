# Travel Envelope · 信封旅行手账

[English](README.md) | **中文**

`travel-envelope` 是一个将旅行原图整理成复古信封拼贴的 Codex Skill。它保留可辨认的目的地风景，把照片、抠图、美食、票据、交通和当地小物件错落地收进纸质信封，适合旅行记录和社媒发图。

## 功能

- 自动选择适合的风景原图作为铺满画面的背景。
- 从背景配色中生成浅淡、低饱和的信封纸色。
- 信封宽度默认保持在画面的约 58–68%，为周围风景留出空间。
- 信封作为独立悬浮的拼贴层，不与道路或地面接触，也不向背景投射落地阴影。
- 带框照片、胶片条、自然抠图、小物件和信封开口之间形成真实的前后遮挡。
- 用户提供的三联照或相关人物连拍默认按原顺序保留为一条胶片。
- 不强制要求人物照片。没有合适人物照时，自动选择地标、建筑、美食、交通、票据或旅行物件作为偏离中线的主体。
- 已提供目的地且有效前景元素少于 5 个时，自动在信封开口附近补充 1–3 个小型当地物件。
- 使用克制的目的地标题和可选装饰邮戳，不虚构日期、票据信息或个人经历。

## 使用条件

- 需要支持 Skill 且能调用内置 `image_gen` 工具的 Codex 环境。安装本仓库不会安装或解锁生图工具。
- 上传旅行原图，至少包含一张适合作背景的风景照片和一张前景照片。

## 安装

本仓库根目录就是 Skill 目录，`SKILL.md` 和 `agents/` 直接位于最外层，没有额外嵌套一层 `travel-envelope/`。

### 让 Codex 安装

```text
请用 $skill-installer 安装 https://github.com/HwawH-J-Y/travel-envelope 中的 Skill。
SKILL.md 位于仓库根目录，请将它安装为 travel-envelope，并保留 agents/openai.yaml。
```

### 下载 ZIP

1. 在仓库页面点击 **Code → Download ZIP**。
2. 解压 `travel-envelope-main`，并将其改名为 `travel-envelope`。
3. 将文件夹移动到 `~/.agents/skills/travel-envelope/`。
4. 确认 `SKILL.md` 直接位于该文件夹内，没有多嵌套一层目录。

### 使用 Git 安装

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/HwawH-J-Y/travel-envelope.git ~/.agents/skills/travel-envelope
```

如果已有同名文件夹，请先检查或备份再决定是否替换。新安装的 Skill 没有出现时，可重启 Codex。

## 使用方法

上传旅行原图，并在请求中指定 `$travel-envelope`：

```text
使用 $travel-envelope，把这些旅行照片做成一张竖版信封旅行手账。
目的地是伦敦，以公园照片为背景，信封标题写 London。
```

成品拼贴可以作为风格参考，但不会提取其中的人物、物件、地标或文字作为照片素材。

## 默认效果

默认生成一张 3:4 竖版拼贴：周围保留可辨认的风景，信封接近正面且纸张轻薄，主体偏离中线，内部素材互相遮挡，标题保持克制。人物不是必需素材。这是 AI 图片合成而非像素级精确拼接；如果原始像素必须完全不变，请使用确定性的抠图和排版软件。

## 仓库文件

- [SKILL.md](SKILL.md) — Skill 指令
- [agents/openai.yaml](agents/openai.yaml) — 展示名称和默认提示语
- [README.md](README.md) — 默认英文说明
- [README.zh-CN.md](README.zh-CN.md) — 中文说明
- [README.en.md](README.en.md) — 兼容旧链接，跳转到默认英文说明
