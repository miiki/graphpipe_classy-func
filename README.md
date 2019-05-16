# ClassyコンテナをFn化する

BLOGの最後の例、「Implementation of Classy」で紹介されているDockerを使用します。  
https://hackernoon.com/machine-learning-model-pipelines-part-ii-23ebd1e6b714
  
Classy, Preprocessor, Downloader, VGG の4つのDockerコンテナのうち、Classy以外のDockerコンテナを起動します。  
以下の手順で、Classy部分をFunction化したサンプルプログラムが実行できます。

1. Oracle Fnが実行できるようセットアップ  
ローカル環境で動くよう Oracle Fn ProjectをセットアップすればOKです。  
(Oracle Cloud環境で動かす場合は、Oracle Cloudのお申込みと申請が必要となります。）

2. classy-funcの雛形作成とファイルの修正
```
$ fn init --runtime go classy-func
$ cd classy-func/

※GoのFDKを使ったHelloWorldサンプルアプリケーションが classy-func/ 配下に作成されています。
ここをgithub上のファイルに置き換えます。
func.go内の preprocessor := と downloader := のURLを、環境にあわせて編集します。
```

3. Functionのdeploy 
```
$ fn --verbose deploy --app classy-fn
```

4. Functionの実行 ※拡張子が.jpg のJPEGファイルを指定
```
$ echo -n '{"name": "https://dummy.com/abc.jpg"}' |fn invoke classy-fn  classy-func
```
