# vue-docker-template

docker-composeを利用してvue.jsの開発環境を構築するためのテンプレートです。

mac環境を想定しているのでlinuxなどその他環境では微調整が必要となります。

## 環境の起動

①コンテナの起動
```bash
docker-compose up -d
```

②起動確認
```bash
docker-compose ps
       Name                    Command              State           Ports
----------------------------------------------------------------------------------
template-workspace   docker-entrypoint.sh /bin/sh   Up      0.0.0.0:8080->8080/tcp
```
＃workspaceコンテナが起動(State=Up)していたらOK

### その他コマンドの実行について

コンテナ上でコマンドを実行する場合下記のように実行する
```
# docker-compose exec app [コマンド]
docker-compose exec app echo test
```

## vueのプロジェクト作成

```bash
# プロジェクト作成
docker-compose exec workspace vue create .
```
※README.md(このファイル)が上書きされます！！！

```bash
# 実行
docker-compose exec workspace yarn serve
```

