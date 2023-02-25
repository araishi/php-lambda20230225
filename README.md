# php-lambda20230225
- fuelphpとbrefでaws lambdaに実装される環境構築
- php brefでlambdaに実装される
- 開発するにはfuelphpのcomposer.phar installが必要

```
// docker、カレントで
docker-compose up
```

```
// 初期設定、Dockerのphp-fpmコンテナの中で
php composer.phar install
```

```
// fuelphp、Dockerのphp-fpmコンテナの中で
cd web;
php composer.phar install
```
