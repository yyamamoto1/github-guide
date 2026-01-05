# Git/GitHub 完全ガイド

**git push が怖くなくなるまでを"意味"で理解するガイド**

> このガイドは [note記事](https://note.com/yamato255/n/n985342275bf8) をベースに、実践的な内容を追加した完全版です。

---

## はじめに

プログラミングを始めると、必ずと言っていいほど登場するのが **Git** と **GitHub**。
しかし初心者にとっては、

- リポジトリ？
- プッシュ？
- クローン？
- エラーが赤文字で出たけど何が起きてるの？

と、専門用語の壁にいきなりぶつかります。

特に最初の `git push`（アップロード）は、**最大の難関であり、同時に最も感動的な瞬間** です。

このガイドでは、**「コマンドの意味」と「なぜその順番なのか」** に焦点を当てて、GitHubの基本から応用までを解説します。

---

## 目次

- [コンセプト：意味で理解する](#コンセプト意味で理解する)
- [クイックスタート](#クイックスタート)
- [詳細ドキュメント](#詳細ドキュメント)
- [学習の進め方](#学習の進め方)
- [参考リソース](#参考リソース)

---

## コンセプト：意味で理解する

### ローカルとリモートの違い【最重要】

GitHubで迷う原因の9割は、「ローカル」と「リモート」の違いが曖昧なことです。

| 種類 | 場所 | 特徴 |
|------|------|------|
| **ローカルリポジトリ** | 自分のPC内 | まだ誰にも見えない。`git commit` までがここ |
| **リモートリポジトリ** | GitHub上 | 他人が見られる。`git push` で初めて反映 |

### よく使う3つの操作

| コマンド | 方向 | イメージ |
|----------|------|----------|
| `git push` | ローカル → GitHub | 机の上の成果物を金庫にしまう |
| `git pull` | GitHub → ローカル | 金庫の最新状態を机に持ってくる |
| `git clone` | GitHub → ローカル（初回） | 金庫を丸ごと自分の机にコピー |

### コマンドをRPGで覚えると一生忘れない

| コマンド | RPGで例えると |
|----------|---------------|
| `git init` | 冒険の記録帳を作る |
| `git add` | セーブしたいアイテムを選ぶ |
| `git commit` | セーブポイントで記録 |
| `git remote add` | セーブ先サーバーを登録 |
| `git push` | クラウドにセーブ |

---

## クイックスタート

### 1. GitHubアカウントの準備

1. [GitHub](https://github.com) でアカウント作成
2. **二要素認証（2FA）を設定**（パスワード＋スマホ認証）

> 初心者ほど必須。後から設定するより、最初に済ませた方が楽です。

### 2. Gitの初期設定

```bash
# ユーザー名の設定
git config --global user.name "Your Name"

# メールアドレスの設定
git config --global user.email "your.email@example.com"

# 設定確認
git config --list
```

### 3. 【完全新規】ゼロからGitHubにプッシュ

初めての人は、まずここだけやればOKです。

#### Step 1: GitHubで「箱（リポジトリ）」を作る

1. GitHub右上「＋」→ **New repository**
2. Repository name を入力
3. **READMEはチェックしない**（重要：空の箱の方がエラーが起きにくい）
4. **Create repository**

#### Step 2: PC側でコマンドを実行

```bash
# 1. Git管理を開始（冒険の記録帳を作る）
git init

# 2. 全ファイルを選択（荷造り）
git add .

# 3. セーブする（履歴を確定）
git commit -m "First commit"

# 4. ブランチ名を main に統一
git branch -M main

# 5. 宛先（GitHub）を登録
git remote add origin https://github.com/あなたのID/リポジトリ名.git

# 6. 初めての発送（感動ポイント）
git push -u origin main
```

**これでGitHubにコードが表示されたら成功です！**

### 4. 【既存】すでにあるリポジトリにプッシュ

```bash
# まず確認
git status
git remote -v

# 送信
git add .
git commit -m "変更内容"
git push -u origin main
```

### 5. 初心者が100%ハマるエラーと解決策

```
! [rejected] main -> main (fetch first)
```

**原因**: GitHub側にREADMEなどがあり、PC側と履歴がズレている

**解決策**:
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

---

## 詳細ドキュメント

### 基礎編
| ドキュメント | 説明 |
|-------------|------|
| [Git基本コマンド集](./docs/git-commands.md) | Windows/Mac対応の基本コマンド |
| [ターミナルからGitHubプッシュ完全ガイド](./docs/push-to-github-guide.md) | 7つのシナリオで詳解 |
| [ターミナル/コマンドプロンプト基本操作](./docs/terminal-basics.md) | CLI操作の基本 |
| [ショートカットキー集](./docs/shortcuts.md) | Windows/Mac/VSCode対応 |

### GitHub編
| ドキュメント | 説明 |
|-------------|------|
| [GitHubメニュー完全ガイド](./docs/github-ui-guide.md) | 全メニュー・UIを解説 |
| [GitHubの使い方](./docs/github-usage.md) | アカウント作成から初期設定まで |
| [リポジトリ管理](./docs/repository-management.md) | リポジトリの作成・設定 |
| [Issues・Projects活用法](./docs/issues-projects.md) | プロジェクト管理 |
| [Pull Request・Code Review](./docs/pull-request-guide.md) | チーム開発の要 |

### AI開発ツール連携
| ドキュメント | 説明 |
|-------------|------|
| [AI開発ツール連携ガイド](./docs/ai-tools-integration.md) | Claude Code, Cursor, GitHub CLI統合 |

### 実践編
| ドキュメント | 説明 |
|-------------|------|
| [実践ワークフロー](./docs/workflow-examples.md) | 実務で使えるフロー |
| [ブランチ戦略](./docs/branching-strategies.md) | Git Flow, GitHub Flow |
| [GitHub Actions入門](./docs/github-actions.md) | CI/CD構築 |
| [トラブルシューティング](./docs/troubleshooting.md) | よくある問題と解決法 |
| [ハンズオン演習](./docs/hands-on-exercises.md) | 実践演習 |

### チートシート
| ドキュメント | 説明 |
|-------------|------|
| [Gitコマンド早見表](./cheatsheets/git-commands-cheatsheet.md) | コマンド一覧 |
| [GitHubショートカット早見表](./cheatsheets/github-shortcuts-cheatsheet.md) | ショートカット一覧 |

---

## よく使うコマンドTOP 10

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

## 学習の進め方

### 初心者向け
1. このREADMEの[クイックスタート](#クイックスタート)を実践
2. [Git基本コマンド集](./docs/git-commands.md)で基本を学ぶ
3. 空フォルダで何度も「push成功体験」を積む

### 中級者向け
1. [ブランチ戦略](./docs/branching-strategies.md)を学ぶ
2. [Pull Request・Code Review](./docs/pull-request-guide.md)で協業方法を学ぶ
3. [実践ワークフロー](./docs/workflow-examples.md)で実務フローを体験

### 上級者向け
1. [GitHub Actions](./docs/github-actions.md)でCI/CD構築
2. [AI開発ツール連携ガイド](./docs/ai-tools-integration.md)で効率化
3. オープンソースプロジェクトに貢献

---

## まとめ：これだけ覚えればOK

GitHubは **ローカル（PC）とリモート（GitHub）の同期**。

基本はこの3つだけ：

```bash
git add .
git commit -m "メモ"
git push
```

**最短上達ルート**: 空フォルダで何度も「push成功体験」を積むこと。

---

## 参考リソース

### 公式ドキュメント
- [Git公式ドキュメント](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Skills](https://skills.github.com/)

### 関連記事
- [GitHub超入門｜git pushが怖くなくなるまでを"意味"で理解するガイド](https://note.com/yamato255/n/n985342275bf8)

---

## おわりに

GitHubは「コード置き場」ではありません。
**開発者の思考と成長のログ** です。

最初の `git push` が通った瞬間、ちょっと嬉しくなりませんでしたか？

その感覚があれば十分です。
次はブランチとマージ。
Gitが「ただのツール」から「楽しい道具」に変わっていきます。

---

## コントリビューション

このガイドの改善提案・追加コンテンツがあれば、IssueまたはPull Requestをお願いします！

---

## ライセンス

MIT License

---

**最終更新**: 2025-01-05
**バージョン**: 3.0.0

**言語**: [日本語](./README.md) | [English](./README_EN.md)
