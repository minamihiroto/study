---
title: "GOlang入門"
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
- [ポインタレシーバをメソッドに適用する方法について・改](https://github.com/minamihiroto/GO/tree/b574710faf9fb657c7538bfda9a0cd2fcd608691)
- [インターフェースについて](https://github.com/minamihiroto/GO/tree/dcaf07307103e70905aeb6179ac326801725258d)
nilはポインター、インターフェイス、マップ、スライス、チャネル、および関数タイプのゼロ値である
- [nilについて](https://github.com/minamihiroto/GO/tree/a9101c250496d8379ccaeb297d92b494bde4bbc2)
アサーションは2つの値(基になる値とアサーションが成功したかどうかを報告するブール値)を返す
- [型アサーションについて](https://github.com/minamihiroto/GO/tree/bf9ad12f0b8eee35e478376293ae670317f80858)
- [型switchについて](https://github.com/minamihiroto/GO/tree/1251f9ecf6b2ceec6d303cb68de0a52afa513288)
- [Stringersについて](https://github.com/minamihiroto/GO/tree/0f631c975ebe16e70d631c77db53fe39b5e1e47f)

# Moduleについて
（modファイル作る前からfmtとか使えたけどなぜなのか）
Goのパッケージ管理システム

go.modファイルを作成する
`$ go mod init 命名`

パッケージのインストール方法
go.sumファイルが作られ、これにはパッケージのバージョンとそのhash値が入っている
👉 npmでいうpackage.lock.jsonみたいなもの
`$ go get -u インストールしたいパッケージ`
👉 -uをつけることで、パッケージとその依存パッケージをネットワークから更新できる

未使用のパッケージを削除する
`$ go mod tidy -v`
👉 -vをつけることで、削除されたパッケージ情報を出力できる


先にmain.goにimportされていないパッケージを記述しておいて、コマンドでインストールする
`$ go build`
👉 本来はコンパイルする為に使われるコマンド
👉 コンパイル後はバイナリファイルが生成され、ファイル名を指定しただけでGOが走る(runする)
👉 バイナリファイルはgo.modにあるmodule名になる

環境変数を表示
`$ go env`

# スターティングGo言語
- [パッケージと構成について１](https://github.com/minamihiroto/GO/tree/9229b417e01e8ab89561be08430b6955668490d5)
  - Goは1つのディレクトリには1つのパッケージのみ定義可能であり、複数のパッケージ定義を同一のディレクトリ内に置くことはできない
- [パッケージと構成について２](https://github.com/minamihiroto/GO/tree/9b5127d27f95bcf85c015ece44512d4bca5b88cc)
  - mainパッケージの分割
  - `$ go run main.go app.go`か`$ go run *.go`で実行
- [パッケージと構成について３](https://github.com/minamihiroto/GO/tree/40ad23ea84356b481a1e2f32fd69769ca360ab4d)
- [パッケージと構成について３`](https://github.com/minamihiroto/GO/tree/523b320a1b3a9fac12b09a87f916497ddfced1b9)
  - Goにはパッケージの機能をテストする機能がある
  - testingにテストを行うためのさまざまな関数がある
    - 今回使ってるのはErrorf()
  - `$ go test module名/ディレクトリ名`でテストを実行
- [変数の暗黙的宣言のスコープについて](https://github.com/minamihiroto/GO/tree/b28a131718bac2e3f57df66a42774fc05d32ee6f)
- [複数行にまたがる文字列について](https://github.com/minamihiroto/GO/tree/d59880e0ba63a31093f46be7ff9d01ba5c95cfb7)
- [配列について１](https://github.com/minamihiroto/GO/tree/8cc5a8471ede60b89de6b095a1358e8db03d06d8)
  - [要素数]要素の型 で一つの型として認識している
    - [5]int !== [3]int
    - [5]int === [5]int
- [配列について２](https://github.com/minamihiroto/GO/tree/e1d77346102652ddb42fa34b902b71a922dff055)
  - Goの配列型は拡張、縮小は不可能
  - 要素数は一定 👉 可変式にしたいなら**スライス**というデータ構造を使う
- [関数の戻り値について](https://github.com/minamihiroto/GO/tree/5ad88141ab87aef621d66106d74b56588f76293c)
  - 割り振り代入 👉 複数の戻り値を一気に変数に代入すること
  - 戻り値の破棄 👉 複数の戻り値のうち、いらない値を破棄して戻り値を受け取ること
- [無名関数について](https://github.com/minamihiroto/GO/tree/d197b99513a20e00d6940e73d01f8d338a8a10a5)
- [関数の別名について](https://github.com/minamihiroto/GO/tree/6d0f0c30f82aedaf06d4a18fd9c7efc7923c5d83)
- [クロージャについて](https://github.com/minamihiroto/GO/tree/b2976a8837d9a9ed194be1847d9281ba074387c1)
  - **無名関数**と**無名関数の処理に関係する無名関数外の環境**のことをクロージャという
- [定数定義について](https://github.com/minamihiroto/GO/tree/02fab24954c5806f5be70d6fbe70836aa240a2b1)
- Goのスコープについて、大きい順で
  - パッケージ
    - 複数のファイルで構成されている
    - 定数、変数、関数などが他のパッケージから参照可能であるかは**識別子の一文字目**が大文字であるかどうかで決まる
    - `fmt.Println()`はfmtパッケージのPrintln関数を呼び出しているが、これはPrintln関数が大文字から始まっているから参照ができている
  - ファイル
    - 同じパッケージのファイルでも、各々のimport定義が独立して働く
    - 片方のファイルでは「f \"fmt\"」という定義、もう片方では「. \"fmt\"」という定義が成立する
  - 関数
  - ブロック
    -  **{ ... }** で囲われたソースコード群
  - 制御構文
- [パッケージ名上書きについて](https://github.com/minamihiroto/GO/tree/57ec196cc05b94e71da6c8a1ffd70528a12adfa7)  
- [if,forについて](https://github.com/minamihiroto/GO/tree/8c3d01f6a3a3e8610fe5dadffc50adfce2737065)
- [配列のfor文表示について](https://github.com/minamihiroto/GO/tree/b2121c84d7432ea5d697e754a9478a71ce1345c1)
- [switchについて](https://github.com/minamihiroto/GO/tree/041092deac4b6d8e34e64502a8683577d7fb1c8c)
  - 簡易文は変数の局所性を高める働きがあるため、積極的に使っていく
- [goto文について]()
  - ほとんど使うことがない
- [ラベル付き文について]()
- [deferについて]()
  - 定義されるものは関数呼び出しの形式に限られる
  - 例1
```go
  defer fmt.Println("A")//関数呼び出しの形式 👉 最後に()がつく
```
  - 例2
```go
  defer func(){
    fmt.Println("A")
    fmt.Println("B")
    }() //関数呼び出しの形式 👉 最後に()がつく
```