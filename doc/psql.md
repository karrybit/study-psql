# psql

## 一般オプション

### 接続先データベースの指定

```sh
psql [-d|--dbname] ${db_name}
```

### データベース一覧

```sh
psql -l
```

### SQL実行

#### シングルコマンド

```sh
psql [-c|--command] ${query}
```

#### ファイル読み込んで実行

```sh
psql [-f|--file] ${sql_file_path}
```

## 入出力オプション

### 実行SQLを標準出力する

```sh
$ psql -U postgres -d some_db -f sample.sql
columnA | columnB
--------+--------
 A      | B
(1行)
```

```sh
$ psql -U postgres -d some_db -f sample.sql [-a|--echo-all]
--this is comment
SELECT columnA, columnB FROM some_table;
columnA | columnB
--------+--------
 A      | B
(1行)
```

### 実行したクエリの結果を任意のファイルに吐き出す

```sh
psql -U postgres -d some_db -f sample.sql [-o|--output] result.txt
```

## 出力形式オプション

### CSV

```sh
psql -U postgres -d some_db -f sample.sql --csv
```

### HTML

```sh
psql -U postgres -d some_db -f sample.sql [-H|--html]
```

## 接続オプション

### ホスト名

デフォルトは`"local socket"`

```sh
psql [-h|--host] ${host_name}
```

### ポート

デフォルトは`5432`

```sh
psql [-p|--port] ${port_number}
```

### ユーザ名

デフォルトは`"$(whoami)"`

```sh
psql [-U|--username] ${user_name}
```

### パスワード

#### パスワード指定

```sh
psql [-W|--password]
```

#### パスワードを指定しない

```sh
psql [-w|--no-passowrd]
```
