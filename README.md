# mk_oct2019_graphpipe

Oracle Fnが実行できるようセットアップし、Classy部分をFunction化します。

```
# classy-funcの雛形作成とファイルの修正
$ fn init --runtime go classy-func
$ cd classy-func/
(GoのFDKを使ったHelloWorldサンプルアプリケーションが classy-func/ 以下に作成されています。
ここをgithub上のファイルに置き換えます。
func.go内のURLを環境にあわせて編集します)

# Functionのdeploy 
$ fn --verbose deploy --app classy-fn

# Functionの実行 
$ echo -n '{"name": "https://dummy.com/abc.jpg"}' |fn invoke classy-fn  classy-func
※拡張子が *.jpg のJPEGファイルを指定
```

Downloader, Preprocessor, VGG はこちらの Implementation of Classyで紹介されているDocker Imageをそのまま使用します。
https://hackernoon.com/machine-learning-model-pipelines-part-ii-23ebd1e6b714
