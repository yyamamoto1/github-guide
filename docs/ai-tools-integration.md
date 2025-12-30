# AI開発ツール連携ガイド

**📋 Assigned to: AI Engineer + DevOps Specialist**
**🚀 2025年最新版 - Claude Code, Cursor, GitHub CLI完全統合ガイド**

## 📋 目次
- [概要](#概要)
- [Claude Code連携](#claude-code連携)
- [Cursor連携](#cursor連携)
- [GitHub CLI (gh)](#github-cli-gh)
- [GitHub Copilot](#github-copilot)
- [統合ワークフロー](#統合ワークフロー)
- [ベストプラクティス](#ベストプラクティス)
- [トラブルシューティング](#トラブルシューティング)

---

## 概要

2025年の開発環境では、AI支援ツールとGitHub連携が不可欠です。本ガイドでは、主要なAI開発ツールとGitHub/Gitの効率的な連携方法を解説します。

### 対象ツール

| ツール | 種類 | 主な用途 |
|--------|------|----------|
| Claude Code | AI CLI | コード生成、レビュー、Git操作 |
| Cursor | AI IDE | インテリジェントコーディング |
| GitHub CLI (gh) | CLI | GitHub操作自動化 |
| GitHub Copilot | AI補完 | コード補完、提案 |

---

## Claude Code連携

### Claude Codeとは

Claude Code（Anthropic社）は、ターミナルから直接AIアシスタントと対話しながらコードを書くことができるCLIツールです。Git/GitHub操作を自然言語で実行できます。

### インストール

```bash
# npmでグローバルインストール
npm install -g @anthropic-ai/claude-code

# インストール確認
claude --version
```

### 初期設定

```bash
# APIキーの設定
claude config set api_key YOUR_ANTHROPIC_API_KEY

# または環境変数で設定
export ANTHROPIC_API_KEY="YOUR_API_KEY"

# 設定確認
claude config list
```

### Git/GitHub連携コマンド

#### リポジトリ初期化

```bash
# 自然言語でプロジェクト初期化
claude "新しいReactプロジェクトを作成して、GitHubにプッシュして"

# /init コマンドで初期化
claude /init

# ultrathinkモードでプロジェクト解析
claude /init --ultrathink
```

#### コミット・プッシュ操作

```bash
# 変更をコミット
claude "変更内容を適切なコミットメッセージでコミットして"

# 変更の確認とコミット
claude "現在の変更を確認して、適切なコミットメッセージを提案して"

# プッシュ
claude "mainブランチにプッシュして"
```

#### ブランチ操作

```bash
# 新しいブランチを作成
claude "feature/user-authenticationブランチを作成して切り替えて"

# ブランチをマージ
claude "feature/user-authenticationをmainにマージして"

# ブランチ一覧を確認
claude "現在のブランチ状態を教えて"
```

#### Pull Request操作

```bash
# PRを作成
claude "この変更でPull Requestを作成して"

# PRの内容を確認
claude "オープン中のPRを一覧表示して"

# PRにコメント
claude "PR #123にレビューコメントを追加して"
```

### /init + ultrathink モード

プロジェクト全体を深く分析し、最適な設定を提案します。

```bash
# プロジェクトの深い分析
claude /init --ultrathink

# 実行される処理:
# 1. ファイル構造の完全スキャン
# 2. 依存関係の分析
# 3. コードパターンの特定
# 4. 最適な設定提案
# 5. .claudeignore, CLAUDE.md の自動生成
```

**生成されるファイル:**

```markdown
# CLAUDE.md
## プロジェクト概要
このプロジェクトは...

## 技術スタック
- Frontend: React 18
- Backend: Node.js + Express
- Database: PostgreSQL

## コーディング規約
- TypeScript必須
- ESLint + Prettier使用
- Conventional Commits形式

## よく使うコマンド
- `npm run dev` - 開発サーバー起動
- `npm test` - テスト実行
- `npm run build` - 本番ビルド
```

### Claude Codeの設定ファイル

**.claudeignore** (除外ファイル設定):
```
node_modules/
.git/
dist/
build/
*.log
.env
.env.local
```

**claude.config.json**:
```json
{
  "model": "claude-sonnet-4-20250514",
  "context_window": 200000,
  "git_integration": true,
  "auto_commit_message": true,
  "language": "ja",
  "editor": "vscode"
}
```

---

## Cursor連携

### Cursorとは

CursorはAIネイティブなコードエディタで、VS Codeベースでありながら、AIによるコード生成・編集機能が深く統合されています。

### インストール

```bash
# macOS (Homebrew)
brew install --cask cursor

# Windows (winget)
winget install Cursor.Cursor

# または公式サイトからダウンロード
# https://cursor.sh
```

### Git連携設定

#### 初期設定

```json
// settings.json
{
  "git.enableSmartCommit": true,
  "git.autofetch": true,
  "git.confirmSync": false,
  "cursor.git.enabled": true,
  "cursor.git.autoStage": true
}
```

#### AI支援Git操作

**コマンドパレット (Cmd/Ctrl + Shift + P):**
```
> Cursor: Generate Commit Message
> Cursor: Explain Diff
> Cursor: Review Changes
> Cursor: Create Pull Request Description
```

### Cursorのキーボードショートカット

| Windows/Linux | Mac | 機能 |
|--------------|-----|------|
| `Ctrl + K` | `Cmd + K` | AIチャット開始 |
| `Ctrl + L` | `Cmd + L` | AIサイドパネル開く |
| `Ctrl + Shift + K` | `Cmd + Shift + K` | コード生成 |
| `Ctrl + Shift + L` | `Cmd + Shift + L` | 選択コードを説明 |
| `Ctrl + Shift + G` | `Cmd + Shift + G` | ソース管理 |

### AI支援コミット

```
# Cursorでのコミットフロー
1. ソース管理パネルを開く (Cmd/Ctrl + Shift + G)
2. 変更ファイルをステージング
3. "AI Generate Message" ボタンクリック
4. 生成されたコミットメッセージを確認
5. コミット実行
```

### Composer機能

Cursorの**Composer**機能を使って複数ファイルを一括編集：

```
# Composer使用例
"src/components/配下の全コンポーネントにエラーハンドリングを追加して"
"テスト関連ファイルをすべて更新してJest設定を最新化して"
"package.jsonの依存関係を最新バージョンに更新して"
```

### .cursorules設定

プロジェクトルートに配置してAI動作をカスタマイズ：

```
# .cursorules

## コーディングスタイル
- TypeScriptを使用
- 関数コンポーネント優先
- カスタムフックでロジック分離

## Git規約
- Conventional Commits形式を使用
- feat: 新機能
- fix: バグ修正
- docs: ドキュメント
- refactor: リファクタリング
- test: テスト

## ファイル構造
src/
  components/   # Reactコンポーネント
  hooks/        # カスタムフック
  utils/        # ユーティリティ関数
  types/        # 型定義

## 禁止事項
- any型の使用
- console.logの残存
- 未使用のimport
```

---

## GitHub CLI (gh)

### インストール

```bash
# macOS
brew install gh

# Windows
winget install --id GitHub.cli

# Linux (Debian/Ubuntu)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

### 認証設定

```bash
# ブラウザ認証
gh auth login

# トークン認証
gh auth login --with-token < token.txt

# 認証状態確認
gh auth status

# 複数アカウント管理
gh auth switch
```

### リポジトリ操作

```bash
# リポジトリ作成
gh repo create my-project --public --description "My new project"

# リポジトリクローン
gh repo clone owner/repository

# リポジトリフォーク
gh repo fork owner/repository --clone

# リポジトリ情報表示
gh repo view

# リポジトリ一覧
gh repo list --limit 20
```

### Issue操作

```bash
# Issue作成
gh issue create --title "バグ報告" --body "詳細説明"

# テンプレート使用
gh issue create --template bug_report.md

# Issue一覧
gh issue list
gh issue list --state closed
gh issue list --label "bug" --assignee "@me"

# Issue詳細表示
gh issue view 123

# Issue編集
gh issue edit 123 --add-label "priority:high"

# Issueクローズ
gh issue close 123 --comment "修正完了"
```

### Pull Request操作

```bash
# PR作成
gh pr create --title "新機能追加" --body "説明"

# Draft PR作成
gh pr create --draft --title "WIP: 機能開発中"

# PR一覧
gh pr list
gh pr list --state merged --author "@me"

# PRチェックアウト
gh pr checkout 456

# PRマージ
gh pr merge 456 --squash --delete-branch

# PRレビュー
gh pr review 456 --approve --body "LGTM!"
gh pr review 456 --request-changes --body "修正が必要です"

# PR差分確認
gh pr diff 456
```

### GitHub Actions操作

```bash
# ワークフロー一覧
gh workflow list

# ワークフロー実行
gh workflow run build.yml

# 実行履歴
gh run list

# 実行詳細確認
gh run view 123456

# 実行ログ表示
gh run view 123456 --log

# 失敗した実行を再実行
gh run rerun 123456
```

### エイリアス設定

```bash
# エイリアス作成
gh alias set prc 'pr create --fill'
gh alias set prm 'pr merge --squash --delete-branch'
gh alias set issues 'issue list --state open --assignee @me'

# エイリアス一覧
gh alias list

# 使用例
gh prc      # PRを素早く作成
gh prm 123  # PR 123をSquashマージ
gh issues   # 自分に割り当てられたIssue
```

### 便利なワンライナー

```bash
# 今週作成したPRを一覧
gh pr list --author "@me" --search "created:>$(date -d '1 week ago' +%Y-%m-%d)"

# マージ待ちのPRを確認
gh pr list --state open --draft=false --review required

# 全リポジトリのIssue統計
gh api graphql -f query='
query {
  viewer {
    issues(first: 100, states: OPEN) {
      totalCount
    }
    pullRequests(first: 100, states: OPEN) {
      totalCount
    }
  }
}'
```

---

## GitHub Copilot

### 概要

GitHub CopilotはAIペアプログラマーとして、リアルタイムでコード提案を行います。

### 設定

**VS Code設定:**
```json
{
  "github.copilot.enable": {
    "*": true,
    "markdown": true,
    "plaintext": false
  },
  "github.copilot.advanced": {
    "length": 500,
    "temperature": 0.3
  }
}
```

**Cursor設定:**
```json
{
  "cursor.copilot.enabled": true,
  "cursor.copilot.inlineSuggest": true
}
```

### Git関連の活用

```javascript
// コメントでコミットメッセージを生成
// Generate a commit message for adding user authentication feature
// feat: implement user authentication with JWT tokens

// PRの説明を生成
// Generate PR description for this change
/*
## Summary
Added user authentication system using JWT.

## Changes
- Implemented login/logout endpoints
- Added middleware for token validation
- Created user session management

## Testing
- Added unit tests for auth service
- Manual testing completed
*/
```

---

## 統合ワークフロー

### 開発フロー例: Claude Code + GitHub CLI

```bash
# 1. プロジェクト初期化
claude /init --ultrathink

# 2. ブランチ作成
gh issue create --title "新機能実装" --body "詳細"
# → Issue #42 が作成される
git checkout -b feature/issue-42

# 3. Claude Codeで開発
claude "Issue #42の要件に基づいてコードを実装して"

# 4. テスト実行
claude "テストを実行して結果を確認して"

# 5. コミット
claude "適切なコミットメッセージでコミットして"

# 6. PR作成
gh pr create --title "feat: Issue #42 実装" --body "Closes #42"

# 7. レビュー依頼
gh pr edit --add-reviewer teammate

# 8. マージ
gh pr merge --squash --delete-branch
```

### Cursor + GitHub CLIワークフロー

```bash
# 1. Cursorでプロジェクトを開く
cursor .

# 2. ターミナルでブランチ作成
git checkout -b feature/new-component

# 3. Cursorで開発（AI支援）
#    - Cmd+K でコード生成
#    - Composer で複数ファイル編集

# 4. ソース管理でコミット
#    - AI生成コミットメッセージ使用

# 5. ターミナルでPR作成
gh pr create --fill

# 6. レビュー・マージ
gh pr merge --squash
```

### CI/CD統合

**.github/workflows/ai-assisted-review.yml:**
```yaml
name: AI-Assisted Code Review

on:
  pull_request:
    types: [opened, synchronize]

jobs:
  ai-review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: AI Code Analysis
        run: |
          # Claude APIでコードレビュー
          curl -X POST https://api.anthropic.com/v1/messages \
            -H "x-api-key: ${{ secrets.ANTHROPIC_API_KEY }}" \
            -H "anthropic-version: 2023-06-01" \
            -d '{
              "model": "claude-sonnet-4-20250514",
              "messages": [{
                "role": "user",
                "content": "Review this PR diff: ${{ github.event.pull_request.diff_url }}"
              }]
            }'

      - name: Security Scan
        uses: github/codeql-action/analyze@v2

      - name: Post Review Comment
        uses: actions/github-script@v6
        with:
          script: |
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: 'AI Review completed. Check the logs for details.'
            })
```

---

## ベストプラクティス

### セキュリティ

1. **APIキーの管理**
   ```bash
   # 環境変数で管理（.envは.gitignoreに追加）
   export ANTHROPIC_API_KEY="sk-..."
   export GITHUB_TOKEN="ghp_..."

   # キーをハードコードしない
   # 誤ってコミットした場合は即座に無効化
   ```

2. **機密情報の除外**
   ```
   # .gitignore
   .env
   .env.local
   *.key
   *.pem
   secrets/
   ```

3. **コードレビュー**
   - AI生成コードは必ず人間がレビュー
   - セキュリティ関連は特に慎重に確認

### 効率化

1. **エイリアスの活用**
   ```bash
   # ~/.bashrc or ~/.zshrc
   alias cc="claude"
   alias gpr="gh pr create --fill"
   alias gpm="gh pr merge --squash --delete-branch"
   ```

2. **テンプレートの活用**
   ```markdown
   <!-- .github/PULL_REQUEST_TEMPLATE.md -->
   ## 変更内容
   <!-- Claude Codeで生成: claude "この変更の説明を生成して" -->

   ## テスト
   - [ ] ユニットテスト通過
   - [ ] 統合テスト通過

   ## 関連Issue
   Closes #
   ```

3. **自動化スクリプト**
   ```bash
   #!/bin/bash
   # daily-dev.sh

   # リポジトリを最新に
   git fetch --all --prune
   git pull --rebase

   # 古いブランチを削除
   git branch --merged | grep -v main | xargs -n 1 git branch -d

   # Dependabot PRを確認
   gh pr list --author "dependabot[bot]"
   ```

---

## トラブルシューティング

### Claude Code

| 問題 | 解決方法 |
|------|----------|
| API接続エラー | `claude config check`で設定確認 |
| コンテキスト超過 | `/clear`でコンテキストリセット |
| Git操作失敗 | Gitの認証状態を確認 |

```bash
# デバッグモード
claude --debug

# 設定リセット
claude config reset

# ログ確認
cat ~/.claude/logs/latest.log
```

### Cursor

| 問題 | 解決方法 |
|------|----------|
| AI応答なし | 設定でAPIキー確認 |
| Git連携エラー | Git認証情報を再設定 |
| パフォーマンス低下 | キャッシュクリア、再起動 |

```bash
# Cursor設定リセット
rm -rf ~/.cursor/cache

# ログ確認
# Help → Toggle Developer Tools → Console
```

### GitHub CLI

| 問題 | 解決方法 |
|------|----------|
| 認証エラー | `gh auth refresh` |
| API制限 | レート制限確認、待機 |
| プロキシ問題 | 環境変数設定 |

```bash
# 認証状態確認
gh auth status

# 詳細ログ
GH_DEBUG=1 gh pr list

# プロキシ設定
export HTTPS_PROXY=http://proxy:8080
```

---

## 関連ドキュメント

- [Git基本コマンド集](./git-commands.md)
- [実践ワークフロー](./workflow-examples.md)
- [ショートカットキー集](./shortcuts.md)
- [GitHubメニュー完全ガイド](./github-ui-guide.md)
- [ハンズオン演習](./hands-on-exercises.md)

---

**🤖 AI Engineer + DevOps Specialist による最終更新**: 2025-12-30
**🔧 次回更新予定**: 新AIツールリリース時
