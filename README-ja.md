<div align="right">

[English](README.md) · [中文](README-zh.md) · 日本語 · [한국어](README-ko.md) · [Русский](README-ru.md)

</div>

# general-readme-skill

> AI コーディングアシスタントを使用して、任意のプロジェクトのプロフェッショナルな README ファイルを生成

![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat&logo=claude&logoColor=white)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-blue?style=flat)

## 機能

| 機能 | 説明 |
|---|---|
| 複数のトーンサポート | 3つのライティングプロファイル：エナジェティック、ミニマル、プロフェッショナル |
| バッジシステム | 3つのビジュアルスタイルで shields.io バッジを自動生成 |
| 多言語対応 | 英語、中国語、日本語、韓国語、ロシア語などの README ファイルを生成 |
| ゼロ依存 | 外部CLI、ランタイム、ネットワークサービスは不要 |
| マルチプラットフォーム | Claude Code、GitHub Copilot、Cursor で動作 |
| プライバシー優先 | 機密キー、パスワード、個人情報を自動マスク |

## クイックスタート

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

## 使い方

AI コーディングアシスタントで `/readme` と入力するか、「generate readme」と話してください。スキルが以下をガイドします：

1. **設定** — トーンプロファイル、バッジスタイル、言語を選択
2. **プロジェクトスキャン** — プロジェクトタイプ、技術スタック、構造を自動検出
3. **生成** — 逆ピラミッド構造で README を作成
4. **出力** — メインファイルと翻訳版を生成

### サポートコマンド

| コマンド | 説明 |
|---|---|
| `/readme` | README 生成をトリガー |
| `generate readme` | 自然言語トリガー |
| `write readme` | 自然言語トリガー |
| `帮我写 README` | 中国語トリガー |
| `更新README` | 既存の README を更新 |

## プロジェクト構造

```
general-readme-skill/
├── SKILL.md                # メインスキル定義ファイル
├── examples/               # README サンプルファイル
│   ├── app-readme.md       # フルスタックアプリケーション例
│   ├── cli-readme.md       # CLI ツール例
│   └── library-readme.md   # ライブラリ/パッケージ例
├── install/                # インストールガイド
│   ├── claude-code.md      # Claude Code セットアップ
│   ├── copilot.md          # GitHub Copilot セットアップ
│   └── cursor.md           # Cursor セットアップ
└── references/             # リファレンスファイル
    ├── badges.md           # 技術バッジマッピング
    ├── badge-styles.md     # バッジレイアウトルール
    ├── diagram-templates.md # Mermaid/SVG テンプレート
    ├── language-guide.md   # 多言語ルール
    ├── section-guidelines.md # セクション執筆ルール
    └── tone-profiles.md    # ライティングトーン定義
```

## 技術スタック

### ドキュメント

| 技術 | 用途 |
|---|---|
| Markdown | 主要コンテンツフォーマット |
| shields.io | バッジ生成 |
| Mermaid | アーキテクチャ図 |

### サポートプラットフォーム

| プラットフォーム | 統合方法 |
|---|---|
| Claude Code | `.claude/skills/` ディレクトリ |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | `.cursor/rules/` ディレクトリ |

## コントリビュート

1. リポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/amazing`)
3. 変更をコミット (`git commit -m 'feat: add amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing`)
5. Pull Request を開く

## ライセンス

LICENSE ファイルが検出されませんでした。プロジェクトのライセンスを明確にするために LICENSE を追加してください。
