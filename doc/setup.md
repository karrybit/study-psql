# setup

## install for mac

brewでinstallする。 結構前に入れたからエラーが出るかどうかは知らない。気がついたら既に入ってた。

```sh
brew install postgresql
```

## init

`initdb`を使う。実行すると指定したパス配下に設定ファイルとかが色々できる。

```sh
initdb /usr/local/var/postgres -E utf-8
```

`pg_ctl`経由で実行することもできる。

```sh
pg_ctl -D /usr/local/var/postgres initdb
```

## start

起動コマンド。`-D`はデータベースのファイルパスを指定するオプション。

```sh
postgres -D /usr/local/postgres
```

`pg_ctl`経由で実行することもできる。

```sh
pg_ctl start -l ${logfile}
```

## stop

```sh
pg_ctl stop
```
