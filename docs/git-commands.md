# Git基本コマンド集

**Windows/Mac対応 - 実務で使える完全版**

## 📋 目次
- [初期設定](#初期設定)
- [リポジトリ操作](#リポジトリ操作)
- [ファイル操作](#ファイル操作)
- [コミット操作](#コミット操作)
- [ブランチ操作](#ブランチ操作)
- [リモート操作](#リモート操作)
- [履歴・差分確認](#履歴差分確認)
- [タグ操作](#タグ操作)
- [取り消し・修正](#取り消し修正)

---

## 初期設定

### Gitのインストール確認

**Windows (コマンドプロンプト/PowerShell):**
```cmd
git --version
```

**Mac (ターミナル):**
```bash
git --version
```

### ユーザー情報の設定

```bash
# グローバル設定（全リポジトリ共通）
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# ローカル設定（特定のリポジトリのみ）
git config --local user.name "Your Name"
git config --local user.email "work.email@company.com"
```

### デフォルトブランチ名の設定

```bash
# デフォルトブランチをmainに設定
git config --global init.defaultBranch main
```

### エディタの設定

**Windows:**
```bash
# VSCode
git config --global core.editor "code --wait"

# Notepad++
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
```

**Mac:**
```bash
# VSCode
git config --global core.editor "code --wait"

# Vim
git config --global core.editor "vim"

# Nano
git config --global core.editor "nano"
```

### 改行コードの設定

**Windows:**
```bash
# Windows環境（CRLF → LF に自動変換）
git config --global core.autocrlf true
```

**Mac:**
```bash
# Mac/Linux環境（LFのまま）
git config --global core.autocrlf input
```

### 設定の確認

```bash
# 全設定を表示
git config --list

# 特定の設定を確認
git config user.name
git config user.email

# 設定ファイルの場所を確認
# グローバル設定
git config --global --list --show-origin

# ローカル設定
git config --local --list --show-origin
```

---

## リポジトリ操作

### 新規リポジトリの作成

```bash
# 現在のディレクトリをGitリポジトリに初期化
git init

# ディレクトリを作成して初期化
git init my-project
cd my-project
```

### 既存リポジトリのクローン

```bash
# HTTPS でクローン
git clone https://github.com/username/repository.git

# SSH でクローン
git clone git@github.com:username/repository.git

# 特定のブランチをクローン
git clone -b develop https://github.com/username/repository.git

# 別名でクローン
git clone https://github.com/username/repository.git my-repo
```

### リポジトリの状態確認

```bash
# 現在の状態を確認
git status

# 簡潔な表示
git status -s

# ブランチの状態も含めて表示
git status -sb
```

---

## ファイル操作

### ファイルの追加（ステージング）

```bash
# 特定のファイルを追加
git add filename.txt

# 複数のファイルを追加
git add file1.txt file2.txt file3.txt

# 全ての変更ファイルを追加
git add .

# 全ての変更ファイルを追加（削除も含む）
git add -A

# 特定の拡張子のファイルを追加
git add *.js

# ディレクトリごと追加
git add src/

# 対話的に追加（部分的にステージング可能）
git add -p
```

### ファイルの削除

```bash
# ファイルを削除してステージング
git rm filename.txt

# ディレクトリごと削除
git rm -r directory/

# Gitの管理から外すが、ファイルは残す
git rm --cached filename.txt

# 強制削除（変更があっても削除）
git rm -f filename.txt
```

### ファイル名の変更

```bash
# ファイル名を変更
git mv old-filename.txt new-filename.txt

# 通常のmvコマンドを使った場合
# Windows (PowerShell):
Rename-Item old-filename.txt new-filename.txt
git add new-filename.txt
git rm old-filename.txt

# Mac:
mv old-filename.txt new-filename.txt
git add new-filename.txt
git rm old-filename.txt
```

---

## コミット操作

### 基本的なコミット

```bash
# ステージングした変更をコミット
git commit -m "commit message"

# 複数行のコミットメッセージ
git commit -m "Title" -m "Description line 1" -m "Description line 2"

# エディタでコミットメッセージを入力
git commit

# ステージングとコミットを同時に実行（追跡済みファイルのみ）
git commit -am "commit message"

# 直前のコミットを修正（コミットメッセージも変更）
git commit --amend -m "new commit message"

# 直前のコミットに変更を追加（メッセージは変更しない）
git add forgotten-file.txt
git commit --amend --no-edit
```

### コミット時のテンプレート

```bash
# コミットメッセージテンプレートを設定
git config --global commit.template ~/.gitmessage.txt
```

**テンプレート例 (~/.gitmessage.txt):**
```
# [type]: [subject]
#
# [body]
#
# [footer]
#
# type: feat, fix, docs, style, refactor, test, chore
# subject: 50文字以内の要約
# body: 詳細説明（必要な場合）
# footer: Issue番号など
```

---

## ブランチ操作

### ブランチの確認

```bash
# ローカルブランチ一覧
git branch

# リモートブランチも含めて一覧表示
git branch -a

# 最新のコミット情報も表示
git branch -v

# マージ済みのブランチを表示
git branch --merged

# 未マージのブランチを表示
git branch --no-merged
```

### ブランチの作成

```bash
# 新しいブランチを作成
git branch feature-branch

# ブランチを作成して切り替え
git checkout -b feature-branch

# 最新のGit（2.23以降）
git switch -c feature-branch

# 特定のコミットからブランチを作成
git branch feature-branch abc1234

# リモートブランチを元に作成
git checkout -b local-branch origin/remote-branch
```

### ブランチの切り替え

```bash
# ブランチを切り替え
git checkout branch-name

# 最新のGit（2.23以降）
git switch branch-name

# 直前のブランチに戻る
git checkout -
git switch -

# 強制的に切り替え（変更を破棄）
git checkout -f branch-name
```

### ブランチの削除

```bash
# ブランチを削除（マージ済みのみ）
git branch -d feature-branch

# ブランチを強制削除（マージされていなくても）
git branch -D feature-branch

# リモートブランチを削除
git push origin --delete feature-branch
```

### ブランチのマージ

```bash
# 現在のブランチに指定ブランチをマージ
git merge feature-branch

# マージコミットを作成しない（Fast-forward）
git merge --ff-only feature-branch

# 必ずマージコミットを作成
git merge --no-ff feature-branch

# マージを中止
git merge --abort

# マージのプレビュー（実際にはマージしない）
git merge --no-commit --no-ff feature-branch
```

### ブランチのリベース

```bash
# 現在のブランチをmainの最新にリベース
git rebase main

# リベースを続行
git rebase --continue

# リベースを中止
git rebase --abort

# リベースをスキップ
git rebase --skip

# インタラクティブリベース（コミットを整理）
git rebase -i HEAD~3
```

---

## リモート操作

### リモートリポジトリの確認

```bash
# リモートリポジトリ一覧
git remote

# 詳細情報も表示
git remote -v

# 特定のリモートの詳細情報
git remote show origin
```

### リモートリポジトリの追加

```bash
# リモートリポジトリを追加
git remote add origin https://github.com/username/repository.git

# 複数のリモートを追加
git remote add upstream https://github.com/original/repository.git
```

### リモートリポジトリの削除・変更

```bash
# リモートリポジトリを削除
git remote remove origin

# リモートリポジトリ名を変更
git remote rename origin new-origin

# リモートURLを変更
git remote set-url origin https://github.com/username/new-repository.git
```

### プッシュ（Push）

```bash
# 現在のブランチをリモートにプッシュ
git push

# 初回プッシュ時（upstream設定）
git push -u origin main

# 特定のブランチをプッシュ
git push origin feature-branch

# 全てのブランチをプッシュ
git push --all

# タグもプッシュ
git push --tags

# 強制プッシュ（危険！）
git push -f

# 安全な強制プッシュ（リモートが変更されていたら失敗）
git push --force-with-lease
```

### プル（Pull）

```bash
# リモートの変更を取得してマージ
git pull

# 特定のブランチをプル
git pull origin main

# リベースしてプル
git pull --rebase

# プルのプレビュー（実際には取得しない）
git pull --dry-run
```

### フェッチ（Fetch）

```bash
# リモートの変更を取得（マージはしない）
git fetch

# 全てのリモートから取得
git fetch --all

# 特定のリモートから取得
git fetch origin

# リモートで削除されたブランチをローカルでも削除
git fetch --prune
```

---

## 履歴・差分確認

### コミット履歴の確認

```bash
# コミット履歴を表示
git log

# 1行で表示
git log --oneline

# グラフ表示
git log --graph --oneline --all

# 直近のn件を表示
git log -5

# 特定のファイルの履歴
git log -- filename.txt

# 特定の期間の履歴
git log --since="2025-01-01" --until="2025-12-31"

# 特定の作者の履歴
git log --author="John Doe"

# 変更内容も表示
git log -p

# 統計情報も表示
git log --stat
```

### 差分の確認

```bash
# 作業ディレクトリとステージングエリアの差分
git diff

# ステージングエリアと最新コミットの差分
git diff --staged
git diff --cached

# 特定のファイルの差分
git diff filename.txt

# ブランチ間の差分
git diff main feature-branch

# コミット間の差分
git diff abc1234 def5678

# 統計のみ表示
git diff --stat
```

### ファイルの履歴確認

```bash
# 各行の最終更新者を表示
git blame filename.txt

# 特定の行範囲を表示
git blame -L 10,20 filename.txt

# ファイルの過去のバージョンを表示
git show abc1234:filename.txt

# ファイルの変更履歴を追跡
git log --follow filename.txt
```

---

## タグ操作

### タグの確認

```bash
# タグ一覧
git tag

# パターンに一致するタグを検索
git tag -l "v1.*"

# タグの詳細情報
git show v1.0.0
```

### タグの作成

```bash
# 軽量タグを作成
git tag v1.0.0

# 注釈付きタグを作成（推奨）
git tag -a v1.0.0 -m "Version 1.0.0"

# 過去のコミットにタグを付ける
git tag -a v0.9.0 abc1234 -m "Version 0.9.0"
```

### タグの削除

```bash
# ローカルのタグを削除
git tag -d v1.0.0

# リモートのタグを削除
git push origin --delete v1.0.0
```

### タグのプッシュ

```bash
# 特定のタグをプッシュ
git push origin v1.0.0

# 全てのタグをプッシュ
git push --tags
```

---

## 取り消し・修正

### 作業ディレクトリの変更を取り消し

```bash
# 特定のファイルの変更を取り消し
git checkout -- filename.txt

# 最新のGit（2.23以降）
git restore filename.txt

# 全てのファイルの変更を取り消し
git checkout -- .
git restore .
```

### ステージングを取り消し

```bash
# 特定のファイルをステージングから外す
git reset HEAD filename.txt

# 最新のGit（2.23以降）
git restore --staged filename.txt

# 全てのファイルをステージングから外す
git reset HEAD
git restore --staged .
```

### コミットの取り消し

```bash
# 直前のコミットを取り消し（変更は残す）
git reset --soft HEAD~1

# 直前のコミットを取り消し（ステージングも解除）
git reset --mixed HEAD~1
git reset HEAD~1  # --mixedがデフォルト

# 直前のコミットを取り消し（変更も破棄）
git reset --hard HEAD~1

# 特定のコミットまで戻る
git reset --hard abc1234

# コミットを打ち消す新しいコミットを作成
git revert HEAD

# 複数のコミットを打ち消す
git revert abc1234 def5678
```

### 特定のファイルを過去の状態に戻す

```bash
# 特定のコミットの状態に戻す
git checkout abc1234 -- filename.txt

# 最新のGit（2.23以降）
git restore --source=abc1234 filename.txt
```

---

## 便利なコマンド・エイリアス

### よく使うエイリアスの設定

```bash
# ステータス確認
git config --global alias.st status

# ブランチ一覧
git config --global alias.br branch

# コミット
git config --global alias.ci commit

# チェックアウト
git config --global alias.co checkout

# 最新のコミット
git config --global alias.last 'log -1 HEAD'

# グラフ表示
git config --global alias.lg "log --graph --oneline --all --decorate"

# 直前のコミットを修正
git config --global alias.amend 'commit --amend --no-edit'

# ブランチを最新に更新
git config --global alias.up 'pull --rebase --autostash'
```

使用例:
```bash
git st           # git statusと同じ
git br           # git branchと同じ
git lg           # 綺麗なログ表示
git amend        # 直前のコミットを修正
```

---

## Windows/Mac 環境別の注意点

### パスの表記

**Windows:**
```cmd
# バックスラッシュ または スラッシュ
C:\Users\username\project
C:/Users/username/project
```

**Mac:**
```bash
# スラッシュのみ
/Users/username/project
```

### ホームディレクトリ

**Windows:**
```cmd
# ホームディレクトリ
%USERPROFILE%
# 例: C:\Users\username

# Gitの設定ファイル
%USERPROFILE%\.gitconfig
```

**Mac:**
```bash
# ホームディレクトリ
~
# 例: /Users/username

# Gitの設定ファイル
~/.gitconfig
```

### 改行コード

**Windows:**
- デフォルト: CRLF (`\r\n`)
- 推奨設定: `git config --global core.autocrlf true`

**Mac:**
- デフォルト: LF (`\n`)
- 推奨設定: `git config --global core.autocrlf input`

### ファイル名の大文字・小文字

**Windows:**
- 大文字・小文字を区別しない

**Mac:**
- 大文字・小文字を区別する（デフォルトは区別しない設定も可）

ファイル名の変更時の注意:
```bash
# 大文字・小文字の変更は明示的に行う
git mv filename.txt FILENAME.txt
```

---

## トラブルシューティング

### よくあるエラーと対処法

**エラー: "fatal: not a git repository"**
```bash
# Gitリポジトリではないディレクトリで実行している
# 解決: 正しいディレクトリに移動するか、git initする
git init
```

**エラー: "fatal: refusing to merge unrelated histories"**
```bash
# 関連のない履歴をマージしようとしている
# 解決: 強制的にマージを許可
git pull origin main --allow-unrelated-histories
```

**エラー: "error: Your local changes would be overwritten"**
```bash
# 変更をコミットまたはスタッシュする
git stash
git pull
git stash pop
```

**プッシュが拒否される**
```bash
# リモートが先に進んでいる場合
# 解決: プルしてからプッシュ
git pull --rebase
git push
```

---

## 次のステップ

このドキュメントで基本コマンドを学んだら、次は以下を学習しましょう：

1. [GitHubの使い方](./github-usage.md) - GitHub上での操作
2. [ブランチ戦略](./branching-strategies.md) - チーム開発のワークフロー
3. [ショートカットキー](./shortcuts.md) - 作業効率化

---

**最終更新**: 2025-10-13
