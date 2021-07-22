# dump and restore

## ダンプ

```sh
pg_dump ${database_name} > ${dumpfile}
```

## リストア

```sh
psql ${database_name} < ${dumpfile}
```

### error時に終了させる

```sh
psql --set ON_ERROR_STOP=on ${database_name} < ${dumpfile}
```

### アトミックなリストア

```sh
psql -1 ${database_name} < ${dumpfile}
```

もしくは

```sh
psql --single-transaction ${database_name} < ${dumpfile}
```

### パイプで繋いで別サーバへダンプを直接リストア

`pg_dump`は標準出力に吐き出されるため、それを利用してパイプで繋いでリストアすることができる

```sh
pg_dump -h ${host1} ${database_name1} | psql -h ${host2} ${database_name2}
```

## クラスタ全体のダンプ

`pg_dump`は単一のデータベースのダンプだが、`pg_dumpall`はデータベースクラスタの全内容のダンプを行う

```sh
pg_dumpall > ${dumpfile}
```

## クラスタ全体のリストア

```sh
psql -f ${dumpfile} postgres
```
