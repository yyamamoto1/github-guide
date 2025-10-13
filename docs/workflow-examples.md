# 実践ワークフロー例

Git/GitHubを使った実務での作業フローを、具体的なコマンドとともに解説します。

---

## 📑 目次

1. [個人開発フロー](#1-個人開発フロー)
2. [チーム開発フロー（Feature Branch）](#2-チーム開発フローfeature-branch)
3. [GitHub Flowフロー](#3-github-flowフロー)
4. [Git Flowフロー](#4-git-flowフロー)
5. [オープンソース貢献フロー](#5-オープンソース貢献フロー)
6. [Issue駆動開発フロー](#6-issue駆動開発フロー)
7. [ホットフィックスフロー](#7-ホットフィックスフロー)
8. [リリースフロー](#8-リリースフロー)

---

## 1. 個人開発フロー

シンプルな個人プロジェクトでの作業フロー。

### 1.1 初回セットアップ

#### Windows:
```cmd
# プロジェクトディレクトリ作成
mkdir my-project
cd my-project

# Git初期化
git init

# 初期ファイル作成
echo # My Project > README.md

# 最初のコミット
git add README.md
git commit -m "Initial commit"

# GitHub リポジトリと連携
git remote add origin https://github.com/username/my-project.git
git branch -M main
git push -u origin main
```

#### Mac:
```bash
# プロジェクトディレクトリ作成
mkdir my-project
cd my-project

# Git初期化
git init

# 初期ファイル作成
echo "# My Project" > README.md

# 最初のコミット
git add README.md
git commit -m "Initial commit"

# GitHub リポジトリと連携
git remote add origin https://github.com/username/my-project.git
git branch -M main
git push -u origin main
```

### 1.2 日常的な作業フロー

**Windows/Mac共通:**

```bash
# 1. 作業開始前に最新を取得
git pull

# 2. ファイルを編集
# （エディタでコード編集）

# 3. 変更を確認
git status
git diff

# 4. 変更をステージング
git add .

# または特定ファイルのみ
git add src/index.js

# 5. コミット
git commit -m "Add new feature"

# 6. GitHubにプッシュ
git push
```

### 1.3 作業の取り消し

#### コミット前の取り消し

```bash
# ステージングを取り消し（ファイルは変更されたまま）
git reset HEAD <ファイル名>

# ファイルの変更を完全に取り消し
git checkout -- <ファイル名>

# すべての変更を取り消し（危険！）
git reset --hard HEAD
```

#### コミット後の取り消し

```bash
# 直前のコミットをやり直し（まだプッシュしていない場合）
git commit --amend -m "Updated commit message"

# コミットを取り消す（変更は残る）
git reset --soft HEAD~1

# コミットを取り消す（変更も取り消す）
git reset --hard HEAD~1
```

---

## 2. チーム開発フロー（Feature Branch）

最も一般的なチーム開発ワークフロー。

### 2.1 全体の流れ

```
main ─────────────●─────────●────────────→
                   \         /
                    \       /
      feature/xxx    ●─────●
```

1. `main` ブランチから機能ブランチを作成
2. 機能ブランチで開発
3. Pull Request 作成
4. コードレビュー
5. `main` にマージ

### 2.2 新機能開発の手順

#### ステップ1: 最新のmainを取得

**Windows/Mac共通:**
```bash
# mainブランチに移動
git checkout main

# 最新を取得
git pull origin main
```

#### ステップ2: 機能ブランチ作成

```bash
# 新しいブランチを作成して切り替え
git checkout -b feature/add-login

# または Git 2.23 以降
git switch -c feature/add-login
```

**ブランチ命名規則の例:**
- `feature/機能名` - 新機能
- `bugfix/バグ名` - バグ修正
- `hotfix/緊急修正名` - 緊急修正
- `refactor/リファクタ内容` - リファクタリング
- `docs/ドキュメント名` - ドキュメント更新

#### ステップ3: 開発とコミット

```bash
# ファイル編集
# ...

# 変更を確認
git status
git diff

# ステージング
git add .

# コミット（わかりやすいメッセージで）
git commit -m "feat: Add login form component"

# さらに開発を続ける
# ...

git add .
git commit -m "feat: Add authentication logic"
git commit -m "test: Add login tests"
```

**コミットメッセージの例（Conventional Commits）:**
- `feat:` - 新機能
- `fix:` - バグ修正
- `docs:` - ドキュメント
- `style:` - フォーマット
- `refactor:` - リファクタリング
- `test:` - テスト
- `chore:` - その他

#### ステップ4: GitHubにプッシュ

```bash
# 初回プッシュ（アップストリーム設定）
git push -u origin feature/add-login

# 2回目以降
git push
```

#### ステップ5: Pull Request 作成

**GitHub上で:**
1. リポジトリページにアクセス
2. 「Compare & pull request」ボタンをクリック
3. PR情報を入力:
   ```markdown
   ## 変更内容
   ログイン機能を追加しました。

   ## 関連Issue
   Closes #123

   ## スクリーンショット
   （あれば画像添付）

   ## テスト
   - [ ] ユニットテストが通る
   - [ ] ログイン成功
   - [ ] ログイン失敗時のエラー表示
   ```
4. Reviewers を指定
5. 「Create pull request」をクリック

#### ステップ6: コードレビュー対応

**レビューコメントへの対応:**
```bash
# ファイルを修正
# ...

# コミット
git add .
git commit -m "fix: Address review comments"

# プッシュ（PRに自動反映）
git push
```

#### ステップ7: マージ

**GitHub上で:**
1. レビュー承認を確認
2. 「Merge pull request」をクリック
3. マージ方法を選択:
   - **Merge commit** - すべてのコミットを保持
   - **Squash and merge** - 1つのコミットにまとめる（推奨）
   - **Rebase and merge** - リベースしてマージ
4. 「Confirm merge」
5. 「Delete branch」でブランチ削除

#### ステップ8: ローカルブランチの後始末

```bash
# mainに戻る
git checkout main

# 最新を取得
git pull origin main

# マージ済みブランチを削除
git branch -d feature/add-login

# リモート追跡ブランチも削除
git fetch --prune
```

### 2.3 mainブランチの変更を取り込む

開発中に `main` が更新された場合。

#### 方法1: Merge（推奨）

```bash
# 機能ブランチで作業中
git checkout feature/add-login

# mainの最新を取得
git fetch origin

# mainをマージ
git merge origin/main

# コンフリクトがあれば解決
# ...

# プッシュ
git push
```

#### 方法2: Rebase

```bash
# mainの最新を取得
git fetch origin

# リベース
git rebase origin/main

# コンフリクトがあれば解決して続行
git add .
git rebase --continue

# プッシュ（履歴が変わるので強制プッシュ必要）
git push --force-with-lease
```

---

## 3. GitHub Flowフロー

シンプルで継続的デプロイに適したフロー。

### 3.1 GitHub Flowの原則

1. `main` ブランチは常にデプロイ可能
2. 新しい作業は `main` から分岐
3. ブランチ名はわかりやすく
4. 定期的にプッシュ
5. Pull Request でディスカッション
6. マージ後すぐデプロイ

### 3.2 実践例

#### 新機能追加

```bash
# 1. mainから分岐
git checkout main
git pull origin main
git checkout -b improve-search

# 2. 開発・コミット
git add .
git commit -m "Improve search algorithm"
git push -u origin improve-search

# 3. PR作成（GitHub上で）

# 4. レビュー・マージ

# 5. デプロイ（自動またはマージ後）
```

#### 継続的デプロイとの連携

**.github/workflows/deploy.yml:**
```yaml
name: Deploy

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy to production
        run: ./deploy.sh
```

---

## 4. Git Flowフロー

大規模プロジェクトやリリースサイクルがあるプロジェクト向け。

### 4.1 ブランチ構成

```
main (production)
│
├── develop (development)
│   │
│   ├── feature/xxx
│   ├── feature/yyy
│   └── feature/zzz
│
└── release/v1.0.0
    │
    └── hotfix/critical-bug
```

**ブランチ種類:**
- **main** - 本番環境（常に安定）
- **develop** - 開発ブランチ
- **feature/** - 機能ブランチ
- **release/** - リリース準備ブランチ
- **hotfix/** - 緊急修正ブランチ

### 4.2 機能開発フロー

```bash
# 1. developから機能ブランチ作成
git checkout develop
git pull origin develop
git checkout -b feature/new-dashboard

# 2. 開発
git add .
git commit -m "Add dashboard component"
git push -u origin feature/new-dashboard

# 3. PR作成（develop へマージ）

# 4. マージ後、ブランチ削除
git checkout develop
git pull origin develop
git branch -d feature/new-dashboard
```

### 4.3 リリースフロー

```bash
# 1. developからreleaseブランチ作成
git checkout develop
git pull origin develop
git checkout -b release/v1.2.0

# 2. バージョン番号更新
# package.json, README.md などを更新

git add .
git commit -m "Bump version to 1.2.0"
git push -u origin release/v1.2.0

# 3. テスト・バグ修正
# バグがあれば修正してコミット

# 4. mainへマージ（PR経由）
# GitHub上でPR作成: release/v1.2.0 → main

# 5. タグ付け
git checkout main
git pull origin main
git tag -a v1.2.0 -m "Release version 1.2.0"
git push origin v1.2.0

# 6. developへもマージ（バックマージ）
git checkout develop
git merge main
git push origin develop

# 7. releaseブランチ削除
git branch -d release/v1.2.0
git push origin --delete release/v1.2.0
```

### 4.4 Hotfixフロー

```bash
# 1. mainからhotfixブランチ作成
git checkout main
git pull origin main
git checkout -b hotfix/critical-security-fix

# 2. 緊急修正
git add .
git commit -m "Fix critical security vulnerability"
git push -u origin hotfix/critical-security-fix

# 3. mainへマージ（PR経由）
# GitHub上でPR作成: hotfix/critical-security-fix → main

# 4. タグ付け
git checkout main
git pull origin main
git tag -a v1.2.1 -m "Hotfix: Critical security fix"
git push origin v1.2.1

# 5. developへもマージ
git checkout develop
git merge main
git push origin develop

# 6. hotfixブランチ削除
git branch -d hotfix/critical-security-fix
git push origin --delete hotfix/critical-security-fix
```

---

## 5. オープンソース貢献フロー

他人のリポジトリに貢献する際のフロー。

### 5.1 全体の流れ

1. リポジトリをフォーク
2. クローン
3. ブランチ作成
4. 変更・コミット
5. フォークにプッシュ
6. Pull Request 作成
7. レビュー対応
8. マージ

### 5.2 詳細手順

#### ステップ1: フォーク

**GitHub上で:**
1. 貢献したいリポジトリにアクセス
2. 右上の「Fork」ボタンをクリック
3. 自分のアカウントにフォークが作成される

#### ステップ2: クローン

**Windows:**
```cmd
# フォークをクローン
git clone https://github.com/YOUR_USERNAME/repository.git
cd repository

# オリジナルをupstreamとして追加
git remote add upstream https://github.com/ORIGINAL_OWNER/repository.git

# 確認
git remote -v
```

**Mac:**
```bash
# フォークをクローン
git clone https://github.com/YOUR_USERNAME/repository.git
cd repository

# オリジナルをupstreamとして追加
git remote add upstream https://github.com/ORIGINAL_OWNER/repository.git

# 確認
git remote -v
```

#### ステップ3: ブランチ作成

```bash
# 最新のupstream/mainを取得
git fetch upstream
git checkout main
git merge upstream/main

# 機能ブランチ作成
git checkout -b fix-typo-in-readme
```

#### ステップ4: 変更・コミット

```bash
# ファイル編集
# ...

# コミット
git add .
git commit -m "docs: Fix typo in README"
```

#### ステップ5: フォークにプッシュ

```bash
# 自分のフォークにプッシュ
git push -u origin fix-typo-in-readme
```

#### ステップ6: Pull Request 作成

**GitHub上で:**
1. 自分のフォークページにアクセス
2. 「Compare & pull request」をクリック
3. PR情報を入力:
   ```markdown
   ## 変更内容
   READMEのタイポを修正しました。

   ## 変更箇所
   - 行123: "recieve" → "receive"
   ```
4. 「Create pull request」をクリック

#### ステップ7: レビュー対応

```bash
# レビューコメントに対応
# ファイル修正

git add .
git commit -m "Address review feedback"
git push
```

#### ステップ8: 最新を同期

開発中にオリジナルが更新された場合:

```bash
# upstreamから最新を取得
git fetch upstream

# 自分のブランチにマージ
git merge upstream/main

# コンフリクト解決（あれば）
# ...

# プッシュ
git push
```

### 5.3 フォークの同期

定期的にオリジナルと同期:

```bash
# mainブランチで
git checkout main

# upstreamから取得
git fetch upstream

# マージ
git merge upstream/main

# フォークを更新
git push origin main
```

または **GitHub上で:**
1. フォークページにアクセス
2. 「Sync fork」ボタンをクリック
3. 「Update branch」

---

## 6. Issue駆動開発フロー

Issue を起点とした開発フロー。

### 6.1 全体の流れ

```
Issue作成 → ブランチ作成 → 開発 → PR作成 → レビュー → マージ → Issue自動クローズ
```

### 6.2 実践例

#### ステップ1: Issue 作成

**GitHub上で:**
1. **Issues** → **New issue**
2. 内容記入:
   ```markdown
   ## バグ内容
   ログインフォームでメールアドレスバリデーションが機能していない

   ## 再現手順
   1. ログインページにアクセス
   2. 無効なメールアドレスを入力
   3. 送信ボタンをクリック

   ## 期待される動作
   エラーメッセージが表示される

   ## 実際の動作
   エラーが表示されずに送信される
   ```
3. Label: `bug`
4. Assignee: 自分
5. 「Submit new issue」→ **#123** が作成される

#### ステップ2: Issueからブランチ作成

**GitHub上で（推奨）:**
1. Issue詳細画面の右サイドバー
2. **Development** → **Create a branch**
3. ブランチ名: `123-fix-email-validation`
4. 「Create branch」

**またはローカルで:**
```bash
git checkout main
git pull origin main
git checkout -b 123-fix-email-validation
```

#### ステップ3: 開発

```bash
# ファイル修正
# ...

git add .
git commit -m "fix: Add email validation to login form

Fixes #123"
```

**コミットメッセージでIssue参照:**
- `Fixes #123` - マージ時に自動クローズ
- `Closes #123` - 同上
- `Resolves #123` - 同上
- `Relates to #123` - 参照のみ（クローズしない）

#### ステップ4: PR作成

```bash
git push -u origin 123-fix-email-validation
```

**GitHub上で:**
1. PR作成
2. 説明欄に `Fixes #123` を記載
3. 「Create pull request」

#### ステップ5: マージ

PRがマージされると、Issue #123 が自動的にクローズされる。

### 6.3 複数Issueへの対応

```bash
# コミットメッセージで複数Issue参照
git commit -m "feat: Add search and filter

Fixes #45
Fixes #67
Relates to #89"
```

---

## 7. ホットフィックスフロー

本番環境の緊急バグ修正。

### 7.1 緊急度別フロー

#### 緊急度: 高（即座に対応）

```bash
# 1. mainから直接hotfixブランチ作成
git checkout main
git pull origin main
git checkout -b hotfix/critical-bug

# 2. 修正
git add .
git commit -m "hotfix: Fix critical payment processing bug"

# 3. プッシュ
git push -u origin hotfix/critical-bug

# 4. PR作成（mainへ）
# レビューを簡略化して迅速にマージ

# 5. マージ後、即座にデプロイ

# 6. developへもバックマージ
git checkout develop
git pull origin develop
git merge main
git push origin develop
```

#### 緊急度: 中（テスト後に対応）

```bash
# 1. mainからhotfixブランチ
git checkout main
git pull origin main
git checkout -b hotfix/security-patch

# 2. 修正
git add .
git commit -m "hotfix: Patch security vulnerability"

# 3. テスト環境でテスト
git push -u origin hotfix/security-patch

# 4. PR作成・レビュー

# 5. マージ・デプロイ
```

### 7.2 ホットフィックスのタグ付け

```bash
# mainでタグ付け
git checkout main
git pull origin main
git tag -a v1.2.1 -m "Hotfix: Critical bug fix"
git push origin v1.2.1

# GitHub Releasesで公開
```

---

## 8. リリースフロー

バージョン管理とリリース手順。

### 8.1 セマンティックバージョニング

```
MAJOR.MINOR.PATCH (例: 2.4.1)
```

- **MAJOR** - 互換性のない変更
- **MINOR** - 後方互換性のある機能追加
- **PATCH** - 後方互換性のあるバグ修正

### 8.2 リリース準備

#### ステップ1: リリースブランチ作成

```bash
# developからリリースブランチ
git checkout develop
git pull origin develop
git checkout -b release/v2.0.0
```

#### ステップ2: バージョン更新

**package.json:**
```json
{
  "name": "my-app",
  "version": "2.0.0",
  ...
}
```

**CHANGELOG.md:**
```markdown
## [2.0.0] - 2025-10-13

### Added
- 新しいダッシュボードUI
- ダークモード対応

### Changed
- API エンドポイントを v2 に変更

### Deprecated
- 旧 API v1 は非推奨（v3で削除予定）

### Removed
- レガシー認証システムを削除

### Fixed
- ログインフォームのバグ修正

### Security
- セキュリティ脆弱性を修正
```

```bash
git add .
git commit -m "chore: Bump version to 2.0.0"
git push -u origin release/v2.0.0
```

#### ステップ3: テスト

```bash
# テスト環境でのテスト
npm test
npm run e2e
```

バグがあれば修正:
```bash
git add .
git commit -m "fix: Fix test failures"
git push
```

#### ステップ4: mainへマージ

**GitHub上でPR:**
1. `release/v2.0.0` → `main`
2. レビュー・承認
3. マージ

#### ステップ5: タグ付け

```bash
git checkout main
git pull origin main

# アノテーション付きタグ
git tag -a v2.0.0 -m "Release version 2.0.0

- New dashboard UI
- Dark mode support
- API v2 migration"

git push origin v2.0.0
```

#### ステップ6: GitHub Release 作成

**GitHub上で:**
1. **Releases** → **Draft a new release**
2. **Choose a tag** → `v2.0.0`
3. **Release title** → `v2.0.0 - Dashboard Redesign`
4. **Description** → CHANGELOG からコピー
5. **Attach binaries** - ビルド成果物（あれば）
6. **Publish release**

#### ステップ7: developへバックマージ

```bash
git checkout develop
git pull origin develop
git merge main
git push origin develop
```

#### ステップ8: リリースブランチ削除

```bash
git branch -d release/v2.0.0
git push origin --delete release/v2.0.0
```

### 8.3 自動リリース（GitHub Actions）

**.github/workflows/release.yml:**
```yaml
name: Release

on:
  push:
    tags:
      - 'v*'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm ci

      - name: Build
        run: npm run build

      - name: Create Release
        uses: actions/create-release@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          tag_name: ${{ github.ref }}
          release_name: Release ${{ github.ref }}
          draft: false
          prerelease: false

      - name: Upload Release Asset
        uses: actions/upload-release-asset@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          upload_url: ${{ steps.create_release.outputs.upload_url }}
          asset_path: ./dist/app.zip
          asset_name: app.zip
          asset_content_type: application/zip
```

---

## 🎯 ワークフロー選択ガイド

| プロジェクト種類 | 推奨フロー | 理由 |
|----------------|----------|------|
| 個人プロジェクト | 個人開発フロー | シンプルで十分 |
| 小規模チーム（2-5人） | GitHub Flow | シンプルで継続的デプロイに適する |
| 中規模チーム（5-15人） | Feature Branch | バランスが良い |
| 大規模プロジェクト | Git Flow | 厳格なリリース管理 |
| オープンソース | OSS貢献フロー | フォークベース |
| 緊急対応 | Hotfix フロー | 迅速な修正 |

---

## 📝 ベストプラクティス

### コミットメッセージ

**良い例:**
```
feat: Add user authentication

- Implement JWT-based authentication
- Add login/logout endpoints
- Add password hashing with bcrypt

Closes #123
```

**悪い例:**
```
update files
```

### ブランチ名

**良い例:**
- `feature/user-authentication`
- `bugfix/login-validation`
- `hotfix/security-patch`
- `123-fix-email-validation`（Issue番号付き）

**悪い例:**
- `test`
- `fix`
- `my-branch`

### Pull Request

**良い例:**
- 明確なタイトル
- 変更内容の説明
- スクリーンショット（UI変更の場合）
- テスト結果
- 関連Issue参照

**悪い例:**
- タイトルだけ
- 説明なし
- 巨大なPR（1000行以上の変更）

### コードレビュー

**レビュアーの心得:**
- 建設的なフィードバック
- 具体的な改善提案
- 良い点も指摘する
- タイムリーにレビュー

**PR作成者の心得:**
- 小さく分割したPR
- 自己レビュー済み
- テスト済み
- ドキュメント更新

---

## 🔗 関連ドキュメント

- [Git基本コマンド集](./git-commands.md)
- [GitHubメニュー完全ガイド](./github-ui-guide.md)
- [ブランチ戦略](./branching-strategies.md)
- [Pull Request・Code Review](./pull-request-guide.md)

---

**最終更新**: 2025-10-13
