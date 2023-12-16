# Rails7,React,MySQL8,Dockerの雛形
https://qiita.com/zakino123/items/5f883112de45a27256b2

### credentials.yml.enc 不要
https://qiita.com/hiroky_814/items/e8d38ba96852f636181e

### 準備
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
```