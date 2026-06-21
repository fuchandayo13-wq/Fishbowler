# Fishbowler

散文テキストの編集・共有・プレイリスト表示 Web アプリです。GitHub Pages で公開できます。

## 機能

| モード | 内容 |
|--------|------|
| **Author** | 本文の編集、アップロード、太字・傍点、書籍情報（著書名・著者・OGP画像） |
| **Reader** | 本文閲覧、任意範囲の共有URL、プレイリスト連続表示 |

### 書式コマンド

- `**太字**` → **太字**
- `{{傍点}}` → 傍点（圏点）

### 共有URL

| 種類 | 形式 | 例 |
|------|------|-----|
| 範囲指定 | `?sel=開始-終了` | `?sel=85-210` |
| プレイリスト | `?pl=開始,終了,開始,終了` | `?pl=0,50,120,200` |

### X（Twitter）カード

リンクを X に貼ると、Spotify と同様に **画像・著書名・著者** がプレビュー表示されます。

> **重要**: X のクローラーは JavaScript を実行しません。Author 画面で設定したあと **「GitHub用 index.html をダウンロード」** してアップロードするか、`<head>` 内の OGP メタタグを手動で更新してください。

## GitHub Pages 公開手順

1. GitHub で `Fishbowler` リポジトリを作成
2. 次のファイルをアップロード:
   - `index.html`
   - `data/book.json`
   - `images/cover.jpg`（1200×630px 推奨。`cover.svg` を JPG に変換しても可）
3. **Settings → Pages → Branch: main / (root)** を有効化
4. `https://あなたのユーザー名.github.io/Fishbowler/` でアクセス

## Author のワークフロー

1. **Author（編集）** タブを開く
2. 著書名・著者・画像 URL を入力
3. 本文を編集（または `.txt` / `book.json` を読込）
4. **設定を反映して保存**
5. GitHub 公開時は **book.json** または **index.html** をダウンロードしてコミット

## ファイル構成

```
Fishbowler/
├── index.html      # メインアプリ
├── data/
│   └── book.json   # 書籍データ（Author がエクスポート可能）
├── images/
│   └── cover.jpg   # OGP / Twitter カード用画像
└── README.md
```
