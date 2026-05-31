<div align="right">

[English](README.md) · 中文 · [日本語](README-ja.md) · [한국어](README-ko.md) · [Русский](README-ru.md)

</div>

# general-readme-skill

> 使用 AI 编程助手为任何项目生成专业的 README 文件

![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-blue?style=flat)

## 功能特性

| 功能 | 描述 |
|---|---|
| 多种写作风格 | 三种写作配置：活力型、简约型和专业型 |
| 徽章系统 | 自动生成 shields.io 徽章，支持三种视觉样式 |
| 多语言支持 | 支持生成英文、中文、日文、韩文、俄文等 README 文件 |
| 零依赖 | 无需外部 CLI、运行时或网络服务 |
| 多平台支持 | 兼容 Claude Code、GitHub Copilot 和 Cursor |
| 隐私保护 | 自动屏蔽敏感密钥、密码和私人信息 |

## 快速开始

### Claude Code

```bash
mkdir -p .claude/skills/general-readme
cp SKILL.md .claude/skills/general-readme/
cp -r references/ .claude/skills/general-readme/
```

### GitHub Copilot

```bash
mkdir -p .github
cp SKILL.md .github/copilot-instructions.md
cp -r references/ .github/copilot-instructions/references/
```

### Cursor

```bash
mkdir -p .cursor/rules
cp SKILL.md .cursor/rules/general-readme.mdc
cp -r references/ .cursor/rules/references/
```

## 使用方法

在 AI 编程助手中输入 `/readme` 或说 "generate readme"。技能将引导你完成：

1. **配置** — 选择写作风格、徽章样式和语言
2. **项目扫描** — 自动检测项目类型、技术栈和结构
3. **生成** — 按照倒金字塔结构创建 README
4. **输出** — 生成主文件和翻译版本

### 支持的命令

| 命令 | 描述 |
|---|---|
| `/readme` | 触发 README 生成 |
| `generate readme` | 自然语言触发 |
| `write readme` | 自然语言触发 |
| `帮我写 README` | 中文语言触发 |
| `更新README` | 更新现有 README |

## 项目结构

```
general-readme-skill/
├── SKILL.md                # 主技能定义文件
├── examples/               # 示例 README 文件
│   ├── app-readme.md       # 全栈应用示例
│   ├── cli-readme.md       # CLI 工具示例
│   └── library-readme.md   # 库/包示例
├── install/                # 安装指南
│   ├── claude-code.md      # Claude Code 设置
│   ├── copilot.md          # GitHub Copilot 设置
│   └── cursor.md           # Cursor 设置
└── references/             # 参考文件
    ├── badges.md           # 技术徽章映射
    ├── badge-styles.md     # 徽章布局规则
    ├── diagram-templates.md # Mermaid/SVG 模板
    ├── language-guide.md   # 多语言规则
    ├── section-guidelines.md # 章节写作规则
    └── tone-profiles.md    # 写作风格定义
```

## 技术栈

### 文档

| 技术 | 用途 |
|---|---|
| Markdown | 主要内容格式 |
| shields.io | 徽章生成 |
| Mermaid | 架构图 |

### 支持平台

| 平台 | 集成方式 |
|---|---|
| Claude Code | `.claude/skills/` 目录 |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | `.cursor/rules/` 目录 |

## 贡献

1. Fork 仓库
2. 创建功能分支 (`git checkout -b feature/amazing`)
3. 提交更改 (`git commit -m 'feat: add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing`)
5. 打开 Pull Request

## 许可证

未检测到 LICENSE 文件。请添加 LICENSE 以明确项目许可。
