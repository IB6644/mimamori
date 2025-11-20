# ⚡ クイックスタートガイド

## 🎯 このリポジトリをGitHubにpushする

### ステップ1: GitHubでリポジトリを作成（すでに完了）

✅ リポジトリ: `https://github.com/IB6644/mimamori`

### ステップ2: コマンド実行

**このフォルダ内で以下を実行:**

```bash
# リモートリポジトリを設定
git remote add origin https://github.com/IB6644/mimamori.git

# mainブランチでpush
git push -u origin main
```

### ステップ3: 認証

**Personal Access Token（PAT）を使用:**

1. Username: `IB6644`
2. Password: **Personal Access Token**（下記で取得）

**Token取得URL:**
👉 https://github.com/settings/tokens/new

**必要な設定:**
- Note: `mimamori-deploy`
- Expiration: 30 days
- Scope: ✅ `repo` にチェック

### ステップ4: GitHub Pages有効化

1. https://github.com/IB6644/mimamori/settings/pages
2. Source: `main` / `/ (root)`
3. Save

**5分後に公開:**
```
https://ib6644.github.io/mimamori/demo.html
```

---

## 🔄 別の方法: ZIPでアップロード

Gitコマンドがうまくいかない場合:

1. このフォルダを圧縮
2. GitHubで "Add file" → "Upload files"
3. ZIPをドラッグ&ドロップ

---

## 📱 公開後のURL

| ページ | URL |
|--------|-----|
| デモページ | `https://ib6644.github.io/mimamori/demo.html` |
| アプリ本体 | `https://ib6644.github.io/mimamori/index.html` |
| デプロイガイド | `https://ib6644.github.io/mimamori/deploy.html` |

---

## 💡 ヒント

**Token保存（オプション）:**
```bash
# Tokenを使ったリモートURL設定
git remote set-url origin https://YOUR_TOKEN@github.com/IB6644/mimamori.git
git push -u origin main
```

---

**問題が発生した場合:**
- `GITHUB_PUSH_GUIDE.md` を参照
- `deploy.html` を開いてビジュアルガイドを確認
