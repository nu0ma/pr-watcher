# pr-watcher

GitHub の PR 状況をターミナルでリアルタイムに監視する CLI ダッシュボード。

自分が作成した PR、レビューリクエスト、対応が必要な項目を一覧で表示します。

## 前提条件

- [Bun](https://bun.sh/) がインストールされていること
- [GitHub CLI (`gh`)](https://cli.github.com/) がインストール・認証済みであること

```sh
gh auth status  # 認証状態を確認
```

## インストール

```sh
bun install
```

## 使い方

```sh
bun run start
```

### オプション

| フラグ | 説明 | デフォルト |
|---|---|---|
| `--interval`, `-i` | 自動更新の間隔（分） | `10` |

```sh
# 5分ごとに更新
bun run start -- --interval 5
bun run start -- -i 5
```

### 開発モード

ファイル変更時に自動リロードします。

```sh
bun run dev
```

## キーバインド

| キー | 操作 |
|---|---|
| `r` | 手動で即時更新 |
| `q` / `Ctrl+C` | 終了 |

## 表示内容

- **My PRs** — 自分が作成したオープン PR（レビュー状態・コメント数付き）
- **Review Requests** — 自分にレビューが依頼されている PR
- **Action Required** — 未読通知がある PR（新しいコメント、レビュー依頼など）
