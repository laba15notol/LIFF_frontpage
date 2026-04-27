# URL変更フロー（新規イベント用）

日付・イベントごとにユニークなURLでフロントページを運用するための手順です。

---

## フロー概要

```
1. 新規イベント用ディレクトリを作成
   ↓
2. index.html をコピー＆設定を編集
   ↓
3. GitHub にプッシュ
   ↓
4. LINE Developers でエンドポイントURLを変更
   ↓
5. 動作確認
```

---

## 詳細手順

### Step 1: 新規イベント用ディレクトリを作成

ユニークID（例: `andmary03`）を決めて、その名前のフォルダを作成します。

```
LIFF_frontpage/
├── index.html          # ルート（参考用）
├── x7k9m2p4/           # 前回イベント
├── andmary03/          # 今回イベント（新規）
│   └── index.html
└── [新しいID]/          # ← 新規作成するフォルダ
    └── index.html
```

### Step 2: index.html をコピー＆設定を編集

既存のイベント用 `index.html`（例: `andmary03/index.html`）をコピーし、以下の項目を編集します。

| 編集項目 | 説明 |
|----------|------|
| `googleFormUrl` | 今回のイベント用GoogleフォームのURL |
| `entryId` | LINE IDを事前入力するフィールドのエントリID |
| `<title>` | イベント名が分かるタイトル |
| コメント | イベントIDを明記 |

### Step 3: GitHub にプッシュ

```bash
# 新規フォルダを追加
git add [新しいID]/

# コミット
git commit -m "Add [新しいID] page for [イベント名]"

# プッシュ
git push origin main
```

### Step 4: LINE Developers でエンドポイントURLを変更

1. [LINE Developers Console](https://developers.line.biz/) にログイン
2. 対象のプロバイダー → チャネル → **LIFF** タブ
3. 使用中のLIFFアプリを編集
4. **エンドポイントURL** を変更

   ```
   変更後: https://laba15notol.github.io/LIFF_frontpage/[新しいID]/
   ```

5. 保存

### Step 5: 動作確認

- ブラウザで直接アクセス: `https://laba15notol.github.io/LIFF_frontpage/[新しいID]/`
- LINEアプリからLIFF経由でアクセスして動作確認

---

## 注意事項

- **LIFF ID は変更不要**です（同じLIFFアプリを使い回す場合）
- エンドポイントURLを変更すると、**以前のURLはLIFF認証で使えなくなります**
- GitHub Pages の反映には数分かかることがあります
- Googleフォームの `entryId` は、フォーム編集画面の「回答を確認」→「URLを取得」で確認できます

---

## 過去のイベントURL一覧

| イベントID | URL |
|------------|-----|
| andmary03 | https://laba15notol.github.io/LIFF_frontpage/andmary03/ |
| x7k9m2p4 | https://laba15notol.github.io/LIFF_frontpage/x7k9m2p4/ |
| andmary04 | https://laba15notol.github.io/LIFF_frontpage/andmary04/ |
| andmary05 | https://laba15notol.github.io/LIFF_frontpage/andmary05/ |
