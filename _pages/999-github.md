---
title: githubメモ
author: sam-ple
## date: 2024-05-01
category: memo
layout: post
---

簡易📝

■ブランチ
―――――――――――
git switch -c dev
git push -u origin dev
―――――――――――
git switch main
git pull origin main
git branch -d dev
git push --delete origin dev
―――――――――――
git branch -a
―――――――――――
ruby "C:\～.rb"
―――――――――――

## 事前準備

## Gitをインストール

### Windows
- Gitをインストール
  - 全てデフォルトの状態で問題無し

### Mac
- xcode-select --install
- /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
- インストールが進み、[Installation Success]と表示されたらインストール完了。
- brew -v
- brew install git
- git --version

## Gitの設定
- Gitの基本設定をGit Bashから行う
  - git config --global user.name {自分の名前}
  - git config --global user.email {メールアドレス}
- VSCodeをインストール
- VSCodeの日本語化
  - 拡張機能(Crtl+Shift+X)からjapaneseを検索しインストール→再起動
- 隠しファイルを見える様にしておく
  - エクスプローラーを開き、表示タブ⇒『ファイル名拡張子』と『隠しファイル』にチェック
- フォルダーを作成し、そのフォルダーをVSCodeで開く
- ローカルリポジトリとして初期化
  - ソース管理(Crtl+Shift+G)→リポジトリを初期化する＜git init＞
  - 『.git』というフォルダーが作成されていると成功
- GitHubでリモートリポジトリを作成
  - リポジトリ名を入力
  - プライベートリポジトリで作成
  - READMEは作らず
- ローカルリポジトリとGitHubのリモートリポジトリを紐づける
  - 新しいターミナル(Crtl+@)の＋からGit Bashを開く
  - git remote add origin https://github.com/{ユーザー名}/{リポジトリ名}.git
  - git remote -vでチェックを行う
    - origin  https://github.com/{ユーザー名}/{リポジトリ名}.git (fetch)
    - origin  https://github.com/{ユーザー名}/{リポジトリ名}.git (push)     
  - git branch -M main
- VSCode上でファイルを編集・追加する
  - M：Modified（変更された）
  - U：Untracked（追跡対象外）
  - R：
  - D：
  - A：
- 変更のステージング・コミットする
  - コミットメッセージが無いとエラー
  - 📝
  - Add / Update / Clean / Remove / Upgrade / Test
- 変更をリモートリポジトリにプッシュする
  - git push -u origin main
- GitHubに反映されたかを確認

## VSCodeメモ
- editor遷移：秀丸→サクラエディタ→TeraPad→Sublime Text→Atom→VSCode
- ショートカットキー
  - エクスプローラー：Ctrl+Shift+E
  - 検索：Ctrl+Shift+F
  - ソース管理：Ctrl+Shift+G
  - 実行とデバック：Ctrl+Shift+D
  - 拡張機能：Ctrl+Shift+X
  - エディターを右に分割：Ctrl+\
- プレビュー表示（標準装備）
  - サイドバイサイドにプレビューを表示：［Ctrl］＋［K］→［V］
  - 同一エディタに別タブとしてプレビューを表示：［Ctrl］＋［Shift］＋［V］
- Markdown All in Oneをインストール
  - markdown記入補佐
  - tableの整列：Alt + Shift + Fで整形 
  - 目次：Ctrl + Shift + P　＞　toc 
- htmlやpdfにエクスポート
  - ~~markdown pdfをインストール~~
  - Markdown Preview Enhancedをインストール
- Excel Viewerをインストール
  - Ctrl + Shift + V。
  - エクスプローラタブで右クリック→Open Preview
- Ascii Tree Generatorをインストール
  - 該当フォルダを右クリック。全体は出来ない？
- アイコン設定
  - ~~vscode-iconsをインストール~~
  - Material Icon Themeをインストール
- markdown記述用。文末に半角スペース2つ追加。置換(Crtl+H)にて正規表現「$」を「  」に置換。
- 半角スペースを見やすく
  - 「ファイル」＞「ユーザー設定」＞「設定」（Ctrl+,）
  - 「whitespace」にて検索し、「Editor:Render Whitespace」の設定をallに変更。
    - none : 表示しない
    - boundary : 単語間の単一空白文字以外を表示する
    - selection : 選択している間のみ空白文字を表示する
    - trailing : 末尾の空白文字のみ表示する
    - all : すべての空白文字を表示する
- 設定の同期をGithubアカウントにて行う。
- タブをスペースにしない
  - 「ファイル」＞「ユーザー設定」＞「設定」（Ctrl+,）
  - 「tab insert」にて検索し、「Editor: Insert Spaces」という項目のチェックを外す。
  - 「Editor: Detect Indentation」のチェックも外す。
- フォント設定
  - ユーザー設定＞設定（Ctrl + ,）＞font family
  - Consolas, 'Courier New', monospace
  - HackGen, 'HackGen Console Hack', HackGen35, 'HackGen35 Console'
  - ~~PlemolJP, 'PlemolJP Console', PlemolJP35, 'PlemolJP35 Console'~~

#### VSCodeのターミナルをGit Bashに変更
- Ctrl + ,のショートカットで、Settings 画面に移動
- 検索欄に Terminal.Integrated.Default Profile: Windows を打ち込み、
Git bash を選択

#### 同じ名前のリポジトリは作成可能
- 一度該当リポジトリを削除。新規で同じ名前で作成。
- .gitフォルダの中身を削除 
- $ find . -type d -name .git -exec rm -rf {} \; -print
- $ git init
- git remote add origin https://github.com/{ユーザー名}/{リポジトリ名}.git
- git remote -vでチェックを行う
- git branch -M main

#### ブランチ
- git switch main
- git switch -c dev
  - git switch -C dev
  - 大文字のCの場合、指定したブランチが存在した場合でも強制的に作成されるため注意
  - id/001 / style
- git branch
- git push -u origin dev  //リモートに登録
- git branch -a
- git add .
- git commit -m "◯◯という機能を追加した close #◯"
- git push origin dev
  - (git push origin HEAD)
- git switch main
  - (git switch -)
- git pull origin main
  - (git pull)
- git branch -d dev
- git push --delete origin dev

### ああああ
- git branch
- git stash
- git status
- git switch dev
- git stash apply
- git stash list

### Gitの履歴を全削除
- チェックアウト
- git checkout --orphan about_branch
- 追加・コミット
- git add -A
- git commit -am "initial commit"
- ブランチを削除・現在のブランチの名前をmainに変更
- git branch -D main
- git branch -m main
- リポジトリを強制的に更新
- git push -f origin main
- アクションには残る

### い
- GitHub の Settings - Emails にある Keep my email addresses private を有効化
- GitHub の Settings - Emails にある Block command line pushes that expose my email を有効化
- Git の設定の user.email を [ID]+[GitHub アカウント名]@users.noreply.github.com に設定する

#### Github page
- Settings→Pages→Branchにてmain/rootを選択してSave
- .nojekyllファイル

## Ruby

https://rubyinstaller.org/downloads/
からダウンロードしてインストール

macOSユーザーであれば最初からPCにRubyが入っている

[macOS]ターミナル / [Windows]コマンドプロンプト
$ ruby -v

Powershell
Ruby --version

code runnerをインストール
Ruby以外でも、 C, C++, Java, JavaScript, PHP, Python, Perl, Go, Lua, Groovy, PowerShell, BAT/CMD, BASH/SH, F# Script, F# (.NET Core), C# Script, C# (.NET Core), VBScript, TypeScript, CoffeeScript, Scala, Swift, Julia, Crystal, OCaml Script, R, AppleScript, Elixir, Visual Basic .NET, Clojure, Haxe, Objective-C, Rust, Racket, AutoHotkey, AutoIt, Kotlin, Dart, Free Pascal, Haskell, Nim, Dが特に設定せずに使用可能

コマンドパレット（Ctrl + Shift + p）を開き、run codeと検索して、コマンドを選び実行します。
ショートカットはctrl + alt + N

入力がある際はコマンドプロンプトから実行。

[macOS]ターミナル / [Windows]コマンドプロンプト
# Nokogiriのインストール
$ gem install nokogiri

# Nokogiriのインストールを確認
$ gem list nokogiri

Ruby3からはopenではなく、URI.openを使う

# git の branch を復元
% git reflog
% git branch recover HEAD@{1}
% git branch
* master
  recover