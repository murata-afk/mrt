# 作業ログ

## 2026-06-23
- プロジェクト開始。
- Claude 標準コネクタを確認 → Gmail / Google Calendar / Google Drive すべて接続済み。
- Web で 2026 時点の仕様を確認（Gmail は下書きまで・会議室はリソース方式）。
- 作成ファイル: `CLAUDE.md`, `PROGRESS.md`, `docs/setup-connectors.md`
- ブランチ `claude/elegant-davinci-nz70or` で作業開始。
- 次の一手: Phase 1（空き枠抽出 → 候補日メール下書き）。ユーザーから会議条件を受領待ち。

## 2026-08-16
- 「デスクトップアプリでフォルダ選択のボタンが見つからない」件を調査。
  原因はタブ違い（Chat タブには無い）/ 環境が Local 以外 / 既存セッションを開いている、が主。
- 作成ファイル: `docs/desktop-open-local-folder.md`（手順＋見つからないときのチェックリスト）
- 補足: Phase 1 は Gmail / Calendar コネクタだけで完結するため、フォルダを開く必要は無い。
