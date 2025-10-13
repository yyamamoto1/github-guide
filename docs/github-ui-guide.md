# GitHubメニュー完全ガイド

GitHubのすべてのメニュー、UI要素、機能を詳しく解説します。

---

## 📑 目次

1. [トップナビゲーションバー](#1-トップナビゲーションバー)
2. [リポジトリページの構成](#2-リポジトリページの構成)
3. [リポジトリタブメニュー](#3-リポジトリタブメニュー)
4. [Settings（設定）メニュー詳細](#4-settings設定メニュー詳細)
5. [Issues（課題管理）](#5-issues課題管理)
6. [Pull Requests（変更提案）](#6-pull-requests変更提案)
7. [Actions（自動化）](#7-actions自動化)
8. [Projects（プロジェクト管理）](#8-projectsプロジェクト管理)
9. [Wiki（ドキュメント）](#9-wikiドキュメント)
10. [Insights（分析）](#10-insights分析)
11. [個人アカウントメニュー](#11-個人アカウントメニュー)
12. [通知センター](#12-通知センター)

---

## 1. トップナビゲーションバー

GitHubページ上部に常に表示されるグローバルナビゲーション。

### 1.1 左側エリア

#### GitHubロゴ
- クリックでダッシュボードに戻る
- ショートカット: `G` → `D`

#### 検索バー
```
Search or jump to...
```
- **機能**: リポジトリ、コード、Issue、PRを横断検索
- **ショートカット**:
  - Windows/Linux: `Ctrl + K` または `/`
  - Mac: `Cmd + K` または `/`
- **検索演算子**:
  - `repo:ユーザー名/リポジトリ名` - 特定リポジトリ内検索
  - `is:issue` - Issue のみ検索
  - `is:pr` - Pull Request のみ検索
  - `language:python` - 特定言語のコード検索
  - `user:ユーザー名` - 特定ユーザーの検索

**例:**
```
repo:facebook/react is:issue label:bug
→ React リポジトリの bug ラベルが付いた Issue を検索
```

#### Pull requests
- 自分に関連するすべてのPRを表示
  - Created（作成したPR）
  - Assigned（割り当てられたPR）
  - Mentioned（メンションされたPR）
  - Review requests（レビュー依頼されたPR）

#### Issues
- 自分に関連するすべてのIssueを表示
  - Created（作成したIssue）
  - Assigned（割り当てられたIssue）
  - Mentioned（メンションされたIssue）

#### Marketplace
- GitHub Apps や Actions を探す
- 有料/無料ツールの購入・インストール

#### Explore
- トレンドリポジトリ
- トピック別リポジトリ
- イベント情報
- GitHub Collections

### 1.2 右側エリア

#### 通知ベル 🔔
- **数字バッジ**: 未読通知数
- **青い点**: 未読あり
- クリックで通知センター表示
- ショートカット: `G` → `N`

#### プラス（+）メニュー
クリックでドロップダウン表示:
- **New repository** - 新規リポジトリ作成
- **Import repository** - 既存リポジトリインポート
- **New codespace** - Codespace 作成
- **New gist** - コードスニペット共有
- **New organization** - 組織アカウント作成
- **New project** - プロジェクトボード作成

#### プロフィールアイコン
クリックでドロップダウン表示:
- **Signed in as [ユーザー名]** - 現在のログインユーザー
- **Set status** - ステータス設定（絵文字付き）
- **Your profile** - プロフィールページ
- **Your repositories** - リポジトリ一覧
- **Your codespaces** - Codespace 一覧
- **Your organizations** - 所属組織
- **Your projects** - プロジェクト一覧
- **Your stars** - スターしたリポジトリ
- **Your gists** - Gist 一覧
- **Your sponsors** - スポンサー管理
- **Upgrade** - プラン変更
- **Feature preview** - ベータ機能
- **Help** - ヘルプドキュメント
- **Settings** - アカウント設定
- **Sign out** - ログアウト

---

## 2. リポジトリページの構成

特定のリポジトリを開いたときの画面構成。

### 2.1 リポジトリヘッダー

```
👤 ユーザー名 / 📁 リポジトリ名
```

#### リポジトリ名の右側アイコン

**Watch（監視）**
- **Participating and @mentions** - 参加中の会話とメンションのみ
- **All Activity** - すべての活動を通知
- **Ignore** - 通知を受け取らない
- **Custom** - カスタム設定

**Fork（フォーク）**
- リポジトリをフォークする
- フォーク数が表示される

**Star（スター）**
- お気に入り登録
- スター数が表示される
- ショートカット: `G` → `S`（スター済みリポジトリへ）

### 2.2 About（概要）セクション

リポジトリの右サイドバー上部に表示。

- **説明文** - リポジトリの説明
- **Topics（トピック）** - タグ（言語、フレームワークなど）
- **README** - README.md へのリンク
- **Website** - プロジェクトのURL
- **License** - ライセンス情報
- **Stars** - スター数
- **Watching** - ウォッチ数
- **Forks** - フォーク数

**編集方法:**
- リポジトリオーナーは歯車アイコンから編集可能

### 2.3 Releases（リリース）

- バージョン管理
- ダウンロード可能なアーカイブ
- リリースノート

### 2.4 Packages（パッケージ）

- npm、Docker、Maven などのパッケージ
- GitHub Packages で公開されたパッケージ

### 2.5 Deployments（デプロイ）

- デプロイ履歴
- 環境ごとのデプロイ状態

### 2.6 Contributors（コントリビューター）

- コミット数順の貢献者一覧
- 各ユーザーのコミット数

### 2.7 Languages（言語）

- リポジトリで使用されている言語の割合
- カラーバーで視覚的に表示

---

## 3. リポジトリタブメニュー

リポジトリページ上部の横並びタブ。

### 3.1 Code（コード）

**デフォルトビュー** - ファイルツリーとREADME表示。

#### ブランチ選択ドロップダウン
```
main ▼
```
- **Switch branches/tags** - ブランチ/タグ切り替え
- **Find a branch** - ブランチ検索
- **View all branches** - すべてのブランチを表示
- ショートカット: `W`

#### ファイル操作ボタン

**Add file（ファイル追加）**
- **Create new file** - 新規ファイル作成
- **Upload files** - ファイルアップロード

**Code（コードダウンロード）**
- **Clone** - クローンURL（HTTPS/SSH/GitHub CLI）
  ```
  HTTPS:
  https://github.com/username/repo.git

  SSH:
  git@github.com:username/repo.git

  GitHub CLI:
  gh repo clone username/repo
  ```
- **Open with GitHub Desktop** - GitHub Desktop で開く
- **Download ZIP** - ZIPファイルでダウンロード

#### ファイルブラウザ

**表示情報:**
- ファイル/フォルダ名
- 最新コミットメッセージ
- コミッター
- コミット日時

**ファイル種類別アイコン:**
- 📁 フォルダ
- 📄 テキストファイル
- 🖼️ 画像ファイル
- 📊 データファイル
- ⚙️ 設定ファイル

**ショートカット:**
- `T` - ファイルファインダー（ファジー検索）
- `L` - 行へジャンプ
- `W` - ブランチ選択
- `Y` - URL を現在のコミット版に変換

#### ファイルビューア

**テキストファイルを開いたとき:**

**上部ボタン:**
- **Raw** - 生ファイル表示
- **Blame** - 各行の最終変更者表示
- **History** - ファイルの変更履歴
- **Edit** - ファイル編集（権限がある場合）
- **Delete** - ファイル削除（権限がある場合）

**行番号機能:**
- 行番号クリック - 行にパーマリンク
- `Shift + クリック` - 複数行選択
- 選択後 `Y` - パーマリンク生成

**コードビューモード:**
- **Code** - 通常表示
- **Preview** - プレビュー（Markdown等）

**画像ファイルの場合:**
- 画像プレビュー表示
- **2-up** - 新旧比較（横並び）
- **Swipe** - スワイプで比較
- **Onion Skin** - 透過重ね合わせ比較

### 3.2 Issues（課題）

詳細は [5. Issues（課題管理）](#5-issues課題管理) を参照。

### 3.3 Pull requests

詳細は [6. Pull Requests（変更提案）](#6-pull-requests変更提案) を参照。

### 3.4 Actions

詳細は [7. Actions（自動化）](#7-actions自動化) を参照。

### 3.5 Projects

詳細は [8. Projects（プロジェクト管理）](#8-projectsプロジェクト管理) を参照。

### 3.6 Wiki

詳細は [9. Wiki（ドキュメント）](#9-wikiドキュメント) を参照。

### 3.7 Security（セキュリティ）

#### Security Overview（概要）
- セキュリティステータス
- 脆弱性アラート数

#### Security policy（セキュリティポリシー）
- SECURITY.md ファイル
- 脆弱性報告方法

#### Security advisories（セキュリティアドバイザリ）
- 脆弱性の公開/非公開
- CVE ID 取得

#### Dependabot alerts（依存関係アラート）
- 依存パッケージの脆弱性検知
- 自動更新PR作成

#### Code scanning alerts（コードスキャン）
- コードの脆弱性検知
- CodeQL による静的解析

#### Secret scanning alerts（シークレットスキャン）
- APIキー、トークン漏洩検知
- 自動無効化（GitHub連携サービス）

### 3.8 Insights（分析）

詳細は [10. Insights（分析）](#10-insights分析) を参照。

### 3.9 Settings（設定）

詳細は [4. Settings（設定）メニュー詳細](#4-settings設定メニュー詳細) を参照。

---

## 4. Settings（設定）メニュー詳細

**注意:** このメニューはリポジトリのオーナーまたは管理者のみ表示されます。

### 4.1 General（一般設定）

#### Repository name（リポジトリ名）
- リポジトリ名の変更
- 警告: URLが変わるため注意

#### Default branch（デフォルトブランチ）
- デフォルトブランチの変更（通常は `main` または `master`）

#### Features（機能）

**有効/無効の切り替え:**
- ✅ **Wikis** - Wiki機能
- ✅ **Issues** - Issue機能
- ✅ **Sponsorships** - スポンサー機能
- ✅ **Preserve this repository** - Arctic Code Vault保存
- ✅ **Discussions** - ディスカッション機能
- ✅ **Projects** - プロジェクトボード

#### Pull Requests

**マージボタンの種類:**
- ✅ **Allow merge commits** - マージコミット許可
- ✅ **Allow squash merging** - スカッシュマージ許可
- ✅ **Allow rebase merging** - リベースマージ許可

**マージ後の自動処理:**
- ✅ **Automatically delete head branches** - マージ後にブランチ自動削除

#### Archives（アーカイブ）
- **Include Git LFS objects in archives** - LFSオブジェクト含む

#### Danger Zone（危険な操作）

**重要な操作:**
- 🔴 **Change repository visibility** - 可視性変更（Public/Private）
- 🔴 **Disable branch protection rules** - ブランチ保護無効化
- 🔴 **Transfer ownership** - 所有権譲渡
- 🔴 **Archive this repository** - アーカイブ化（読み取り専用）
- 🔴 **Delete this repository** - リポジトリ削除

### 4.2 Access > Collaborators and teams（コラボレーター管理）

#### Manage access（アクセス管理）

**個人ユーザーの追加:**
1. **Add people** ボタンをクリック
2. ユーザー名またはメールアドレス入力
3. 権限レベル選択:
   - **Read** - 読み取り専用
   - **Triage** - IssueとPRの管理
   - **Write** - コードのプッシュ可能
   - **Maintain** - 設定変更可能（一部）
   - **Admin** - 完全な管理者権限

**組織チームの追加:**
1. **Add teams** ボタンをクリック
2. チーム選択
3. 権限レベル選択

### 4.3 Access > Moderation options（モデレーション）

#### Interaction limits（インタラクション制限）
- 新規ユーザーの操作制限
- 一時的なスパム対策

#### Code review limits（コードレビュー制限）
- レビュー権限の制限

### 4.4 Code and automation > Branches（ブランチ）

#### Branch protection rules（ブランチ保護ルール）

**保護ルールの追加:**
1. **Add rule** ボタンをクリック
2. ブランチ名パターン入力（例: `main`）
3. 保護設定を選択:

**Protect matching branches（マッチするブランチを保護）**

基本的な保護:
- ✅ **Require a pull request before merging** - PR必須
  - Require approvals（承認必須数: 1-6）
  - Dismiss stale pull request approvals when new commits are pushed
  - Require review from Code Owners
- ✅ **Require status checks to pass before merging** - ステータスチェック必須
  - Require branches to be up to date before merging
  - Status checks（必要なチェック選択）
- ✅ **Require conversation resolution before merging** - 会話解決必須
- ✅ **Require signed commits** - 署名付きコミット必須
- ✅ **Require linear history** - 直線的な履歴必須
- ✅ **Require deployments to succeed before merging** - デプロイ成功必須

管理者向け設定:
- ✅ **Do not allow bypassing the above settings** - 管理者も従う
- ✅ **Restrict who can push to matching branches** - プッシュ権限制限
- ✅ **Allow force pushes** - フォースプッシュ許可
- ✅ **Allow deletions** - ブランチ削除許可

#### Default branch（デフォルトブランチ）
- デフォルトブランチの切り替え

### 4.5 Code and automation > Tags（タグ）

#### Protected tags（保護タグ）
- タグの作成/削除制限
- バージョンタグの保護

### 4.6 Code and automation > Actions（Actions）

#### Actions permissions（Actions権限）

**リポジトリでのActions使用許可:**
- ⚪ **Disable Actions** - Actions無効
- ⚪ **Allow all actions and reusable workflows** - すべて許可
- ⚪ **Allow [organization] actions and reusable workflows** - 組織内のみ
- ⚪ **Allow select actions and reusable workflows** - 選択したもののみ

#### Workflow permissions（ワークフロー権限）
- **Read repository contents and packages permissions** - 読み取りのみ
- **Read and write permissions** - 読み書き可能

#### Artifact and log retention（成果物とログの保持）
- 保持日数設定（1-400日）

#### Fork pull request workflows（フォークPRワークフロー）
- フォークからのPRでのActions実行設定

### 4.7 Code and automation > Webhooks（Webhook）

#### Webhooks
外部サービスとの連携設定。

**Webhook追加:**
1. **Add webhook** ボタンをクリック
2. 設定項目:
   - **Payload URL** - 送信先URL
   - **Content type** - `application/json` または `application/x-www-form-urlencoded`
   - **Secret** - 認証用シークレット
   - **SSL verification** - SSL検証の有効化
   - **Which events would you like to trigger this webhook?**
     - Just the push event（プッシュのみ）
     - Send me everything（すべて）
     - Let me select individual events（個別選択）

**イベント種類（一部）:**
- Push
- Pull request
- Issues
- Issue comment
- Release
- Deployment
- Star
- Fork
- Watch

### 4.8 Code and automation > Environments（環境）

#### Deployment environments（デプロイ環境）

**環境の作成:**
1. **New environment** ボタンをクリック
2. 環境名入力（例: `production`, `staging`, `development`）
3. 環境設定:

**Protection rules（保護ルール）:**
- **Required reviewers** - デプロイ承認者必須
- **Wait timer** - 待機時間設定
- **Deployment branches** - デプロイ可能ブランチ制限

**Environment secrets（環境シークレット）:**
- 環境固有の秘密情報

### 4.9 Code and automation > Codespaces（Codespace）

#### Codespaces設定
- Codespace使用許可
- マシンタイプ制限
- タイムアウト設定

### 4.10 Code and automation > Pages（GitHub Pages）

#### GitHub Pages設定

**サイト公開設定:**
1. **Source** - ソース選択
   - Deploy from a branch（ブランチから）
   - GitHub Actions（Actionsから）
2. **Branch** - 公開ブランチ選択
   - ブランチ名（例: `main`, `gh-pages`）
   - フォルダ選択（`/ (root)` または `/docs`）
3. **Custom domain** - カスタムドメイン設定
4. **Enforce HTTPS** - HTTPS強制

**公開後:**
```
Your site is published at https://username.github.io/repository/
```

### 4.11 Security > Code security and analysis（コードセキュリティ）

#### Dependency graph（依存関係グラフ）
- ✅ 依存パッケージの可視化

#### Dependabot alerts（Dependabotアラート）
- ✅ 脆弱性検知の有効化

#### Dependabot security updates（セキュリティ更新）
- ✅ 自動セキュリティ更新PR

#### Dependabot version updates（バージョン更新）
- dependabot.yml ファイルで設定

**設定例:**
```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
```

#### Code scanning（コードスキャン）
- CodeQL によるセキュリティ解析
- **Setup** で有効化

#### Secret scanning（シークレットスキャン）
- ✅ APIキー等の漏洩検知
- パブリックリポジトリは自動有効

### 4.12 Security > Deploy keys（デプロイキー）

#### Deploy keys（デプロイ専用SSHキー）

**キー追加:**
1. **Add deploy key** ボタンをクリック
2. **Title** - キーの名前
3. **Key** - 公開鍵（`ssh-rsa ...`）
4. ✅ **Allow write access** - 書き込み許可

**用途:**
- CI/CDサーバーからのデプロイ
- 読み取り専用クローン

### 4.13 Security > Secrets and variables（シークレットと変数）

#### Actions secrets（Actionsシークレット）

**リポジトリシークレット:**
1. **New repository secret** ボタンをクリック
2. **Name** - シークレット名（大文字推奨: `API_KEY`）
3. **Value** - 秘密情報（暗号化保存）

**環境シークレット:**
- 環境ごとに異なるシークレット設定

**組織シークレット:**
- 組織レベルでの共有シークレット

#### Dependabot secrets
- Dependabot用のシークレット

#### Actions variables（Actions変数）
- 暗号化不要な設定値

### 4.14 Integrations > GitHub Apps（GitHub Apps）

#### Installed GitHub Apps
- インストール済みアプリ一覧
- 権限管理
- アンインストール

### 4.15 Integrations > Email notifications（メール通知）

#### Email notification settings
- プッシュ通知の送信先メールアドレス
- コミット差分の送信設定

---

## 5. Issues（課題管理）

### 5.1 Issues一覧画面

#### フィルタータブ
```
[Open] [👤 Assigned] [💬 Mentioned] [Closed]
```

- **Open** - 未解決Issue
- **Assigned** - 自分にアサインされたIssue
- **Mentioned** - 自分がメンションされたIssue
- **Closed** - 解決済みIssue

#### 検索・フィルター

**検索ボックス:**
```
is:open is:issue assignee:@me
```

**フィルター演算子:**
- `is:open` / `is:closed` - 状態
- `is:issue` / `is:pr` - 種類
- `assignee:ユーザー名` - 担当者
- `label:バグ` - ラベル
- `milestone:v1.0` - マイルストーン
- `author:ユーザー名` - 作成者
- `mentions:ユーザー名` - メンション
- `no:assignee` - 担当者なし
- `sort:created-asc` - 作成日昇順
- `sort:updated-desc` - 更新日降順

**例:**
```
is:open label:bug assignee:@me
→ 自分にアサインされた未解決のバグIssue
```

#### ソート
```
[Newest] [Oldest] [Most commented] [Least commented] [Recently updated] [Least recently updated]
```

#### アクションボタン

**Labels（ラベル管理）**
- 新規ラベル作成
- ラベル編集/削除
- 色とアイコン設定

**Milestones（マイルストーン管理）**
- マイルストーン作成
- 期日設定
- 進捗管理

**New issue（新規Issue作成）**

### 5.2 Issue作成画面

#### Title（タイトル）
```
Issue タイトルを入力
```

#### Comment（コメント）

**Markdown エディター:**
- **Write** - 編集モード
- **Preview** - プレビューモード

**ツールバー:**
- **B** - 太字
- **I** - 斜体
- **Header** - 見出し
- **Quote** - 引用
- **Code** - コード
- **Link** - リンク
- **Bulleted list** - 箇条書き
- **Numbered list** - 番号付きリスト
- **Task list** - タスクリスト
- **@Mention** - メンション
- **Reference** - Issue/PR参照
- **Attach files** - ファイル添付

**便利な記法:**
```markdown
# 見出し1
## 見出し2

**太字** *斜体* ~~取り消し線~~

- 箇条書き
1. 番号付きリスト

- [ ] タスク1
- [x] タスク2（完了）

@ユーザー名 - メンション
#123 - Issue参照

`インラインコード`

​```python
def hello():
    print("Hello")
​```

![画像説明](URL)
[リンクテキスト](URL)
```

#### 右サイドバー

**Assignees（担当者）**
- 担当者の割り当て
- 複数選択可能

**Labels（ラベル）**
- ラベルの付与
- 複数選択可能
- 例: `bug`, `enhancement`, `documentation`

**Projects（プロジェクト）**
- プロジェクトボードに追加

**Milestone（マイルストーン）**
- マイルストーンに追加

**Development（開発）**
- リンクしたPRやブランチ
- **Create a branch** - Issue用ブランチ作成

**Helpful resources（ヘルプ）**
- GitHub Docs へのリンク

#### 送信ボタン
- **Submit new issue** - Issue作成

### 5.3 Issue詳細画面

#### Issue本体表示
- タイトル
- 番号（#123）
- 状態（Open/Closed）
- 作成者・作成日時

#### コメント欄
- タイムライン形式で表示
- コメント追加
- 絵文字リアクション

**コメント操作:**
- **Edit** - 編集
- **Quote reply** - 引用返信
- **Delete** - 削除（自分のコメント）
- **Hide** - 非表示（管理者のみ）
- **Report** - 報告

#### Issueアクション

**右上ボタン:**
- **Edit** - タイトル編集
- **New issue** - 新規Issue作成
- **Lock conversation** - 会話のロック
- **Pin issue** - Issue ピン留め
- **Transfer issue** - Issue 転送

**下部ボタン:**
- **Close issue** - Issue を閉じる
- **Comment** - コメント投稿
- **Close with comment** - コメントして閉じる

#### 通知設定
```
[🔔 Subscribe] または [🔕 Unsubscribe]
```

#### Issue 参照
他のIssueやコミットから参照されたリンクバック表示。

### 5.4 Issueテンプレート

**設定方法:**

1. `.github/ISSUE_TEMPLATE/` ディレクトリ作成
2. テンプレートファイル作成

**バグ報告テンプレート例:**
```.github/ISSUE_TEMPLATE/bug_report.md
---
name: Bug Report
about: バグを報告する
title: '[BUG] '
labels: bug
assignees: ''
---

**バグの説明**
何が起こっているかを明確に説明してください。

**再現手順**
1. '...' にアクセス
2. '....' をクリック
3. '....' にスクロール
4. エラーが表示される

**期待される動作**
本来どうあるべきかを説明してください。

**スクリーンショット**
該当する場合、スクリーンショットを追加してください。

**環境:**
 - OS: [例: Windows 11]
 - ブラウザ: [例: Chrome 120]
 - バージョン: [例: 1.2.3]

**追加情報**
その他の情報があれば追加してください。
```

**機能リクエストテンプレート例:**
```.github/ISSUE_TEMPLATE/feature_request.md
---
name: Feature Request
about: 新機能を提案する
title: '[FEATURE] '
labels: enhancement
assignees: ''
---

**機能の説明**
実現したい機能を明確に説明してください。

**解決したい課題**
この機能がどのような問題を解決するかを説明してください。
例: [...する時に、いつも...]

**提案する解決策**
どのように実装すべきか、あなたの考えを説明してください。

**代替案**
検討した他のアプローチがあれば説明してください。

**追加情報**
その他の情報があれば追加してください。
```

**config.yml で選択式に:**
```.github/ISSUE_TEMPLATE/config.yml
blank_issues_enabled: false
contact_links:
  - name: 質問・サポート
    url: https://github.com/username/repo/discussions
    about: 使い方の質問はこちら
```

---

## 6. Pull Requests（変更提案）

### 6.1 Pull Requests一覧画面

#### フィルタータブ
```
[Open] [👤 Assigned] [💬 Mentioned] [📝 Review requests] [Closed]
```

- **Open** - 未マージPR
- **Assigned** - 自分にアサインされたPR
- **Mentioned** - 自分がメンションされたPR
- **Review requests** - レビュー依頼されたPR
- **Closed** - クローズ済みPR

#### 検索・フィルター

**フィルター演算子:**
- `is:open` / `is:closed` / `is:merged` - 状態
- `is:pr` - PR
- `review:approved` - 承認済み
- `review:changes-requested` - 変更要求あり
- `review:required` - レビュー必須
- `draft:true` - ドラフトPR
- `assignee:ユーザー名` - 担当者
- `label:ラベル` - ラベル
- `author:ユーザー名` - 作成者
- `base:ブランチ名` - マージ先ブランチ
- `head:ブランチ名` - マージ元ブランチ

**例:**
```
is:open is:pr review:required assignee:@me
→ 自分がレビューすべき未マージPR
```

### 6.2 Pull Request作成画面

#### Compare changes（変更比較）

**ブランチ選択:**
```
base: main  ←  compare: feature-branch
```
- **base** - マージ先（通常 `main`）
- **compare** - マージ元（機能ブランチ）

#### Able to merge（マージ可否）
```
✅ Able to merge. These branches can be automatically merged.
```
または
```
❌ Can't automatically merge. You'll need to resolve conflicts.
```

#### PR作成フォーム

**Title（タイトル）**
```
PRタイトルを入力
```

**Comment（説明）**
Issueと同様のMarkdownエディター。

**テンプレート例:**
```markdown
## 変更内容
このPRで何を変更したか説明してください。

## 関連Issue
Closes #123

## 変更種類
- [ ] バグ修正
- [ ] 新機能
- [ ] ドキュメント更新
- [ ] リファクタリング

## テスト方法
1. ...
2. ...

## スクリーンショット
該当する場合、スクリーンショットを追加してください。

## チェックリスト
- [ ] コードレビューを受けた
- [ ] テストが通る
- [ ] ドキュメントを更新した
```

**Reviewers（レビュアー）**
- レビュアーを指定
- チーム指定も可能

**Assignees（担当者）**
- PR担当者を指定

**Labels（ラベル）**
- ラベル付与

**Projects（プロジェクト）**
- プロジェクトボードに追加

**Milestone（マイルストーン）**
- マイルストーン設定

**Development（開発）**
- リンクするIssue選択
- `Closes #123` で自動クローズ

#### PRタイプ選択

**Create pull request（通常のPR）**
- すぐにレビュー可能

**Create draft pull request（ドラフトPR）**
- 作業中を示す
- レビュー不要
- 準備完了後に **Ready for review** に変更

### 6.3 Pull Request詳細画面

#### タブメニュー

**Conversation（会話）**
- タイムライン表示
- コメント
- レビュー結果
- ステータスチェック
- マージボタン

**Commits（コミット）**
- PR内の全コミット一覧
- 各コミットのdiff

**Checks（チェック）**
- CI/CDステータス
- Actions実行結果
- 失敗時のログ

**Files changed（変更ファイル）**
- ファイル差分表示
- インラインコメント
- レビュー機能

#### Conversation タブ詳細

**ステータスバッジ:**
```
🟢 Open  /  🟣 Merged  /  🔴 Closed
```

**マージステータス:**
```
✅ This branch has no conflicts with the base branch
```
または
```
❌ This branch has conflicts that must be resolved
```

**レビューステータス:**
- ✅ Approved（承認済み）
- 🔄 Changes requested（変更要求）
- 💬 Commented（コメントのみ）
- ⏳ Review required（レビュー待ち）

**Checks ステータス:**
- ✅ All checks have passed
- ⏳ Some checks haven't completed yet
- ❌ Some checks were not successful

**マージボタン:**
```
[Merge pull request ▼]
```

**マージ方法選択:**
- **Create a merge commit** - マージコミット作成
  ```
  git merge --no-ff feature-branch
  ```
- **Squash and merge** - コミットをまとめてマージ
  ```
  git merge --squash feature-branch
  ```
- **Rebase and merge** - リベースしてマージ
  ```
  git rebase main && git merge feature-branch
  ```

**マージ後:**
```
✅ Pull request successfully merged and closed
[Delete branch] ボタン表示
```

#### Files changed タブ詳細

**ファイル差分表示:**

**ヘッダー:**
```
[Viewed] ファイル名  [💬] [⋯]
```
- **Viewed** - 確認済みチェック
- **💬** - コメント数
- **⋯** - ファイルメニュー（生ファイル表示等）

**差分表示モード:**
- **Unified** - 統合表示（デフォルト）
- **Split** - 分割表示（新旧横並び）

**行コメント:**
- 行番号の `+` ボタンでコメント追加
- `Shift + クリック` で複数行選択
- **Add single comment** - 即座にコメント投稿
- **Start a review** - レビューに追加（一括投稿）

**コメントタイプ:**
- **Comment** - 通常コメント
- **Approve** - 承認
- **Request changes** - 変更要求

**レビュー完了:**
```
[Finish your review]
```
- コメントまとめて投稿
- レビュー結果選択

**フィルター:**
```
[Conversations] [⚠️ 5 unresolved] [✅ 2 resolved]
```

**Viewed チェック:**
- ファイル確認済みマーク
- 未確認ファイルが一目瞭然

### 6.4 Pull Requestテンプレート

**設定方法:**

**単一テンプレート:**
```.github/pull_request_template.md
## 変更内容
このPRで何を変更したか説明してください。

## 関連Issue
Closes #

## 変更種類
- [ ] バグ修正 (Bug fix)
- [ ] 新機能 (New feature)
- [ ] 破壊的変更 (Breaking change)
- [ ] ドキュメント更新 (Documentation update)

## テスト方法
1. ...
2. ...

## スクリーンショット（該当する場合）


## チェックリスト
- [ ] 自分でコードをレビューした
- [ ] コードにコメントを追加した（特に分かりにくい箇所）
- [ ] ドキュメントを更新した
- [ ] 変更によって新しい警告が発生しない
- [ ] テストを追加した（新機能の場合）
- [ ] すべてのテストが通る
- [ ] 依存関係を更新した
```

**複数テンプレート:**
```.github/PULL_REQUEST_TEMPLATE/bug_fix.md
```.github/PULL_REQUEST_TEMPLATE/feature.md
など複数作成可能。

**PR作成時にURLで指定:**
```
?template=bug_fix.md
```

---

## 7. Actions（自動化）

### 7.1 Actions一覧画面

#### ワークフロー一覧（左サイドバー）
- 各ワークフロー名
- 最終実行ステータス
- クリックで該当ワークフローの実行履歴

#### 実行履歴（中央）
- ワークフロー実行の一覧
- ステータス（成功/失敗/実行中）
- トリガー（push/PR/schedule等）
- 実行者
- 実行時刻
- 所要時間

**ステータスアイコン:**
- ✅ Success（成功）
- ❌ Failure（失敗）
- 🟡 In progress（実行中）
- ⚪ Cancelled（キャンセル）
- ⏭️ Skipped（スキップ）

#### フィルター
```
[Event] [Status] [Branch] [Actor]
```
- **Event** - トリガー種類（push, pull_request, schedule等）
- **Status** - 成功/失敗
- **Branch** - ブランチ
- **Actor** - 実行者

#### アクションボタン

**New workflow（新規ワークフロー）**
- テンプレートから作成
- 自分で作成

**Run workflow（手動実行）**
- 手動トリガーワークフロー用

### 7.2 ワークフロー実行詳細

#### 実行サマリー
- ワークフロー名
- トリガー
- 実行者
- コミット情報
- ステータス
- 所要時間

#### Jobs（ジョブ一覧）（左サイドバー）
- 各ジョブのステータス
- 並列実行の場合、複数表示

#### ジョブ詳細（中央）
- 各ステップの実行ログ
- 展開/折りたたみ可能
- エラー箇所のハイライト

**ステップ表示:**
```
✅ Set up job
✅ Run actions/checkout@v3
✅ Set up Node.js
✅ Install dependencies
✅ Run tests
❌ Build
```

**ログ操作:**
- クリックで展開
- **View raw logs** - 生ログ表示
- **Download log archive** - ログダウンロード
- **Search logs** - ログ検索

#### 再実行ボタン
```
[Re-run all jobs ▼]
```
- **Re-run all jobs** - すべてのジョブ再実行
- **Re-run failed jobs** - 失敗したジョブのみ再実行

#### Artifacts（成果物）
- ワークフローで生成されたファイル
- ダウンロード可能
- 保持期限設定可能

**例:**
- ビルド成果物
- テストレポート
- カバレッジレポート

### 7.3 ワークフロー作成

#### 基本構造

```.github/workflows/ci.yml
name: CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

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

    - name: Run tests
      run: npm test

    - name: Build
      run: npm run build
```

#### トリガー種類（on:）

**Push:**
```yaml
on:
  push:
    branches:
      - main
      - 'releases/**'
    paths:
      - 'src/**'
```

**Pull Request:**
```yaml
on:
  pull_request:
    types: [opened, synchronize, reopened]
```

**Schedule（定期実行）:**
```yaml
on:
  schedule:
    - cron: '0 0 * * *'  # 毎日0時
```

**Workflow Dispatch（手動実行）:**
```yaml
on:
  workflow_dispatch:
    inputs:
      environment:
        description: 'Environment to deploy'
        required: true
        default: 'staging'
```

**複数トリガー:**
```yaml
on: [push, pull_request, workflow_dispatch]
```

#### ランナー（runs-on:）
- `ubuntu-latest`
- `windows-latest`
- `macos-latest`
- `ubuntu-22.04`（特定バージョン）
- `self-hosted`（セルフホスト）

#### よく使うActions

**Checkout:**
```yaml
- uses: actions/checkout@v3
```

**Node.js セットアップ:**
```yaml
- uses: actions/setup-node@v3
  with:
    node-version: '18'
    cache: 'npm'
```

**Python セットアップ:**
```yaml
- uses: actions/setup-python@v4
  with:
    python-version: '3.11'
```

**成果物アップロード:**
```yaml
- uses: actions/upload-artifact@v3
  with:
    name: build-files
    path: dist/
```

**成果物ダウンロード:**
```yaml
- uses: actions/download-artifact@v3
  with:
    name: build-files
```

**キャッシュ:**
```yaml
- uses: actions/cache@v3
  with:
    path: ~/.npm
    key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
```

#### シークレットの使用

```yaml
- name: Deploy
  env:
    API_KEY: ${{ secrets.API_KEY }}
  run: ./deploy.sh
```

#### マトリックス戦略

```yaml
jobs:
  test:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [ubuntu-latest, windows-latest, macos-latest]
        node-version: [16, 18, 20]

    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-node@v3
      with:
        node-version: ${{ matrix.node-version }}
```

---

## 8. Projects（プロジェクト管理）

### 8.1 Projects概要

GitHubのプロジェクト管理機能。カンバンボードやテーブルビューで Issue と PR を管理。

**Projects (classic) と Projects (beta/new) の違い:**
- **Projects (classic)** - 従来版、シンプル
- **Projects (new)** - 新版、高機能（推奨）

### 8.2 Projects (new) の作成

#### プロジェクト作成
1. リポジトリの **Projects** タブ
2. **Link a project** → **New project**
3. テンプレート選択:
   - **Board** - カンバンボード
   - **Table** - テーブルビュー
   - **Roadmap** - ロードマップビュー
   - **Start from scratch** - 空のプロジェクト

#### プロジェクト設定
- プロジェクト名
- 説明
- アクセス権限

### 8.3 ビュータイプ

#### Board（カンバンボード）

**デフォルトカラム:**
- 📋 **To Do** - 未着手
- 🚧 **In Progress** - 進行中
- ✅ **Done** - 完了

**カード操作:**
- ドラッグ&ドロップで移動
- カード追加（+ ボタン）
- Issue/PR を追加

**カラム操作:**
- カラム追加
- カラム名変更
- カラム並び替え
- カラム削除

#### Table（テーブルビュー）

**スプレッドシート形式:**
- 行: Issue/PR
- 列: フィールド（カスタマイズ可能）

**デフォルトフィールド:**
- Title（タイトル）
- Assignees（担当者）
- Status（ステータス）
- Labels（ラベル）
- Repository（リポジトリ）

**カスタムフィールド追加:**
- **Text** - テキスト
- **Number** - 数値
- **Date** - 日付
- **Single select** - 単一選択
- **Iteration** - イテレーション（スプリント）

**フィルター:**
```
status:In Progress assignee:@me
```

**ソート:**
- 任意のカラムでソート

**グループ化:**
- Status別
- Assignee別
- Label別

#### Roadmap（ロードマップ）

**タイムライン表示:**
- ガントチャート形式
- 開始日・終了日でバー表示
- マイルストーン管理

### 8.4 プロジェクトアイテム管理

#### アイテム追加

**既存Issue/PR追加:**
1. **+ Add item**
2. Issue/PR番号入力または検索
3. 選択して追加

**新規アイテム作成:**
1. カラム内の **+ Add item**
2. タイトル入力
3. **Create new issue** - Issueとして作成
4. **Add as draft** - ドラフトアイテムとして追加

#### アイテム操作
- ドラッグ&ドロップで移動
- ステータス変更
- フィールド編集
- アイテム削除

#### フィルター

**例:**
```
status:"In Progress"
assignee:@me
label:bug
no:assignee
```

**保存済みビュー:**
- フィルター設定を保存
- 複数ビューを切り替え

### 8.5 自動化（Workflows）

#### デフォルトワークフロー
- **Item added to project** - プロジェクト追加時
- **Item closed** - アイテムクローズ時
- **Item reopened** - アイテム再オープン時
- **Pull request merged** - PRマージ時

**アクション例:**
- ステータスを "Done" に設定
- ラベルを追加
- 担当者を設定

#### カスタムワークフロー

**例: PRマージ時にDoneに移動**
```
When: Pull request merged
Then: Set status to Done
```

**例: Issueクローズ時にアーカイブ**
```
When: Issue closed
Then: Archive item
```

### 8.6 Projects設定

#### Settings（設定）

**General:**
- プロジェクト名
- 説明
- README
- アクセス制御

**Manage access（アクセス管理）:**
- ベース権限（Public/Private）
- コラボレーター追加
- 権限レベル（Read/Write/Admin）

**Workflows（ワークフロー）:**
- 自動化ルール設定
- 有効/無効切り替え

**Danger zone（危険な操作）:**
- プロジェクト削除
- プロジェクトクローズ

---

## 9. Wiki（ドキュメント）

### 9.1 Wiki概要

リポジトリのドキュメント専用スペース。

**特徴:**
- Markdown記法
- 履歴管理（Git）
- サイドバー
- フッター
- 検索機能

### 9.2 Wikiの有効化

1. **Settings** → **Features**
2. ✅ **Wikis** をチェック

### 9.3 Wikiページ作成

#### 初回作成
1. **Wiki** タブをクリック
2. **Create the first page**
3. ページ編集

#### ページ追加
1. **New Page** ボタン
2. ページタイトル入力
3. 内容編集
4. **Save Page**

### 9.4 Wiki編集

#### エディター

**Markdown モード:**
- **Edit** - 編集
- **Preview** - プレビュー

**ツールバー:**
- 見出し、リスト、リンク、画像等

**編集完了:**
- **Save Page** - 保存
- **Cancel** - キャンセル

#### ページタイトルの命名規則
- スペース使用可能: `Getting Started`
- URLは自動変換: `Getting-Started`

### 9.5 Wikiナビゲーション

#### サイドバー（_Sidebar）

**作成方法:**
1. **New Page**
2. タイトル: `_Sidebar`
3. 内容をMarkdownで記述

**例:**
```markdown
## ドキュメント

- [ホーム](Home)
- [インストール](Installation)
- [使い方](Usage)
- [API リファレンス](API-Reference)
- [FAQ](FAQ)

## 開発者向け

- [コントリビューション](Contributing)
- [開発環境構築](Development-Setup)
```

#### フッター（_Footer）

**作成方法:**
1. **New Page**
2. タイトル: `_Footer`
3. 内容を記述

**例:**
```markdown
© 2025 My Project | [ライセンス](License) | [Code of Conduct](Code-of-Conduct)
```

### 9.6 Wiki履歴管理

#### ページ履歴
- **Page History** - 変更履歴表示
- 各リビジョンの差分表示
- 過去バージョンへの復元

#### Git クローン

Wikiは独立したGitリポジトリ。

**クローンURL:**
```bash
git clone https://github.com/username/repo.wiki.git
```

**ローカル編集後プッシュ:**
```bash
git add .
git commit -m "Update documentation"
git push
```

### 9.7 Wiki検索

**検索ボックス:**
- Wiki内全文検索
- ページタイトル・内容を検索

---

## 10. Insights（分析）

### 10.1 Insightsタブ概要

リポジトリの活動状況、統計情報を可視化。

**メニュー（左サイドバー）:**
- Pulse
- Contributors
- Community
- Commits
- Code frequency
- Dependency graph
- Network
- Forks
- Traffic（Private リポジトリのみ）

### 10.2 Pulse（概要）

**期間選択:**
- Last 24 hours
- Last 3 days
- Last week
- Last month

**表示内容:**
- マージされたPR数
- オープンされたIssue数
- クローズされたIssue数
- 新規コントリビューター
- リリース
- コミット数

**アクティブなPR・Issue:**
- 最近のアクティビティ一覧

### 10.3 Contributors（コントリビューター）

**グラフ表示:**
- 時系列のコミット数
- コントリビューター別の色分け

**コントリビューターリスト:**
- コミット数順
- 各ユーザーのコミット数
- Additions（追加行数）
- Deletions（削除行数）

### 10.4 Community（コミュニティ）

**コミュニティプロフィールチェックリスト:**

✅ **推奨ファイル:**
- Description（説明）
- README.md
- CODE_OF_CONDUCT.md（行動規範）
- CONTRIBUTING.md（コントリビューションガイド）
- LICENSE（ライセンス）
- SECURITY.md（セキュリティポリシー）
- Issue templates
- Pull request template

**進捗表示:**
```
Community profile: 75% complete
```

### 10.5 Commits（コミット）

**コミットアクティビティグラフ:**
- 週ごとのコミット数
- 1年分のデータ

**日別・時間別ヒートマップ:**
- 曜日×時間帯のコミット傾向
- 濃淡でコミット数を表示

### 10.6 Code frequency（コード追加削減頻度）

**グラフ:**
- 緑: Additions（追加行数）
- 赤: Deletions（削除行数）
- 週単位の推移

**期間:**
- リポジトリ作成時からの全期間

### 10.7 Dependency graph（依存関係グラフ）

**Dependencies（依存関係）:**
- 使用している依存パッケージ一覧
- パッケージ名、バージョン
- ライセンス情報

**Dependents（依存者）:**
- このリポジトリに依存しているリポジトリ
- パブリックリポジトリのみ

**脆弱性アラート:**
- 脆弱性のあるパッケージにバッジ表示

### 10.8 Network（ネットワーク）

**フォークネットワークグラフ:**
- リポジトリとフォークの関係図
- ブランチの分岐・マージ
- コミット履歴の可視化

**操作:**
- ズーム
- 時間範囲スライダー
- ブランチフィルター

### 10.9 Forks（フォーク）

**フォーク一覧:**
- フォーク数
- 各フォークのスター数
- 最終更新日
- フォーク先へのリンク

**ソート:**
- Newest（新しい順）
- Oldest（古い順）
- Most starred（スター数順）
- Recently updated（最近更新順）

### 10.10 Traffic（トラフィック）

**注意:** Privateリポジトリ、または管理者のみ閲覧可能。

#### Git clones（クローン数）

**グラフ:**
- 過去2週間のクローン数
- Unique cloners（ユニーククローナー数）
- Total clones（総クローン数）

#### Visitors（訪問者）

**グラフ:**
- 過去2週間の訪問者数
- Unique visitors（ユニーク訪問者数）
- Total views（総閲覧数）

#### Popular content（人気コンテンツ）

**ページビュー:**
- どのパスが閲覧されたか
- Unique visitors
- Total views

#### Referring sites（参照サイト）

**流入元:**
- どのサイトからアクセスがあったか
- Unique visitors
- Total views

**例:**
- google.com
- twitter.com
- stackoverflow.com

---

## 11. 個人アカウントメニュー

右上のプロフィールアイコンをクリックしたときのメニュー詳細。

### 11.1 Your profile（プロフィール）

**プロフィールページ:**
- プロフィール画像
- 名前
- Bio（自己紹介）
- 所在地
- ウェブサイト
- Twitter
- 組織
- Achievements（実績バッジ）

**ピン留めリポジトリ:**
- 最大6個
- Customize your pins で変更

**コントリビューショングラフ:**
- 過去1年の活動ヒートマップ
- 緑の濃淡でコミット頻度表示

**アクティビティフィード:**
- リポジトリ作成
- Issue/PR作成
- コミット
- スター

### 11.2 Your repositories（リポジトリ）

**リポジトリ一覧:**
- 自分が所有するリポジトリ
- コラボレーター参加リポジトリ

**フィルター:**
- Type（Public/Private/Sources/Forks）
- Language（言語）
- Sort（Name/Stars/Updated）

**検索:**
```
Find a repository...
```

### 11.3 Your projects（プロジェクト）

**プロジェクト一覧:**
- ユーザーレベルのプロジェクト
- リポジトリレベルのプロジェクト

**New project:**
- 新規プロジェクト作成

### 11.4 Your stars（スター）

**スター済みリポジトリ一覧:**
- スターしたリポジトリ
- スター日時

**フィルター:**
- Language
- Sort（Recently starred/Most stars/Recently active）

**Lists:**
- スターリスト作成
- カテゴリ分け

### 11.5 Your gists（Gist）

**Gist一覧:**
- 公開Gist
- シークレットGist

**New gist:**
- 新規Gist作成

### 11.6 Settings（設定）

詳細な個人アカウント設定。

#### Public profile（公開プロフィール）
- Name
- Public email
- Bio
- URL
- Twitter
- Company
- Location

#### Account（アカウント）
- ユーザー名変更
- パスワード変更
- アカウント削除

#### Appearance（外観）
- **Theme（テーマ）:**
  - Light（ライト）
  - Dark（ダーク）
  - Dark dimmed（ダークディム）
  - Sync with system（システム設定に同期）

#### Accessibility（アクセシビリティ）
- キーボードショートカット
- モーションの制限

#### Notifications（通知）
- メール通知設定
- Web通知設定
- 通知フィルター

**通知の種類:**
- Participating（参加中）
- Watching（監視中）
- @mentions（メンション）
- CI activity（CI アクティビティ）
- Dependabot alerts

**通知先:**
- メールアドレス選択
- GitHub上のみ

#### Billing and plans（課金とプラン）
- 現在のプラン
- 使用状況
- プラン変更
- 支払い方法

**プラン種類:**
- **Free** - 無料
  - Unlimited public repositories
  - Unlimited private repositories
  - 2,000 Actions minutes/month
  - 500 MB Packages storage
- **Pro** - $4/月
  - 3,000 Actions minutes/month
  - 2 GB Packages storage
  - Advanced tools and insights
- **Team** - $4/user/月
  - Team access controls
  - 3,000 Actions minutes/month
  - 2 GB Packages storage
- **Enterprise** - $21/user/月
  - SAML single sign-on
  - Advanced auditing
  - 50,000 Actions minutes/month

#### Emails（メールアドレス）
- メールアドレス追加
- Primary email 設定
- Email preferences

#### Security（セキュリティ）

**Two-factor authentication（2FA）:**
- 2段階認証設定
- TOTP app（Google Authenticator等）
- SMS
- Security keys（YubiKey等）
- Recovery codes

**Sessions（セッション）:**
- アクティブなセッション一覧
- デバイス、場所、最終アクティブ
- セッション無効化

**Security log（セキュリティログ）:**
- アカウントアクティビティ履歴
- ログイン、設定変更等

#### SSH and GPG keys（SSH・GPGキー）

**SSH keys:**
- 公開鍵登録
- 複数キー登録可能

**新規SSH鍵追加:**
1. **New SSH key**
2. Title入力（例: "MacBook Pro"）
3. Key貼り付け（`ssh-rsa ...`）
4. **Add SSH key**

**GPG keys:**
- コミット署名用GPG鍵
- Verified コミット

#### Organizations（組織）
- 所属組織一覧
- 組織作成

#### Repositories（リポジトリ設定）
- デフォルトリポジトリ設定
- デフォルトブランチ名（`main`）

#### Codespaces
- Codespace設定
- デフォルトエディター
- タイムアウト
- Dotfiles

#### Copilot（GitHub Copilot）
- Copilot有効化
- Suggestions設定

#### Applications（アプリケーション）

**Installed GitHub Apps:**
- インストール済みアプリ
- 権限確認
- アンインストール

**Authorized OAuth Apps:**
- OAuth認証済みアプリ
- 権限確認
- 認証解除

**Authorized GitHub Apps:**
- 認証済みGitHub Apps
- 権限確認

#### Scheduled reminders（スケジュールリマインダー）
- レビュー依頼リマインダー
- 曜日・時刻設定

#### Developer settings（開発者設定）

**Personal access tokens:**
- Fine-grained tokens（新）
- Tokens (classic)

**新規トークン作成（classic）:**
1. **Generate new token**
2. Note（用途）
3. Expiration（有効期限）
4. Select scopes（権限選択）:
   - repo（リポジトリ）
   - workflow（Actions）
   - write:packages（パッケージ）
   - delete:packages
   - admin:org（組織）
   - admin:public_key（公開鍵）
   - admin:repo_hook（Webhook）
   - admin:org_hook
   - gist
   - notifications
   - user（ユーザー）
   - delete_repo（リポジトリ削除）
5. **Generate token**
6. トークンをコピー（1回のみ表示）

**OAuth Apps:**
- 自分が作成したOAuth App
- Client ID/Secret

**GitHub Apps:**
- 自分が作成したGitHub App
- App ID/Webhook設定

---

## 12. 通知センター

ベルアイコン 🔔 をクリックしたときの画面。

### 12.1 通知一覧

**フィルタータブ:**
```
[Inbox] [Unread] [Saved] [Done]
```

- **Inbox** - 受信トレイ
- **Unread** - 未読
- **Saved** - 保存済み
- **Done** - 完了

**通知アイテム:**
- リポジトリ名
- Issue/PR タイトル
- 通知理由（@mention, review requested, assigned等）
- 時刻

### 12.2 通知の種類

**アイコン:**
- 💬 **Comment** - コメント
- 👁️ **Review** - レビュー
- ✅ **Approval** - 承認
- ⚠️ **Changes requested** - 変更要求
- 🔀 **Merged** - マージ
- 🔴 **Closed** - クローズ
- ✨ **Assigned** - アサイン
- 🔔 **Mentioned** - メンション

### 12.3 通知操作

**個別通知:**
- クリック - 該当ページへ移動
- **Mark as done** - 完了マーク（チェックアイコン）
- **Save** - 保存（ブックマークアイコン）
- **Unsubscribe** - 購読解除

**一括操作:**
- 複数選択（チェックボックス）
- **Mark as done**
- **Mark as read**
- **Mark as unread**

### 12.4 通知フィルター

**検索ボックス:**
```
is:unread reason:mention
```

**フィルター:**
- `is:unread` / `is:read`
- `reason:assign` - アサインされた
- `reason:author` - 自分が作成
- `reason:comment` - コメントされた
- `reason:mention` - メンションされた
- `reason:review-requested` - レビュー依頼
- `reason:state-change` - 状態変更
- `repo:owner/repo` - 特定リポジトリ

**例:**
```
is:unread reason:review-requested
→ 未読のレビュー依頼のみ
```

### 12.5 通知設定

**リポジトリ単位:**
- **Watch** - すべて通知
- **Participating and @mentions** - 参加中とメンションのみ
- **Ignore** - 通知しない
- **Custom** - カスタム設定

**Issue/PR単位:**
- **Subscribe** - このIssue/PRを購読
- **Unsubscribe** - 購読解除

**通知方法:**
- GitHub上の通知
- メール通知
- モバイル通知（GitHub Mobile）

---

## 📱 GitHub Mobile アプリ

### モバイルアプリの機能
- 通知確認・対応
- Issue/PR閲覧・コメント
- コードレビュー
- マージ承認
- プッシュ通知

**ダウンロード:**
- [iOS](https://apps.apple.com/app/github/id1477376905)
- [Android](https://play.google.com/store/apps/details?id=com.github.android)

---

## 🎯 まとめ

### よく使う機能の場所

| 機能 | 場所 |
|------|------|
| リポジトリ作成 | 右上 `+` → New repository |
| Issue作成 | リポジトリ → Issues → New issue |
| PR作成 | リポジトリ → Pull requests → New pull request |
| Actions設定 | リポジトリ → Actions → New workflow |
| 設定変更 | リポジトリ → Settings |
| 通知確認 | 右上 🔔 ベルアイコン |
| プロフィール | 右上アイコン → Your profile |
| スター一覧 | 右上アイコン → Your stars |

### 効率化のヒント

1. **ショートカットキーを活用**
   - `?` で一覧表示
   - `G` → `I` で Issues へ
   - `T` でファイル検索

2. **通知を整理**
   - カスタムフィルター活用
   - Done/Saved で管理

3. **Projectsで一元管理**
   - 複数リポジトリのIssue/PRを統合
   - カンバンボードで可視化

4. **Actionsで自動化**
   - テスト・ビルド・デプロイ
   - 定型作業の自動化

5. **テンプレート活用**
   - Issue/PRテンプレート
   - 記入漏れ防止

---

## 🔗 関連ドキュメント

- [Git基本コマンド集](./git-commands.md)
- [ショートカットキー集](./shortcuts.md)
- [実践ワークフロー](./workflow-examples.md)
- [GitHubの使い方](./github-usage.md)

---

**最終更新**: 2025-10-13
