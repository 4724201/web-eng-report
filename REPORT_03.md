# 
第3回Webエンジニアリング演習　レポート
## 
学籍番号
4724201
## 
イメージとコンテナの違い
イメージは、コンテナを作成するために必要なアプリケーションや設定などをまとめたものである。一方、コンテナはイメージをもとに作成され、実際にアプリケーションを実行する環境である。Dockerでは、イメージからコンテナを作成して実行することで、アプリケーションを動作させることができる。
## Dockerfileの各行の役割
FROM：ベースとなるイメージを指定する。
COPY：ホスト側のファイルをコンテナ内にコピーする。
## 動作確認
@4724201 ➜ /workspaces/web-eng-docker (main) $ docker compose ps NAME IMAGE COMMAND SERVICE CREATED STATUS PORTS web-eng-docker-web-1 web-eng-docker-web "/docker-entrypoint.…" web 33 seconds ago Up 31 seconds 0.0.0.0:8080->80/tcp, [::]:8080->80/tcp