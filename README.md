# leaving-match-backend

## development
main ブランチ<br>
esa 参照

## 環境構築

1. leaving-match-backend をクローンする

2. .env.local ファイルをディレクトリ直下に配置する

3. 
```
docker compose up -d --build
```

4. test.http から動作確認

5. DB の中身を確認したいときは docker exec -it leaving-match_db mysql -u root -p で {MYSQL_ROOT_PASSWORD} を入力
USE {MYSQL_DATABASE}; 
SELECT * FROM {テーブル名};

6. 一時的にコンテナを停止したい場合は 
```
docker stop {コンテナ名}
```
<br>再開する場合は 
```
docker start {コンテナ名}
```


## ディレクトリ構成

```
leaving-match-backend
├─ app/
│  ├─ lib/        # 共通設定
│  ├─ router/     # コントローラー呼び出し
│  ├─ controller/ # API呼び出し時に機能する部分
│  ├─ service/    # 実際のテーブル操作部分
│  ├─ model/      # 扱う型の設定
│  ├─ go.mod
│  ├─ go.sum
│  └─ main.go
├─ db/            # テーブル設定
├─ docker/        # Dockerfile
├─ .env.local     # 環境変数（引き継ぎ）
├─ compose.yml    # コンテナ設定
└─ README.md
```

- 各ファイルの詳細はesa (https://kjlb.esa.io/posts/9449) を確認