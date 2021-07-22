# pg_ctl

`pg_ctl`とは`postgres`のラッパー

## init

`initdb`と同じ

```sh
pg_ctl init[db] [-D DATADIR] [-s] [-o OPTIONS]
```

## start

起動コマンド

```sh
pg_ctl start [-D DATADIR] [-l FILENAME] [-W] [-t SECS] [-s] [-o OPTIONS] [-p PATH] [-c]
```

## stop

停止コマンド

```sh
pg_ctl stop [-D DATADIR] [-m SHUTDOWN-MODE] [-W] [-t SECS] [-s]
```

## restart

再起動コマンド

```sh
pg_ctl restart [-D DATADIR] [-m SHUTDOWN-MODE] [-W] [-t SECS] [-s] [-o OPTIONS] [-c]
```

## reload

再読み込みコマンド

```sh
pg_ctl [-D DATADIR] [-s]
```

### status

起動状態確認コマンド

```sh
pg_ctl status [-D DATADIR]
```

# オプション

## `-s`

エラーメッセージのみ出力し、他の情報は表示しない

## `-w`, `--wait`

起動・停止処理が完了するのを待機する

デフォルトで有効

## `-W`, `--no-wait`

起動・停止処理が完了するのを待機しない

## `-c`, `--core-files`

クラッシュ時にcoreファイルを生成する

## `-l`, `--log`

指定のファイルにログを書き込む

## `-o`, `--options`

`postgres`に渡すオプションを指定する
