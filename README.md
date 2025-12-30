# 🚀 Git/GitHub完全ガイド

**Windows/Mac対応の実践的チュートリアル**

Git/GitHubの基本から応用まで、実務で使える知識を網羅した完全ガイドです。

## 📚 目次

### 基礎編
- [Git基本コマンド集](./docs/git-commands.md) - Windows/Mac対応
- [ターミナルからGitHubプッシュ完全ガイド](./docs/push-to-github-guide.md) ⭐ **実践重視**
- [ターミナル/コマンドプロンプト基本操作](./docs/terminal-basics.md)
- [ショートカットキー集](./docs/shortcuts.md) - Windows/Mac/VSCode対応

### GitHub編
- [GitHubメニュー完全ガイド](./docs/github-ui-guide.md)
- [GitHubの使い方](./docs/github-usage.md)
- [リポジトリ管理](./docs/repository-management.md)
- [Issues・Projects活用法](./docs/issues-projects.md)
- [Pull Request・Code Review](./docs/pull-request-guide.md)

### AI開発ツール連携 🤖 **NEW**
- [AI開発ツール連携ガイド](./docs/ai-tools-integration.md) - Claude Code, Cursor, GitHub CLI統合
  - Claude Code: `/init` + ultrathink によるプロジェクト分析
  - Cursor: AIネイティブエディタでのGit操作
  - GitHub CLI (gh): コマンドラインからGitHub操作
  - GitHub Copilot: AIペアプログラミング

### 実践編
- [実践ワークフロー](./docs/workflow-examples.md)
- [ブランチ戦略](./docs/branching-strategies.md)
- [GitHub Actions入門](./docs/github-actions.md)
- [トラブルシューティング](./docs/troubleshooting.md)
- [ハンズオン演習](./docs/hands-on-exercises.md) ⭐ **実践演習**

### チートシート
- [Gitコマンド早見表](./cheatsheets/git-commands-cheatsheet.md)
- [GitHubショートカット早見表](./cheatsheets/github-shortcuts-cheatsheet.md)

---

## 🎯 こんな方におすすめ

- Gitを初めて使う方
- GitHubの使い方を学びたい方
- チーム開発に参加する方
- WindowsとMac両方の環境を使う方
- ショートカットキーで効率化したい方
- **AI開発ツール（Claude Code, Cursor, GitHub Copilot）を活用したい方** 🤖 NEW

---

## 📖 各ドキュメントの概要

### 1. Git基本コマンド集
Windows/Mac両対応のGit基本コマンドを網羅。
- 初期設定
- リポジトリ操作
- ブランチ操作
- コミット操作
- リモート操作
- 各コマンドのWindows/Mac差分を明記

### 2. ターミナルからGitHubプッシュ完全ガイド ⭐**NEW**
ローカルファイルをGitHubにプッシュする全プロセスを7つのシナリオで詳解。
- 新規プロジェクトのアップロード手順
- ファイル更新・プッシュの流れ
- ブランチを使った開発フロー
- チーム開発での協力方法
- タグとリリース管理
- 実用的な操作テクニック
- トラブルシューティング・解決方法

### 3. GitHubメニュー完全ガイド
GitHubの全メニュー・UIを画面キャプチャ付きで解説。
- ナビゲーションバー
- リポジトリメニュー
- Settings各項目
- Actions/Issues/Projects/Wiki
- 各機能の使い方を詳しく説明

### 4. ショートカットキー集
作業効率が劇的に向上するショートカット集。
- GitHubウェブサイト上のショートカット
- VSCode Git関連ショートカット
- ターミナル/コマンドプロンプトのショートカット
- Windows/Mac両対応

### 5. 実践ワークフロー
実務で使える具体的なワークフロー例。
- 個人開発フロー
- チーム開発フロー
- オープンソースプロジェクト貢献フロー
- Issue → Branch → PR → Merge の完全な流れ

### 6. AI開発ツール連携ガイド 🤖 NEW
最新のAI開発ツールとGit/GitHub連携を完全解説。
- **Claude Code**: `/init` + ultrathinkでプロジェクト全体を深く分析
- **Cursor**: AIネイティブエディタでのGit操作・コミットメッセージ自動生成
- **GitHub CLI (gh)**: コマンドラインからIssue, PR, Actions操作
- **GitHub Copilot**: AIペアプログラミングとGit連携
- 統合ワークフロー・CI/CD設定例

---

## 🚀 クイックスタート

### Gitのインストール確認

**Windows:**
```cmd
git --version
```

**Mac:**
```bash
git --version
```

### 初期設定

```bash
# ユーザー名の設定
git config --global user.name "Your Name"

# メールアドレスの設定
git config --global user.email "your.email@example.com"

# 設定確認
git config --list
```

### 最初のリポジトリを作成

```bash
# ディレクトリ作成
mkdir my-first-repo
cd my-first-repo

# Gitリポジトリとして初期化
git init

# READMEファイル作成
echo "# My First Repository" > README.md

# ステージング
git add README.md

# コミット
git commit -m "Initial commit"
```

---

## 📝 よく使うコマンドTOP 10

| コマンド | 説明 |
|---------|------|
| `git status` | 現在の状態を確認 |
| `git add .` | 全ての変更をステージング |
| `git commit -m "message"` | 変更をコミット |
| `git push` | リモートにプッシュ |
| `git pull` | リモートから最新を取得 |
| `git branch` | ブランチ一覧表示 |
| `git checkout -b <branch>` | 新しいブランチを作成して切り替え |
| `git merge <branch>` | ブランチをマージ |
| `git log` | コミット履歴を表示 |
| `git diff` | 変更差分を表示 |

---

## 🔑 よく使うショートカット

### GitHub ウェブサイト

| Windows/Linux | Mac | 機能 |
|--------------|-----|------|
| `Ctrl + K` | `Cmd + K` | コマンドパレット |
| `S` | `S` | リポジトリ検索 |
| `G` → `I` | `G` → `I` | Issuesページへ |
| `G` → `P` | `G` → `P` | Pull requestsページへ |
| `T` | `T` | ファイル検索 |
| `L` | `L` | ファイル内の行へジャンプ |

### VSCode Git操作

| Windows/Linux | Mac | 機能 |
|--------------|-----|------|
| `Ctrl + Shift + G` | `Cmd + Shift + G` | ソース管理を開く |
| `Ctrl + Enter` | `Cmd + Enter` | コミット |
| `Alt + Enter` | `Option + Enter` | コミット & プッシュ |

詳細は[ショートカットキー集](./docs/shortcuts.md)を参照。

---

## 🎓 学習の進め方

### 初心者向け（1-2週間）
1. [Git基本コマンド集](./docs/git-commands.md)で基本を学ぶ
2. [ターミナル基本操作](./docs/terminal-basics.md)でCLI操作に慣れる
3. [GitHubの使い方](./docs/github-usage.md)でGitHubアカウント作成・初期設定
4. 実際にリポジトリを作ってコミット・プッシュを試す

### 中級者向け（2-4週間）
1. [ブランチ戦略](./docs/branching-strategies.md)を学ぶ
2. [Pull Request・Code Review](./docs/pull-request-guide.md)で協業方法を学ぶ
3. [実践ワークフロー](./docs/workflow-examples.md)で実務フローを体験
4. [ショートカットキー](./docs/shortcuts.md)で効率化

### 上級者向け（1ヶ月以上）
1. [GitHub Actions](./docs/github-actions.md)でCI/CD構築
2. [トラブルシューティング](./docs/troubleshooting.md)で問題解決力を養う
3. オープンソースプロジェクトに貢献
4. 自分のチームに合わせたワークフローを設計

---

## 🛠️ トラブルシューティング

よくある問題と解決方法は[トラブルシューティング](./docs/troubleshooting.md)を参照してください。

**即座に解決したい場合:**
- [コミットを間違えた時](#)
- [プッシュを取り消したい時](#)
- [マージコンフリクトが発生した時](#)
- [間違ってファイルを削除した時](#)

---

## 📚 参考リソース

### 公式ドキュメント
- [Git公式ドキュメント](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Skills](https://skills.github.com/)

### おすすめ書籍・サイト
- Pro Git（無料・日本語版あり）
- Learn Git Branching（インタラクティブ学習）
- GitHub Learning Lab

---

## 🤝 コントリビューション

このガイドの改善提案・追加コンテンツがあれば、Issueまたはプルリクエストをお願いします！

---

## 📄 ライセンス

MIT License

---

## 🌟 最後に

Gitを使いこなせるようになると、開発効率が劇的に向上します。
このガイドがあなたの学習の助けになれば幸いです。

何か質問があれば、Issuesでお気軽にお尋ねください！

---

**最終更新**: 2025-12-30
**バージョン**: 2.0.0 - AI開発ツール連携対応
