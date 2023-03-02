---
title: "Google ColabでGPT-3のファインチューニングを試す方法"
emoji: "🎹"
type: "tech" 
topics: [Google Colaboratory,Google Colab,"GPT","GPT3","fine-tuning","ファインチューニング","chatGPT"]
published: true
---
自分はOpenAI APIの無料期間内に行ったため、期間後の課金設定が必要かは知らない（多分いる）

とりあえず公式の情報をみて、JSONのデータセットを用意しておく。
https://platform.openai.com/docs/guides/fine-tuning

```JSON
{"prompt": "<prompt text>", "completion": "<ideal generated text>"}
{"prompt": "<prompt text>", "completion": "<ideal generated text>"}
{"prompt": "<prompt text>", "completion": "<ideal generated text>"}
```

「data.json」としてファイルを保持して進める
![イメージ1](/images/example-image1.png)

そしたら早速コードを書いていく
とりあえずいつものようにoprnaiをpip installする
```python
!pip install --upgrade openai -q
```

その次に必要なライブラリとAPIキーの設定
```python
import openai
import requests
import json
openai.api_key = "<APIキー>"
```

ここでdata.jsonを学習用の拡張子jsonlに変換する必要があるので、下記コマンドを記述
```python
!openai tools fine_tunes.prepare_data -f data.json
```

実行すると途中で[Recommended] ...のような記載が返ってくるので、とりあえずYで進める
（これはデータの記述をええ感じにしてくれるやつなので、基本YでOK、こだわりあるならnで無視しよう）

成功するとdata.jsonファイルの下に、data_prepared.jsonlというファイルができているのが確認できる
これで下準備が終わったので、早速ファインチューニングを試すことにする

これで実行！....
```python
%env OPENAI_API_KEY=APIキー
!openai api fine_tunes.create -t "data_prepared.jsonl" -m "curie"
```

こんな感じで進んでいってくれます
```
Found potentially duplicated files with name 'data_prepared.jsonl', purpose 'fine-tune' and size 411 bytes
file-xxxxxxxxxxxx
Enter file ID to reuse an already uploaded file, or an empty string to upload this file anyway: 
Upload progress: 100% 411/411 [00:00<00:00, 464kit/s]

Uploaded file from data_prepared.jsonl: file-xxxxxxxxxxxx
Created fine-tune: ft-xxxxxxxxxxxx
Streaming events until fine-tuning is complete...

(Ctrl-C will interrupt the stream, but not cancel the fine-tune)

[2023-03-02 17:06:54] Created fine-tune: ft-xxxxxxxxxxxx
```

このまま成功すれば嬉しいのですが、大体下記のような感じで、途中切断されます
```
Stream interrupted (client disconnected).
To resume the stream, run:

  openai api fine_tunes.follow -i ft-xxxxxxxxxxxx
```

自分は1発で成功したことないです
上記で書いてある通り、帰ってきたコマンドをそのまま打っちゃいましょう
```python
!openai api fine_tunes.follow -i ft-xxxxxxxxxxxx
```

```
Stream interrupted (client disconnected).
To resume the stream, run:

  openai api fine_tunes.follow -i ft-xxxxxxxxxxxx
```

はい、またダメでした
自分はこれを5,6回ほど続けてやっと成功する場合もありました
もうなんどもやってますが、本当に1発で成功しません
なんでか教えてください偉い人🥺

ちなみに成功するとこんな感じになります
```
[2023-03-02 17:06:54] Created fine-tune: ft-xxxxxxxxxxxx
[2023-03-02 17:12:05] Fine-tune costs $x.xx
[2023-03-02 17:12:06] Fine-tune enqueued. Queue number: 0
[2023-03-02 17:12:09] Fine-tune started
[2023-03-02 17:13:10] Completed epoch 1/4
[2023-03-02 17:13:10] Completed epoch 2/4
[2023-03-02 17:13:11] Completed epoch 3/4
[2023-03-02 17:13:11] Completed epoch 4/4
[2023-03-02 17:13:30] Uploaded model: curie:ft-xxxxxxxxxxxx
[2023-03-02 17:13:31] Uploaded result file: file-xxxxxxxxxxxx
[2023-03-02 17:13:31] Fine-tune succeeded

Job complete! Status: succeeded 🎉
Try out your fine-tuned model:

openai api completions.create -m curie:ft-xxxxxxxxxxxx -p <YOUR_PROMPT>
```

これにてファインチューニング完了です
いくら使われるかとかも書いてます
レスポンスの最後に記載されているコマンドでパラメータ設定なしの簡単テストが可能です

あとはよしなにパラメータを書いて、request.post投げればファインチューニングしたモデルで回答してくれます！

自分は正直いいデータセットを用意できなかったので、あまりいい使い方はできませんでした...
誰かの役に立てれば幸いです
もしどこか記述が間違っていたりしたら優しく教えてください🙇‍♂️
GPT3.5も出たことだし、次はそっちで遊んでいきたいと思います！（GPT3.5はファインチューニング未対応 23/3/3現在）