# Testing

To run tests:
1. Start containers:
```
docker-compose up -d
```
2. Create database:
```
docker-compose exec db mysql -uroot -proot -e "CREATE DATABASE \`yii2_test_db\` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci" 
```
3. Setup application:
```
docker-compose exec app php tests/bin/yii app/setup --interactive=0
```
5. Start web server for acceptance tests (do not close bash session):
```
docker-compose exec app php -S localhost:8080
```
5. Run tests in separate window:
```
docker-compose exec app vendor/bin/codecept run
```
