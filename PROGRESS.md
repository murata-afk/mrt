# 作業ログ

## 2026-06-23
- プロジェクト開始。
- Claude 標準コネクタを確認 → Gmail / Google Calendar / Google Drive すべて接続済み。
- Web で 2026 時点の仕様を確認（Gmail は下書きまで・会議室はリソース方式）。
- 作成ファイル: `CLAUDE.md`, `PROGRESS.md`, `docs/setup-connectors.md`
- ブランチ `claude/elegant-davinci-nz70or` で作業開始。
- 次の一手: Phase 1（空き枠抽出 → 候補日メール下書き）。ユーザーから会議条件を受領待ち。

## 2026-07-30
- 新ワークフロー「毎朝のスケジュール & ミーティングアドバイス通知」開始。
- 標準コネクタ確認 → Google Calendar / Slack / Gmail すべて接続済み（Slack ツール呼び出し確認）。
- Web で 2026 時点の Slack コネクタ仕様を確認（2026-01 GA・読み取り＋送信対応）。
- 作成/更新: `CLAUDE.md`（本ワークフロー用に再構成）, `docs/morning-brief.md`（新規）, `docs/setup-connectors.md`（Slack 追記）。
- ブランチ `claude/morning-schedule-meeting-advice-jrlpvy` で作業。
- 次の一手: Phase 1（今日+明日の予定 → アドバイス生成 → 自分への Slack DM）。ユーザーから通知先の確定待ち。
