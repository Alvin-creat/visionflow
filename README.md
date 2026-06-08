# Image Prompt Extractor

一个 Claude Code Skill —— 上传任何图片，自动反推/生成高质量的 AI 绘图 prompt。

## 能做什么

- 🔍 **AI 生图反推**：上传一张 AI 生成的图，还原接近原始的 prompt
- 📷 **照片转 prompt**：上传真实照片，生成可在 Midjourney / SD / DALL·E 中复现的描述
- 🎨 **风格提取**：分析插画、设计稿的艺术风格，输出精准的 style keywords
- 🎯 **多平台适配**：自动识别 Midjourney / Stable Diffusion / DALL·E / Flux / ComfyUI 格式

## 触发方式

在对话中直接说，例如：

- 「帮我提取这张图的提示词」
- 「what's the prompt for this image?」
- 「这张插画是什么风格？给我 SD 的 prompt」
- 「reverse engineer this image, I want to recreate it in Flux」

## 安装

### 方式一：项目级（推荐）

将整个文件夹放到你的项目根目录下的 `.claude/skills/` 中：

```
your-project/
└── .claude/
    └── skills/
        └── image-prompt-extractor/
            ├── SKILL.md
            └── references/
```

### 方式二：全局安装

```bash
claude plugin install image-prompt-extractor.skill
```

## 文件结构

```
image-prompt-extractor/
├── SKILL.md                         # 核心工作流 + 触发描述
├── references/
│   ├── prompt-styles.md             # 5 大平台 prompt 参数参考
│   └── visual-analysis-guide.md     # 图像分析方法论
└── README.md
```

## 许可

MIT
