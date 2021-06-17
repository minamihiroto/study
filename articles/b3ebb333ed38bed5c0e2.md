---
title: "GOの勉強を始める"
emoji: "🦫"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["GO"]
published: true
---
随時更新

[ここにコード類は載せてるよ](https://github.com/minamihiroto/GO)

# 環境構築
1. [dockerfileを作成](https://github.com/minamihiroto/GO/blob/3cbf0cfa1fd4cb8bab6666e2a9d8ab6e929a1461/app/dockerfile)
2. [docker-compose.ymlを作成](https://github.com/minamihiroto/GO/blob/3cbf0cfa1fd4cb8bab6666e2a9d8ab6e929a1461/docker-compose.yml)
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

# 基礎初級~progate~
- [変数について](https://github.com/minamihiroto/GO/tree/3cbf0cfa1fd4cb8bab6666e2a9d8ab6e929a1461)
- [条件分岐について](https://github.com/minamihiroto/GO/tree/48e171bdeeb1c7f08999a99a0957d1e3e4bc4d63)
- [Printfの基礎について](https://github.com/minamihiroto/GO/tree/11bcab89ccdf9cd9d268291a5e5aa6f43441e912)
- [繰り返し処理について](https://github.com/minamihiroto/GO/tree/33a03d7d5c34bfd86f02710750099b0b7ac2367b)
- [乱数について](https://github.com/minamihiroto/GO/tree/2f4aec6e2e1c854dd097d0125132f3de4050d78e)
- [文字列の入力について](https://github.com/minamihiroto/GO/tree/610acf51728081960c033d7ad08753d7ea802c1d)
- [関数について１](https://github.com/minamihiroto/GO/tree/7d562ab99b4288d051bf8ac8c0a0004124eaa8db)
- [関数について２](https://github.com/minamihiroto/GO/tree/58734db44fba8e8b2e980f2afc2ea73213c29477)

# 基礎初級~A Tour of Go~
- [複数戻り値について](https://github.com/minamihiroto/GO/tree/92fc074b84c597a704b8f4c39a1ac282ec245441)
- [戻り値に名前をつける](https://github.com/minamihiroto/GO/tree/7c2e85834244d92325a2ba937bea4d0f695c27bf)
変数について
  - 関数外で定義する際はキーワードではじまる宣言( var, func, など)が必要、:=ではだめ
  - 変数に初期値を与えないとゼロ値( zero value )が与えられる 👉nullではない
    - 数値型は0
    - bool型はfalse
    - string型は""(空文字)
- [定数について](https://github.com/minamihiroto/GO/tree/f7caa67bd3fbf6c82d110bf892b750a0f184d845)
- [importをまとめる](https://github.com/minamihiroto/GO/tree/e43d47b9005c0f356be4772aa84adbc18c0150db)

# 基礎中級~progate~
変数はコンピュータの**メモリ**に保存され、その場所を**アドレス**と呼ぶ
👉アドレスは16進数で表され、他の変数に代入することもできる
👉GOではアドレスを**ポインタ**と呼び扱っている
- [ポインタについて](https://github.com/minamihiroto/GO/tree/64126df15f7ad1413bd0703e7ccd24d5b84309dc)
ポインタが代入された変数を**ポインタ型変数**と呼ぶ
ポインタ型は「*変数の型」で定義できる
- 変数に"&"をつける👉"ポインタ"を出力できる
- ポインタ型変数に"*"をつける👉"ポインタが示す変数の値"を出力できる
- [ポインタ型変数について](https://github.com/minamihiroto/GO/tree/9b8c8b8343225a75df0b40647eef91d64d6cd4bb)
- [関数をまたぐポインタについて](https://github.com/minamihiroto/GO/tree/904fee69f8d5d2c18b603898423be614cb09f3d1)
- [引数のポインタについて１](https://github.com/minamihiroto/GO/tree/27170077493140e787924bd64691292220fd13a2)
- [引数のポインタについて２](https://github.com/minamihiroto/GO/tree/65264a7de4dcbaab173d51150c764011ddd13b8d)

# 基礎中級~A Tour of Go~
- [構造体について](https://github.com/minamihiroto/GO/tree/19e034f8fa2c68a7f3137481009f2cb1bd1b769c)
- [レシーバについて](https://github.com/minamihiroto/GO/tree/b26bb9f21b476b976dd1f2809d54aeefe9cf7c06)
- [メソッドについて](https://github.com/minamihiroto/GO/tree/22bf584153a174aaa5071bc646a253b1f90417f1)
- [レシーバを引数にとる関数について](https://github.com/minamihiroto/GO/tree/8016f8dddc0244917ef3ff8a08b6cc366c6eeaa9)
- [型の別名作成について](https://github.com/minamihiroto/GO/tree/5cddec50052c297908cd4e2135282c6b35f9410e)