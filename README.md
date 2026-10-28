# pptskill

一个用于 PPT 制作的中文技能，适合需要先确认内容和制作方案、再开始制作的工作流。

适用任务：制作或修改可编辑 PPT、生成整页 PPT 风格图片、将图片重建为可编辑 PPT。

## 如何工作

1. 读取技能附带的制作习惯，以及本次提供的大纲、正文、模板和参考图。
2. 提出具体计划，说明页数、逐页内容、视觉风格和交付方式。
3. 用户确认计划后，再制作和检查结果。

同一任务中已经确认的计划持续有效，不重复要求确认。用户当次明确要求直接制作或跳过计划时，以当次指令为准。

## 在 Codex 中安装

下载本仓库并解压，将里面的 `pptskill` 文件夹完整复制到个人技能目录：

- Windows：`%USERPROFILE%\.agents\skills\`
- macOS / Linux：`~/.agents/skills/`

安装后的目录应为 `.agents/skills/pptskill/SKILL.md`，并保留旁边的 `references` 文件夹。

Codex 会自动发现技能；若没有显示，重启 Codex。然后在对话中调用：

```text
$pptskill 请根据我提供的大纲和模板制作 PPT，先给出制作计划。
```

也可以在 Codex 中让 `$skill-installer` 从 GitHub 安装：

```text
$skill-installer 安装 https://github.com/chenchen4511/pptskill/tree/main/pptskill
```

目录和调用方式参见 [OpenAI 官方技能说明](https://learn.chatgpt.com/docs/build-skills)。

## 内置的制作习惯

- 内容以当次提供的材料和最新要求为依据，合并页面时保留非重复的实质信息。
- 配图优先从用户提供的材料中提取。
- 中文默认使用微软雅黑；优先直角方框，同层级保持字号、位置和对齐一致。
- 整套风格统一，布局可以根据内容变化；局部修改尽量保留原布局。
- 整页图片每页独立生成，检查实际尺寸和文字清晰度。
- 区分图片封装版和逐元素可编辑版，按实际编辑能力交付。

这些偏好来自作者的使用习惯，可在 `pptskill/references/ppt-preferences.md` 中修改；本次用户的明确要求优先。

## 工具要求

本技能提供流程和制作偏好。生成图片、制作可编辑 PPT、提取配图和渲染检查，需要运行环境提供相应工具；安装本技能不会自动安装这些工具。

## 案例

[下载：英国谢菲尔德 AMRC 案例研究](examples/英国谢菲尔德AMRC案例研究.pptx)

这是一份用户提供的单页案例 PPT，可用于查看内容组织和版式。案例中的主题、页数和布局仅适用于该案例，新任务仍以当次材料与确认后的计划为准。

## 仓库结构

```text
.
├── README.md
├── LICENSE
├── examples/
│   └── 英国谢菲尔德AMRC案例研究.pptx
└── pptskill/
    ├── SKILL.md
    └── references/
        └── ppt-preferences.md
```

## 许可证

[MIT License](LICENSE)。
