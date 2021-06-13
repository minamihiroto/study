---
title: "GOの勉強を始める"
emoji: "🦫"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["GO"]
published: true
---
随時更新

[ここにコード類は載せてるよ](https://github.com/minamihiroto/go_plactice)

# 環境構築
1. dockerfileを作成
2. docker-compose.ymlを作成
3. vscodeのソース管理タブで"GitHubに公開"を選択し、リポジトリ名を決めpush
  - リモートで`git init`、ローカルで`git init`、`git add .`、`git commit -m "first commit"`、`git remote add origin https://github.com~~~~`、`git push`まで自動で行われる
4. [masterからmainに変更する（githubのリモート＆ローカルブランチ）branches](https://qiita.com/masakinihirota/items/1a657674e609be112fc6)
5. `docker-compose up -d`で起動
6. `docker-compose down`で削除

# コードを実行
1. マウントディレクトリにmain.goを作成
2. `docker-compose up -d`で起動
3. `docker-compose exec app go run main.go`
  - `docker-compose run app go run main.go`ならdockercomposeが起動していなくても実行できる

# 基礎~progate~
- [変数について](https://github.com/minamihiroto/GO/tree/3cbf0cfa1fd4cb8bab6666e2a9d8ab6e929a1461)
- [条件分岐について](https://github.com/minamihiroto/GO/tree/48e171bdeeb1c7f08999a99a0957d1e3e4bc4d63)
- [Printfの基礎について](https://github.com/minamihiroto/GO/tree/11bcab89ccdf9cd9d268291a5e5aa6f43441e912)
- [繰り返し処理について](https://github.com/minamihiroto/GO/tree/33a03d7d5c34bfd86f02710750099b0b7ac2367b)
- [乱数について](https://github.com/minamihiroto/GO/tree/2f4aec6e2e1c854dd097d0125132f3de4050d78e)
- [文字列の入力について](https://github.com/minamihiroto/GO/tree/610acf51728081960c033d7ad08753d7ea802c1d)
- [関数について１](https://github.com/minamihiroto/GO/tree/7d562ab99b4288d051bf8ac8c0a0004124eaa8db)
- [関数について２](https://github.com/minamihiroto/GO/tree/58734db44fba8e8b2e980f2afc2ea73213c29477)

# 基礎~A Tour of Go~
- [複数戻り値について](https://github.com/minamihiroto/GO/tree/92fc074b84c597a704b8f4c39a1ac282ec245441)
- [戻り値に名前をつける](https://github.com/minamihiroto/GO/tree/7c2e85834244d92325a2ba937bea4d0f695c27bf)
変数について
  - 関数外で定義する際はキーワードではじまる宣言( var, func, など)が必要、:=ではだめ
  - 変数に初期値を与えないとゼロ値( zero value )が与えられる 👉nullではない
    - 数値型は0
    - bool型はfalse
    - string型は""(空文字)
- [定数について](https://github.com/minamihiroto/GO/tree/f7caa67bd3fbf6c82d110bf892b750a0f184d845)