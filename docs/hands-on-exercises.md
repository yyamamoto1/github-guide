# 🎯 ハンズオン演習: 実践でGitを学ぼう
**AI Education Assistant #8 担当領域**

## 📚 学習プログラム

このハンズオン演習では、段階的にGit/GitHubの操作を実践します。各演習は実際のファイルを使って行います。

---

## 🌟 演習1: はじめてのGitリポジトリ (15分)

### 🎯 目標
- Gitリポジトリを初期化
- ファイルをコミット
- 基本的なGitコマンドに慣れる

### 📋 手順

#### ステップ1: プロジェクト作成
```bash
# 1. 演習用ディレクトリを作成
mkdir git-practice-1
cd git-practice-1

# 2. プロジェクトファイルを作成
echo "# 私のGit練習プロジェクト" > README.md
echo "このプロジェクトでGitの基本を学習します。" >> README.md

# 3. シンプルなHTMLファイルを作成
cat > index.html << 'EOF'
<!DOCTYPE html>
<html>
<head>
    <title>Git練習サイト</title>
</head>
<body>
    <h1>Hello Git!</h1>
    <p>これは練習用のウェブサイトです。</p>
</body>
</html>
EOF

# 4. CSSファイルを作成
echo "body { font-family: Arial, sans-serif; margin: 40px; }" > style.css
```

#### ステップ2: Git初期化・コミット
```bash
# 1. Gitリポジトリとして初期化
git init

# 2. 現在の状態を確認
git status

# 3. ファイルをステージング
git add README.md
git add index.html
git add style.css

# 4. ステージング状態を確認
git status

# 5. 初回コミット
git commit -m "🎉 初回コミット: プロジェクトの基本ファイルを追加"

# 6. コミット履歴を確認
git log --oneline
```

### ✅ チェックポイント
- [ ] `.git` ディレクトリが作成されている
- [ ] `git status` で「working tree clean」と表示される
- [ ] `git log` でコミットが確認できる

---

## 🚀 演習2: ファイル更新とコミット (20分)

### 🎯 目標
- ファイルを更新してコミット
- 差分を確認
- コミットメッセージのベストプラクティスを学ぶ

### 📋 手順

#### ステップ1: ファイル更新
```bash
# 1. HTMLファイルに新しいセクションを追加
cat >> index.html << 'EOF'
    <h2>Git学習の進捗</h2>
    <ul>
        <li>✅ リポジトリ初期化</li>
        <li>✅ ファイルコミット</li>
        <li>🔄 ファイル更新中</li>
    </ul>
EOF

# 2. CSSに新しいスタイルを追加
echo "h2 { color: #333; border-bottom: 2px solid #007ACC; }" >> style.css
echo "ul { background: #f5f5f5; padding: 20px; }" >> style.css

# 3. 新しいJavaScriptファイルを追加
echo "console.log('Git練習プロジェクト開始！');" > script.js
echo "document.addEventListener('DOMContentLoaded', function() {" >> script.js
echo "    console.log('ページが読み込まれました');" >> script.js
echo "});" >> script.js
```

#### ステップ2: 変更確認・コミット
```bash
# 1. 変更内容を確認
git status
git diff

# 2. 段階的にステージング（実務でよく使う方法）
git add index.html
git status

git add style.css
git status

git add script.js
git status

# 3. コミット
git commit -m "✨ 機能追加: 学習進捗セクションとスタイリングを追加

- HTMLに進捗リストセクションを追加
- CSSにh2とulのスタイルを追加  
- JavaScriptファイルを新規作成
- ページ読み込み時のログ機能を実装"

# 4. 履歴確認
git log --oneline
```

### ✅ チェックポイント
- [ ] `git diff` で変更差分が確認できた
- [ ] 複数ファイルを個別にステージングできた
- [ ] 詳細なコミットメッセージを書けた

---

## 🌿 演習3: ブランチワークフロー (30分)

### 🎯 目標
- ブランチを作成・切り替え
- ブランチで機能開発
- マージの実践

### 📋 手順

#### ステップ1: 機能ブランチ作成
```bash
# 1. 現在のブランチ確認
git branch

# 2. 新機能用ブランチ作成・切り替え
git checkout -b feature/contact-form

# 3. ブランチ確認
git branch

# 4. 連絡先フォームのHTMLを作成
cat > contact.html << 'EOF'
<!DOCTYPE html>
<html>
<head>
    <title>お問い合わせ</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>お問い合わせフォーム</h1>
    <form id="contactForm">
        <label for="name">お名前:</label>
        <input type="text" id="name" name="name" required>
        
        <label for="email">メールアドレス:</label>
        <input type="email" id="email" name="email" required>
        
        <label for="message">メッセージ:</label>
        <textarea id="message" name="message" required></textarea>
        
        <button type="submit">送信</button>
    </form>
    
    <script src="contact.js"></script>
</body>
</html>
EOF
```

#### ステップ2: フォーム機能の実装
```bash
# 1. フォーム用JavaScriptを作成
cat > contact.js << 'EOF'
document.addEventListener('DOMContentLoaded', function() {
    const form = document.getElementById('contactForm');
    
    form.addEventListener('submit', function(e) {
        e.preventDefault();
        
        const name = document.getElementById('name').value;
        const email = document.getElementById('email').value;
        const message = document.getElementById('message').value;
        
        console.log('フォーム送信データ:', { name, email, message });
        alert('お問い合わせありがとうございます！');
        
        form.reset();
    });
});
EOF

# 2. フォーム用CSSを追加
cat >> style.css << 'EOF'

/* フォームスタイル */
form {
    max-width: 600px;
    margin: 20px 0;
}

label {
    display: block;
    margin-top: 15px;
    font-weight: bold;
}

input, textarea {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border: 1px solid #ddd;
    border-radius: 4px;
}

button {
    background: #007ACC;
    color: white;
    padding: 12px 24px;
    border: none;
    border-radius: 4px;
    margin-top: 15px;
    cursor: pointer;
}

button:hover {
    background: #005a9e;
}
EOF
```

#### ステップ3: ブランチでコミット
```bash
# 1. 変更をコミット
git add .
git commit -m "✨ 新機能: お問い合わせフォームを実装

- contact.htmlにフォームページを作成
- contact.jsにフォーム送信処理を実装
- style.cssにフォーム用スタイルを追加
- バリデーション機能付き"

# 2. メインページにリンクを追加
sed -i '' 's|</body>|    <p><a href="contact.html">お問い合わせはこちら</a></p>\n</body>|' index.html

git add index.html
git commit -m "🔗 リンク追加: メインページから問い合わせページへのリンク"

# 3. ブランチの履歴確認
git log --oneline
```

#### ステップ4: マージ
```bash
# 1. メインブランチに戻る
git checkout main

# 2. ファイル状態確認（contact関連ファイルが無いことを確認）
ls

# 3. 機能ブランチをマージ
git merge feature/contact-form

# 4. ファイル状態確認（contact関連ファイルが追加されたことを確認）
ls

# 5. 履歴確認
git log --oneline --graph

# 6. 不要なブランチを削除
git branch -d feature/contact-form
```

### ✅ チェックポイント
- [ ] ブランチを作成・切り替えできた
- [ ] ブランチごとにファイル状態が変わることを確認できた
- [ ] マージによってファイルが統合された

---

## 🔄 演習4: GitHubへのプッシュ (25分)

### 🎯 目標
- GitHubリポジトリを作成
- ローカルリポジトリをリモートに接続
- プッシュ・プル操作を実践

### 📋 手順

#### ステップ1: GitHubリポジトリ作成
**GitHubウェブサイトで操作:**
1. https://github.com にログイン
2. 右上の「+」→「New repository」
3. Repository name: `git-practice-project`
4. Description: `Git学習用の練習プロジェクト`
5. Public を選択
6. **重要**: 「Add a README file」はチェックしない
7. 「Create repository」をクリック

#### ステップ2: リモート接続・プッシュ
```bash
# 1. リモートリポジトリを追加
git remote add origin https://github.com/YOUR_USERNAME/git-practice-project.git

# 2. リモート確認
git remote -v

# 3. ブランチ名をmainに設定
git branch -M main

# 4. 初回プッシュ
git push -u origin main

# 5. GitHubで確認
# ブラウザでリポジトリページを確認し、ファイルがアップロードされているか確認
```

#### ステップ3: 更新・プッシュサイクル
```bash
# 1. READMEを更新
cat >> README.md << 'EOF'

## 🎯 プロジェクト概要
このプロジェクトはGit/GitHubの学習用に作成されました。

## 📁 ファイル構成
- `index.html` - メインページ
- `contact.html` - お問い合わせフォーム
- `style.css` - スタイルシート
- `script.js` - メインページ用JavaScript
- `contact.js` - フォーム用JavaScript

## 🎓 学習内容
- [x] Gitリポジトリの初期化
- [x] ファイルのコミット
- [x] ブランチワークフロー
- [x] GitHubへのプッシュ
EOF

# 2. 変更をコミット・プッシュ
git add README.md
git commit -m "📚 ドキュメント更新: READMEにプロジェクト詳細を追加"
git push

# 3. GitHubで更新を確認
```

### ✅ チェックポイント
- [ ] GitHubリポジトリが作成された
- [ ] ローカルリポジトリがプッシュされた
- [ ] README更新がGitHubに反映された

---

## 🤝 演習5: チーム開発シミュレーション (35分)

### 🎯 目標
- リモートからの更新取得
- コンフリクト解決
- チーム開発のワークフローを体験

### 📋 手順

#### ステップ1: リモートでの変更をシミュレート
**GitHubウェブサイトで操作:**
1. リポジトリページの `index.html` をクリック
2. 編集ボタン（鉛筆アイコン）をクリック
3. `<h1>Hello Git!</h1>` を `<h1>Hello Git & GitHub!</h1>` に変更
4. 下部のコミットメッセージに: `🌐 Update: GitHubとの連携を強調`
5. 「Commit changes」をクリック

#### ステップ2: ローカルで同じファイルを変更
```bash
# 1. ローカルでも同じファイルを変更（意図的にコンフリクトを作成）
sed -i '' 's|<h1>Hello Git!</h1>|<h1>Welcome to Git World!</h1>|' index.html

# 2. 変更をコミット
git add index.html
git commit -m "🎨 スタイル更新: よりウェルカムなメッセージに変更"

# 3. プッシュを試行（失敗するはず）
git push
```

#### ステップ3: コンフリクト解決
```bash
# 1. リモートの変更を取得
git fetch origin

# 2. マージを試行（コンフリクトが発生）
git merge origin/main

# 3. コンフリクトファイルを確認
cat index.html

# 4. 手動でコンフリクトを解決
# エディタで開いて以下のようにマークされた部分を編集:
# <<<<<<< HEAD
# <h1>Welcome to Git World!</h1>
# =======
# <h1>Hello Git & GitHub!</h1>
# >>>>>>> origin/main

# 5. 解決例（両方の変更を統合）
sed -i '' 's|<<<<<<< HEAD||' index.html
sed -i '' 's|=======||' index.html
sed -i '' 's|>>>>>>> origin/main||' index.html
sed -i '' 's|<h1>Welcome to Git World!</h1>|<h1>Welcome to Git & GitHub World!</h1>|' index.html

# 6. 解決をコミット
git add index.html
git commit -m "🔀 マージ: リモートとローカルの変更を統合"

# 7. プッシュ
git push
```

### ✅ チェックポイント
- [ ] リモートの変更を取得できた
- [ ] コンフリクトが発生した
- [ ] 手動でコンフリクトを解決できた
- [ ] 解決結果をプッシュできた

---

## 🏷️ 演習6: タグとリリース (15分)

### 🎯 目標
- バージョンタグの作成
- GitHubリリースの作成

### 📋 手順

#### ステップ1: タグ作成
```bash
# 1. 現在の状態を確認
git log --oneline

# 2. バージョンタグを作成
git tag -a v1.0.0 -m "🎉 Version 1.0.0 - 基本機能完成

- メインページ実装
- お問い合わせフォーム実装
- スタイリング完了
- GitHub連携完了"

# 3. タグ一覧確認
git tag

# 4. タグをプッシュ
git push origin v1.0.0

# 5. 全てのタグをプッシュ
git push origin --tags
```

#### ステップ2: GitHubリリース作成
**GitHubウェブサイトで操作:**
1. リポジトリページの「Releases」をクリック
2. 「Create a new release」をクリック
3. Tag version: `v1.0.0` を選択
4. Release title: `初回リリース v1.0.0`
5. Description に以下を記入:
```markdown
## 🎉 初回リリース

### 実装機能
- ✅ メインページ
- ✅ お問い合わせフォーム
- ✅ レスポンシブデザイン
- ✅ JavaScriptインタラクション

### 学習達成項目  
- ✅ Git基本操作
- ✅ ブランチワークフロー
- ✅ GitHubプッシュ・プル
- ✅ コンフリクト解決
```
6. 「Publish release」をクリック

### ✅ チェックポイント
- [ ] タグが作成された
- [ ] タグがGitHubにプッシュされた
- [ ] GitHubリリースが作成された

---

## 🎖️ 卒業課題: 独自機能の追加 (45分)

### 🎯 目標
これまでの学習を活かして、独自の機能を追加してリリースまで行う

### 📋 課題内容
以下のいずれかの機能を実装してください：

#### オプション1: ギャラリーページ
- 画像ギャラリーページを作成
- 画像クリックで拡大表示
- カテゴリ別フィルタリング

#### オプション2: ブログページ  
- 簡単なブログページを作成
- 記事一覧とサマリー表示
- カテゴリタグ機能

#### オプション3: プロフィールページ
- 自己紹介ページを作成
- スキル一覧表示
- SNSリンク集

### 📋 実装手順
1. 機能ブランチ作成 (`feature/gallery`, `feature/blog`, `feature/profile`)
2. HTML, CSS, JavaScript実装
3. ローカルでテスト
4. コミット（適切なメッセージで）
5. メインブランチにマージ
6. GitHubにプッシュ
7. v1.1.0タグ作成・リリース

### ✅ 評価ポイント
- [ ] 適切なブランチワークフローで開発
- [ ] わかりやすいコミットメッセージ
- [ ] 機能が正常に動作する
- [ ] GitHubにプッシュされている
- [ ] リリースが作成されている

---

## 🎓 学習完了証明

### 📋 全演習チェックリスト

#### 基礎レベル
- [ ] 演習1: Gitリポジトリ初期化・コミット
- [ ] 演習2: ファイル更新・差分確認
- [ ] 演習3: ブランチワークフロー

#### 実践レベル  
- [ ] 演習4: GitHubプッシュ・プル
- [ ] 演習5: コンフリクト解決
- [ ] 演習6: タグ・リリース管理

#### 応用レベル
- [ ] 卒業課題: 独自機能実装・リリース

### 🏆 修了認定
全ての演習を完了した方は、以下のバッジを取得できます：

**🎖️ Git/GitHub マスター認定**
- Git基本操作習得
- ブランチワークフロー理解
- チーム開発経験
- リリース管理スキル

### 🔗 次のステップ
- [GitHub Actions入門](./github-actions.md)
- [オープンソース貢献ガイド](./opensource-contribution.md)
- [Git上級テクニック](./advanced-git.md)

---

💡 **AI Education Assistant による継続学習支援**
- 個別の学習進捗管理
- 弱点分野の重点的な演習提案
- 実際のプロジェクトでの実践指導
- 質問・疑問への即座回答