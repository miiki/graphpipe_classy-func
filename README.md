# mk_oct2019_graphpipe

Oracle Code Tokyo のデモで実施した Oracle Fn のファンクション

Oracle Fnが実行できるようセットアップした後、

# classy-funcの雛形作成
$ fn init --runtime go classy-func
$ cd classy-func/
GoのFDKを使ったHelloWorldサンプルアプリケーションが classy-func/ 以下に作成されています。ここをgithub上のファイルに置き換えます。

# Functionのdeploy 
$ fn --verbose deploy --app classy-fn

# Functionの実行
$ echo -n '{"name": "https://www.oracle.com/assets/candy-177355-ja.jpg"}' |fn invoke classy-fn  classy-func
