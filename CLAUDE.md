# 会社経営AI - プロジェクト設定

## プロジェクト概要

cc-company プラグイン（Shin-sibainu/cc-company）をインストール・セットアップし、
Claude Code上で仮想会社組織を構築・運営する。
秘書が窓口 → CEOが振り分け → 各部署がMarkdownファイルで業務を管理する仕組み。

deep-research-report.md をロードマップに、MCP連携・Telegram操作・Codexレビュー自動化等で機能拡充する。

## 仕組み

- **cc-company**: Claude Codeプラグイン。`/company` スキルで `.company/` フォルダを生成・運営
- **秘書**: ユーザーの窓口。TODO管理、壁打ち、メモ
- **CEO**: 裏方で判断。必要に応じて部署に振り分け
- **各部署**: 専門領域のMarkdownファイル管理（PM、リサーチ、開発、経理、営業等）

## ファイル構成

```
.
├── CLAUDE.md               # このファイル
├── AGENTS.md               # 開発フロー概要
├── Plans.md                # タスク管理
├── deep-research-report.md # 拡張ロードマップ（リサーチ報告書）
├── .claude/                # Harness設定
│   ├── settings.json
│   ├── memory/
│   └── rules/
├── .company/               # cc-company が生成（秘書室・CEO・各部署）
└── scripts/                # 拡張用スクリプト（Telegramブリッジ等）
```

## 運用ルール

### 1. コミットルール（必須）

- 作業ごとに細かく分割してcommitすること
- 1つの論理的な変更 = 1 commit
- コミットメッセージは変更内容を正確に反映

### 2. Push前のCodexレビュー（必須）

- pushする前に必ず `codex review --uncommitted` を実施
- レビュー指摘があれば修正→再レビュー→問題なしを確認してからpush

### 3. サブエージェント委任・PM的振る舞い（必須）

- 基本的に作業はサブエージェント（Task tool）に委任してコンテキストを削減
- メインエージェントはPM的に計画・指示・確認・統合を行う
- 直接実装するのは軽微な修正のみ

### 4. Plans.md 駆動

- すべてのタスクは Plans.md に記載してから着手
- `[ ]` → `[x]` で進捗を追跡
