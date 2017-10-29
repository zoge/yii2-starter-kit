# Testing

To run tests:
1. Start containers:
```
docker-compose up -d
```
2. Create database:
```
docker-compose exec db mysql -uroot -proot -e 'CREATE DATABASE yii2_test_db'
```
3. Setup application:
```
docker-compose exec app php tests/codeception/bin/yii app/setup --interactive=0
```
4. Start web server (do not close bash session):
```
docker-compose exec app php -S localhost:8080
```
5. Run tests in separate window:
```
docker-compose exec app vendor/bin/codecept run
```
