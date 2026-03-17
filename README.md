# ✦ マイデイ / MyDay

> **このプロジェクトは全コードを AI（Claude by Anthropic）を使用して作成しました。**  
> The entire codebase was generated with AI assistance (Claude by Anthropic).

---

## 📋 概要

マイデイは、毎日の予定・タスク・ニュースを一画面で管理できる**個人用ダッシュボード**です。  
単一のHTMLファイルで動作し、サーバー不要でブラウザだけで使えます。

## ✨ 機能

| 機能 | 説明 |
|------|------|
| 📅 スケジュール管理 | 時刻指定・終日イベント、タイムライン表示、重複イベントのカラム分割 |
| ✅ タスク管理 | 優先度・カテゴリ・締め切り、フィルター、進捗バー |
| 📰 ニュース | Hacker News / Reddit から自動取得 |
| 🎙️ AI解説 | Anthropic API でニュースをAI対話形式で解説（要APIキー） |
| 📚 勉強管理 | YouTubeプレイリスト登録・クイックスタート |
| 📅 Google Calendar 同期 | ICS URL または OAuth API 経由で自動同期 |
| 🎨 5テーマ | Dark / Glass / Neon / Aurora / Warm |

## 🔒 セキュリティ確認（Public公開について）

このリポジトリには**個人情報・秘密鍵・プライベートURLは一切含まれていません。**

| ファイル | 確認事項 | 状態 |
|----------|----------|------|
| `マイデイ.html` | APIキー・ICS URL・メールアドレスのハードコード | ✅ なし（すべてlocalStorage経由） |
| `calendar_sync.py` | 個人のICS URL | ✅ なし（プレースホルダーのみ） |
| `calendar_data.js` | カレンダー予定データ | ✅ 空（実行時に生成） |

**すべての個人情報（APIキー・ICS URL・名前など）はブラウザの `localStorage` に保存されます。**  
GitHubリポジトリには一切含まれません。

> ⚠️ **注意**: `calendar_sync.py` を使う場合、自分のICS URLをファイルに直書きした状態でコミットしないでください。`.gitignore` で `calendar_data.js` を除外することを推奨します。

## 🚀 使い方

### GitHub Pages でホスティング（推奨）

1. このリポジトリをFork または クローン
2. Settings → Pages → `main` ブランチを選択
3. `https://ユーザー名.github.io/リポジトリ名/マイデイ.html` でアクセス

### ローカルで使う

HTMLファイルをブラウザで直接開くだけです。

```
マイデイ.html をダブルクリック
```

## 📅 Google Calendar 同期のセットアップ

### 方法① ICS URL（簡単・推奨）

1. Google カレンダー → 設定 ⚙️ → カレンダーの設定
2. 「カレンダーの統合」→「非公開のアドレス（ICS形式）」をコピー
3. アプリの **設定タブ → Google Calendar同期** に貼り付け

> ⚠️ ICS URLは推測不可能なURLですが、URLを知る人なら誰でも予定を閲覧できます。人に見せないようにしてください。

### 方法② OAuth API（GitHub Pages上でのみ動作）

1. [Google Cloud Console](https://console.cloud.google.com) でプロジェクト作成
2. Google Calendar API を有効化
3. OAuth クライアントID（ウェブアプリ）を作成
4. 承認済みJavaScript生成元に GitHub Pages の URL を追加
5. アプリの設定タブにクライアントIDを入力 → 「連携」ボタン

## 🛠️ 使用技術・外部サービス

| 種別 | 内容 |
|------|------|
| フロントエンド | HTML / CSS / Vanilla JavaScript（フレームワーク不使用） |
| フォント | Google Fonts（M PLUS 1p, Outfit） |
| ニュース | Hacker News Firebase API, Reddit JSON API |
| AI解説 | Anthropic Claude API（要APIキー） |
| カレンダー | Google Calendar ICS / Google Calendar API |
| CORSプロキシ | [corsproxy.io](https://corsproxy.io)（ICS取得時） |
| データ保存 | ブラウザ localStorage（サーバーなし） |

## 📝 ライセンス

MIT License

---

*Built entirely with [Claude](https://claude.ai) by Anthropic* 🤖