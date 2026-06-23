# コネクタ確認メモ（2026-06時点）

このプロジェクトで使う「コネクタ」= Claude に最初から組み込まれている公式連携。
ユーザー側のインストール作業はゼロ。各操作は実行のたびに承認を求められる（誤操作防止）。

## このフローに関係するコネクタ

| コネクタ | 用途 | このユーザー環境での状態 |
|---|---|---|
| Google Calendar | 空き時間取得 / 予定登録 / 会議室(リソース)予約 | ✅ 接続済み |
| Gmail | 候補日メールの下書き作成 / 返信の読み取り | ✅ 接続済み |
| Google Drive | （任意）バックアップ保存先 | ✅ 接続済み |

※ 接続済み = Claude 側で `mcp__Gmail__*` `mcp__Google_Calendar__*` ツールが実際に呼べる状態を確認済み。

## 重要な仕様（2026年時点・Web確認済み）

- **Gmail コネクタはメールを「送信」できない。「下書き」までが上限**。
  → 今回のフロー（送信は人間が手動）と完全に一致するので好都合。
- **Google Calendar の会議室は「リソース」という特別な参加者**。
  会議室ごとにメールアドレスを持ち、予定の参加者(attendee)に `resource=true` で追加すると予約になる。
  空き判定は Google 側の重複検知エンジンが自動で行う。
- Google Calendar API は無料（1日100万リクエストまで）。
- `suggest_time` ツールで「指定期間・所要時間・営業時間内」の空き枠を自動抽出できる。

## 会議室予約について（Phase 3 で詳しく扱う）

会議室リソースは「Google Workspace 管理者があらかじめ登録したもの」しか使えない。
- 個人の Gmail アカウントには会議室リソースが無い場合がある
- Phase 3 着手時に「自社にどんな会議室リソースがあるか」を一緒に確認する

## 参考リンク

- [Use Google Workspace connectors | Claude Help Center](https://support.claude.com/en/articles/10166901-use-google-workspace-connectors)
- [Share room and resource calendars | Google Workspace Help](https://knowledge.workspace.google.com/admin/calendar/share-room-and-resource-calendars)
- [Allow Free/Busy Google Calendar room booking](https://knowledge.workspace.google.com/admin/calendar/allow-free-busy-google-calendar-room-booking)
