# database

## 一覧

```sh
psql -U $(whoami) -d postgres -c "select * from pg_database;"
```

もしくは

```sh
psql -U $(whoami) -d postgres
\l
```

## 作成

クエリ

```sql
CREATE DATABASE ${database_name}
```

シェルから作成

```sh
psql -U $(whoami) -d postgres -c "create database ${database_name}"
```

もしくは

```sh
createdb ${database_name}
```

## 削除

クエリ

```sql
DROP DATABASE ${database_name}
```

シェルから削除

```sh
psql -U $(whoami) -d postgres -c "drop database ${database_name}"
```

もしくは

```sh
dropdb ${database_name}
```
