# 再利用パターン

## 開発ワークフロー

```
1. Plans.md にタスク追加
2. サブエージェントに委任して実装
3. 成果物確認 → 細かくcommit
4. Push前にCodexレビュー
5. 指摘修正 → 再レビュー → Push
```

## サブエージェント委任パターン

```
Task tool → subagent_type に応じて使い分け:
- Explore: コードベース調査
- Plan: 設計・計画
- general-purpose: 複雑なマルチステップタスク
- claude-code-harness:task-worker: 単一タスク実装
- claude-code-harness:code-reviewer: コードレビュー
```
