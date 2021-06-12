---
title: "GOの勉強を始める"
emoji: "🦫"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["GO"]
published: false
---

[ここにコード類は載せてるよ](https://github.com/minamihiroto/go_plactice)

# 環境構築
1. dockerfileを作成
2. docker-compose.ymlを作成
3. vscodeのソース管理タブで"GitHubに公開"を選択し、リポジトリ名を決めpush
  - リモートで`git init`、ローカルで`git init`、`git add .`、`git commit -m "first commit"`、`git remote add origin https://github.com~~~~`、`git push`まで自動で行われる
4. [masterからmainに変更する（githubのリモート＆ローカルブランチ）branches](https://qiita.com/masakinihirota/items/1a657674e609be112fc6)
5. `docker-compose up -d`で起動
6. `docker-compose down`で削除

# コードを記述
1. マウントディレクトリにmain.goを作成
2. `docker-compose up -d`で起動
3. `docker-compose exec app go run main.go`
  - `docker-compose run app go run main.go`ならdockercomposeが起動していなくても実行できる

