# role

PostgreSQLは、ロールという概念を使用してデータベースへの接続承認を管理する。 ロールはデータベース全体で共通。

## create

シェルからロールの作成を行うことができる。

```sh
createuser ${name}
```

SQLで作成もできる。

```sql
CREATE ROLE ${name}
```

## drop

シェルからロールの削除を行うことができる。

```sh
dropuser ${name}
```

SQLで削除もできる。

```sql
DROP ROLE ${name}
```

## role一覧

```sql
psql -U $(whoami) -d postgres -c "SELECT rolname FROM pg_roles";
```
