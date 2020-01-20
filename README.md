

cd ~/laravel-docker

docker run --rm -v $(pwd):/app composer install

for ubuntu
sudo chown -R $USER:$USER ~/laravel-docker

for mac
sudo chown -R {username}:{username} ~/laravel-docker

cp .env.example .env

docker-compose up -d

docker-compose exec app php artisan key:generate

docker-compose exec app php artisan config:cache

docker-compose exec app php artisan migrate