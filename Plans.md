# 会社経営AI - Plans.md

## Phase 0: プロジェクト初期化 ✅

- [x] Harness セットアップ（CLAUDE.md / AGENTS.md / Plans.md / .claude/）
- [x] Codexレビュー通過・.gitignore整備

## Phase 1: cc-company インストール・セットアップ

- [x] cc-company プラグインをインストール（手動配置で完了）
- [ ] `/company` でオンボーディング実行 → `.company/` 生成
- [ ] 動作確認（秘書に話しかけ → 部署振り分けが機能するか）

## Phase 2: 機能拡充（deep-research-report.md ベース）

### MCP連携
- [ ] Search Console MCP 接続（SEO事実データ取得）
- [ ] GA4 MCP 接続（アクセス解析）
- [ ] YouTube MCP（文字起こし・分析）
- [ ] GitHub MCP（リポジトリ連携）
- [ ] .mcp.json の秘密情報管理（環境変数展開）

### Codexレビュー自動化
- [ ] hooks で変更後にCodexレビュー自動起動
- [ ] レビュー結果を `.company/reviews/` に保存するスクリプト

### Telegram ブリッジ（スマホ操作）
- [ ] OpenClaw + Telegram ブリッジ設計
- [ ] Claude Code ヘッドレス実行（`-p` / `--session-id`）連携
- [ ] Telegramスレッド ↔ Claude Codeセッションのマッピング

## Phase 3: 高度な自動化

- [ ] subagents / hooks による部署ごとの実働強化
- [ ] 監査ログ・レポート自動生成
- [ ] OpenClaw sandbox 連携

---

*最終更新: 2026-03-11*
