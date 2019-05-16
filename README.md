# mk_oct2019_graphpipe

Oracle Fnが実行できるようセットアップし、Classy部分をFunction化する

<img src="attach:classy.png" alt="attach:classy">

```
# classy-funcの雛形作成
$ fn init --runtime go classy-func
$ cd classy-func/
GoのFDKを使ったHelloWorldサンプルアプリケーションが classy-func/ 以下に作成されています。
ここをgithub上のファイルに置き換えます。

# Functionのdeploy 
$ fn --verbose deploy --app classy-fn

# Functionの実行
$ echo -n '{"name": "https://www.oracle.com/assets/candy-177355-ja.jpg"}' |fn invoke classy-fn  classy-func
```

