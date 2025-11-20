# 🚀 デプロイガイド

## 📦 ファイル構成

```
hasegawa_mimamori_web/
├── index.html          # メインアプリ
├── demo.html           # スマホフレーム付きデモページ
├── flutter.js          # Flutter Web エンジン
├── flutter_bootstrap.js
├── main.dart.js        # コンパイル済みDartコード
├── assets/            # アセットファイル
├── canvaskit/         # CanvasKit（描画エンジン）
├── icons/             # アイコン
├── README.md          # プロジェクト説明
├── DEPLOY_GUIDE.md    # このファイル
└── .nojekyll          # GitHub Pages用設定
```

## 🌐 GitHub Pagesへのデプロイ（推奨）

### 方法1: GitHubウェブインターフェース（最も簡単）

1. **GitHubにログイン** → 新規リポジトリ作成
   - Repository name: `hasegawa-mimamori-demo`
   - Public/Private: お好みで選択
   - **Initialize with README: チェックを外す**

2. **ファイルをアップロード**
   - "uploading an existing file" をクリック
   - `hasegawa_mimamori_web` フォルダ内の全ファイルをドラッグ&ドロップ
   - "Commit changes" をクリック

3. **GitHub Pagesを有効化**
   - Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: "main" / "/(root)"
   - Save

4. **公開URL確認**
   - 数分後に `https://your-username.github.io/hasegawa-mimamori-demo/demo.html` でアクセス可能

### 方法2: Git コマンドライン

```bash
# リポジトリを初期化
cd hasegawa_mimamori_web
git init
git add .
git commit -m "Initial commit: はせがわ見守りプラットフォーム"

# GitHubリポジトリに接続（リポジトリURLを置き換え）
git remote add origin https://github.com/YOUR_USERNAME/hasegawa-mimamori-demo.git
git branch -M main
git push -u origin main

# GitHub Pagesを有効化（GitHubウェブインターフェースで設定）
```

## 🚀 Netlifyへのデプロイ（超高速）

1. **Netlify にログイン** → https://app.netlify.com/
2. **"Add new site" → "Deploy manually"**
3. **`hasegawa_mimamori_web` フォルダをドラッグ&ドロップ**
4. **数秒で公開完了！** 独自URLが自動生成されます
5. **カスタムドメイン設定可能**（オプション）

## ☁️ Vercelへのデプロイ

1. **Vercel にログイン** → https://vercel.com/
2. **"Add New Project"**
3. **"Import Git Repository" または ドラッグ&ドロップ**
4. **Build settings: すべてデフォルトのまま**
5. **Deploy → 完了！**

## 🖥️ 独自サーバーへのデプロイ

### Apache / Nginx

```bash
# Apacheの場合
sudo cp -r hasegawa_mimamori_web/* /var/www/html/hasegawa/

# Nginxの場合
sudo cp -r hasegawa_mimamori_web/* /usr/share/nginx/html/hasegawa/
```

### Node.js (http-server)

```bash
npm install -g http-server
cd hasegawa_mimamori_web
http-server -p 8000
```

## 🔧 トラブルシューティング

### 1. ページが真っ白になる

**原因:** ベースパスの設定が間違っている

**解決策:** 
- GitHub Pagesの場合、リポジトリ名がパスに含まれます
- `https://username.github.io/repository-name/demo.html`
- サブディレクトリで動作させる場合は、`index.html` の `<base href="/">` を調整

### 2. アセットが読み込めない

**原因:** CORSエラーまたはパスの問題

**解決策:**
- ローカルテストは `http-server` や `python3 -m http.server` を使用
- `file://` プロトコルでは動作しません

### 3. GitHub Pagesで404エラー

**原因:** `.nojekyll` ファイルがない

**解決策:**
- リポジトリのルートに `.nojekyll` ファイルが存在することを確認
- すでに含まれていますが、念のため確認してください

## 📱 推奨アクセス方法

**デモプレゼンテーション用:**
👉 `https://your-domain/demo.html`

**フルスクリーンアプリ:**
👉 `https://your-domain/index.html`

## 🎯 公開後のチェックリスト

- [ ] デモページ（demo.html）が正しく表示される
- [ ] スマホフレーム内のアプリが動作する
- [ ] 下部ナビゲーションで画面切り替え可能
- [ ] グラフが正しく表示される
- [ ] カードのタップで詳細が表示される
- [ ] リロードボタンが動作する
- [ ] レスポンシブデザインが機能する（モバイル表示）

## 🔒 セキュリティ注意事項

このデモアプリは**プロトタイプ**です。本番環境で使用する場合は以下を実装してください：

- ✅ ユーザー認証（Firebase Auth など）
- ✅ HTTPS通信の強制
- ✅ APIエンドポイントのセキュリティ
- ✅ データの暗号化
- ✅ セッション管理

## 📞 サポート

デプロイに関する質問は、開発者までお問い合わせください。

**開発者:** 梅澤優一（Ume）  
**所属:** 大崎電気工業株式会社 インキュベーション室

---

© 2025 大崎電気工業株式会社 × 株式会社はせがわ | PoC Prototype
