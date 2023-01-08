## Docker Wordpress環境構築

#### 1. Gitクローン
```
git clone https://github.com/TakanoriIchikawa/docker-wordpress.git プロジェクト名
```

#### 2. 環境変数の設定
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

#### 3. Dockerイメージのビルド
```
docker compose build --no-cache
```

#### 4. Dockerコンテナの起動
```
docker compose up -d
```

#### 5. Wordpressのインストール
```
docker compose exec app sh /tmp/setup.sh
```

http://localhost:{.envのWEB_PORT} にアクセスすると下記画面が表示

![docker-wordpress1](https://user-images.githubusercontent.com/53390190/171085509-98770624-bce1-4f15-bedc-01f85f4aecb9.png)

#### 6. Wordpressの初期設定（DB）
- データベース名、ユーザー名、パスワードは`.env`の値を入力
- データベースのホスト名は`db`（dockerのコンテナ名）と入力
- テーブルの接頭辞は任意（デフォルトはwp_）

![docker-wordpress2](https://user-images.githubusercontent.com/53390190/171085529-4e1f2094-4ade-4f11-8de2-2dc79483f011.png)

#### 7. Wordpressの初期設定（プロジェクト）

#### 8. プラグインのインストール


#### 9 . リモートリポジトリの変更
```
git remote set-url origin プロジェクトのリモートリポジトリURL
```

#### 10 . リモートリポジトリへプッシュ
```
git push origin master
```