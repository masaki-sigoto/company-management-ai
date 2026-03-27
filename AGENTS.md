# 会社経営AI - 開発フロー

## 二層構造

このプロジェクトは2つのレイヤーで動く:

### レイヤー1: cc-company（日常運営）

```
あなた → /company → 秘書（窓口） → CEO（振り分け） → 各部署
```

- `/company` で秘書に話しかけて業務を進める
- 秘書がTODO管理、壁打ち、メモを担当
- 部署が必要な案件はCEOが自動振り分け
- すべて `.company/` 内のMarkdownファイルで管理

### レイヤー2: Harness（拡張開発）

```
Plan → Work → Review → Commit → (Codex Review) → Push
```

- cc-companyの機能拡充（MCP連携、Telegramブリッジ等）を開発するとき
- Plans.mdに基づいてタスク管理
- サブエージェント委任でコンテキスト節約
- Push前にCodexレビュー必須

## エージェント役割分担

| 役割 | 担当 | 場面 |
|------|------|------|
| メインエージェント（PM） | 計画・指示・確認 | 拡張開発時 |
| サブエージェント | 実装・テスト | Task tool経由 |
| Codex CLI | コードレビュー | Push前 |
| 秘書（cc-company） | 窓口・TODO・壁打ち | 日常運営時 |

## コマンド早見表

| コマンド | 用途 |
|---------|------|
| `/company` | 秘書に話しかける（日常運営） |
| `/plan-with-agent` | 拡張開発の計画作成 |
| `/work` | Plans.mdのタスク実行 |
| `/harness-review` | レビュー |
| `/sync-status` | 進捗確認 |
