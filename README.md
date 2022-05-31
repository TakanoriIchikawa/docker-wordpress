## Docker Wordpress環境構築

1. Gitクローン
```
$ git clone https://github.com/TakanoriIchikawa/docker-wordpress.git プロジェクト名
```

2. 環境変数の設定
```
cd プロジェクト名
cp .env.example .env

// .envを編集（以下、設定例）
WEB_PORT=80
DB_NAME=wordpress
DB_USER=wordpress
DB_PORT=3306
DB_PASSWORD=wordpress
DB_ROOT_PASSWORD=root
```

3. Dockerイメージのビルド
```
$ docker compose build --no-cache
```

4. Dockerコンテナの起動
```
$ docker compose up -d
```

5. Wordpressのインストール
```
$ docker compose exec app sh /tmp/setup.sh
```
http://localhost:{.envのWEB_PORT}

6. Wordpressの初期設定




8. リモートリポジトリの変更
```
$ git remote set-url origin プロジェクトのリモートリポジトリURL
```