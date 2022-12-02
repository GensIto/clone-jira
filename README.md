# jira clone(作成中)

jira のクローン副業で使う機会がありタスク管理にめっちゃいいと感じた。
タスクの内容を書く時に notion の感じだったら書きやすいと感じてガッチャンして使いやすいの作ってみたい！！！と思って頑張って作ってみる。

# branch 分け方参考

```
feature/{作業者名前}_{日付}_{説明}
  新規機能の開発用。

release/{バージョン名}
  次回リリースの準備用。

hotfix/{日付}_{説明 or Issue番号}
  現在の製品バージョンのバグフィックス用。
```

# アーキテクト予定

### front

- react
- mui
- axios
- zustand

### back

- fast api

# 参考

- [app](https://www.udemy.com/course/jirareact-hookstypescript-django-rest-apijira/learn/lecture/34295734?start=0#overview)
- [fast api 構築](https://zenn.dev/sh0nk/books/537bb028709ab9/viewer/96a124)
- [fast api jwt docs](https://fastapi.tiangolo.com/ja/tutorial/security/oauth2-jwt/)

# fast api docker 手順

- docker-compose build
- ```
  docker-compose run \
    --entrypoint "poetry init \
      --name demo-app \
      --dependency fastapi \
      --dependency uvicorn[standard]" \
    demo-app
  ```
- docker-compose run --entrypoint "poetry install" demo-app --no-root <- [エラー対処](https://github.com/python-poetry/poetry/issues/1227)
- docker-compose build --no-cache
- docker-compose up <- app 立ち上げ
- ## mysql クライアントのインストール
- docker-compose exec demo-app poetry add sqlalchemy aiomysql
- docker-compose exec db mysql demo <- ターミナルで起動
  - SHOW TABLES;
  - SHOW DESCRIBE tasks;
  - DESCRIBE dones;
