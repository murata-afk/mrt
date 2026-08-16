# デスクトップアプリでローカルの `mrt` フォルダを開く手順

このプロジェクト（`murata-afk/mrt`）を、自分の PC 上のフォルダとして Claude デスクトップアプリで開くための手順。

> **そもそも必要？**
> Phase 1（空き枠抽出 → Gmail 下書き）は Gmail / Google Calendar コネクタだけで完結するので、**フォルダを開く必要はない**。
> 手元のファイル（`CLAUDE.md` や `docs/`）を直接編集させたいときだけこの手順を使う。

---

## 前提

- Claude デスクトップアプリ（最新版）
- **Pro / Max / Team / Enterprise** のいずれかのプラン（Code タブに必要）
- Git がインストール済み
  - macOS … 標準で入っていることが多い
  - Windows … [Git for Windows](https://git-scm.com/downloads/win) を入れて**アプリを再起動**

## 手順

### 1. リポジトリをローカルに clone する

まだ PC に無い場合のみ。ターミナル（Windows は Git Bash）で実行する。

```bash
cd ~/            # 好きな置き場所へ
git clone https://github.com/murata-afk/mrt.git
```

→ `~/mrt` ができる。

### 2. Code タブを開く

アプリ上部中央の **Code** タブをクリックする。

- **Chat タブにはフォルダ選択が無い**（ファイルアクセスなしの会話専用）。ここで探しても見つからない
- Cowork タブの場合は、入力欄の下の **Work in a folder** チェックボックス、または **New Project → Use an existing folder**

### 3. 環境を `Local` にする

プロンプト入力欄の付近にある環境セレクタで **Local** を選ぶ。

- `Remote` / `SSH` / `WSL` を選んでいると、フォルダではなく**リポジトリ選択**に切り替わり、`Select folder` ボタンは出ない

### 4. `Select folder` でフォルダを選ぶ

**Select folder** をクリックし、手順1で clone した `mrt` フォルダを選択する。

- このボタンは**新規セッションを作るときだけ**表示される。既存セッションを開いている状態では出ないので、新しいセッションを作ること

### 5. モデルと権限モードを決めて送信

送信ボタン横のドロップダウンでモデルを選び、権限モードを選んでからタスクを入力して Enter。

| モード | 挙動 |
|---|---|
| **Manual**（既定） | 変更前に毎回確認を求める。**このプロジェクトの方針（送信前・予約前に人間確認）に合うのでこれ推奨** |
| Accept edits | ファイル編集を自動で受け入れる |
| Plan | ファイルを編集せず方針だけ提案する |

フォルダを開くと `CLAUDE.md` が自動で読み込まれ、このプロジェクトの前提（Gmail は下書きまで、など）が引き継がれる。

---

## 「フォルダ選択のボタンが見つからない」ときのチェックリスト

| # | 確認すること | 対処 |
|---|---|---|
| 1 | Chat タブにいないか | 上部中央のタブで **Code**（または Cowork）へ切り替える |
| 2 | 環境が `Local` か | `Remote` / `SSH` / `WSL` だとリポジトリ選択になる |
| 3 | 新規セッション画面か | フォルダ指定は最初の1回だけ。新しいセッションを作る |
| 4 | 有料プランか | Code タブ押下でアップグレード案内が出るなら未加入 |
| 5 | アプリが最新版か | 古いと機能自体が無い。アップデートする |
| 6 | （Windows）Git が入っているか | 未インストールだとローカルセッションが動かない |

`Failed to load session` が出る場合は、選んだフォルダが移動・削除された可能性がある。別のフォルダを選び直すか、アプリを再起動する。

## web 版との違い

claude.ai/code（ブラウザ版）や、そこから起動したセッションは **Remote** 実行。ローカルの PC のフォルダは見えず、GitHub リポジトリを選ぶ方式なので、フォルダ選択ボタンは存在しない。

| | ローカルフォルダ | GitHub リポジトリ |
|---|---|---|
| デスクトップ + Local | ✅ | ✅ |
| デスクトップ + Remote | ❌ | ✅ |
| web 版（claude.ai/code） | ❌ | ✅ |

## 参考リンク

- [デスクトップアプリを始める | Claude Code Docs](https://code.claude.com/docs/ja/desktop-quickstart)
- [Desktop application | Claude Code Docs](https://code.claude.com/docs/ja/desktop)
- [Get started with Claude Cowork | Claude Help Center](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)
