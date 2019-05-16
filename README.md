# mk_oct2019_graphpipe

Downloader, Preprocessor, VGG はこちらの Implementation of Classyで紹介されているDockerを使用します。  
https://hackernoon.com/machine-learning-model-pipelines-part-ii-23ebd1e6b714
  
Classy部分をFunction化しました。

1. Oracle Fnが実行できるようセットアップ

2. classy-funcの雛形作成とファイルの修正
```
$ fn init --runtime go classy-func
$ cd classy-func/
(GoのFDKを使ったHelloWorldサンプルアプリケーションが classy-func/ 以下に作成されています。
ここをgithub上のファイルに置き換えます。
func.go内のURLを環境にあわせて編集します)
```

3. Functionのdeploy 
```
$ fn --verbose deploy --app classy-fn
```

4. Functionの実行※拡張子が *.jpg のJPEGファイルを指定
```
$ echo -n '{"name": "https://dummy.com/abc.jpg"}' |fn invoke classy-fn  classy-func

```
