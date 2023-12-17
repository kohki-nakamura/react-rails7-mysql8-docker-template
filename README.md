# Rails7,React,MySQL8,Dockerの雛形
https://qiita.com/zakino123/items/5f883112de45a27256b2

## 準備
```
git clone git@github.com:kohki-nakamura/react-ruby-mysql-docker-practiceApp.git;
cd react-ruby-mysql-docker-practiceApp;

cp .env.sample .env;
docker-compose build;
docker-compose run backend bundle install;
docker-compose run --rm frontend sh -c "cd app && npm install";

docker-compose run backend rails db:create;
docker-compose run backend rails db:migrate;
docker-compose run backend rails db:seed;

docker-compose up -d
```

access to http://localhost:3000
access to http://localhost:3001

# 環境構築Tips
## credentials.yml.enc 不要
https://qiita.com/hiroky_814/items/e8d38ba96852f636181e

## localhostがhttpsにリダイレクトされる
Chromeのみで発生
```
2023-12-17 12:07:03 +0900 HTTP parse error, malformed request: #<Puma::HttpParserError: Invalid HTTP format, parsing fails. Are you trying to open an SSL connection to a non-SSL Puma?>
```
https://stackoverflow.com/questions/25277457/google-chrome-redirecting-localhost-to-https/28586593#28586593

1. chromeで開発者ツールを開く
2. リロードボタンを右クリック
3. 一番下の「キャッシュの削除とハード再読み込み」を選択
4. リロード