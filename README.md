# Websockets-With-Beyondcode
this project use Laravel 10

## Create a new laravel project 
### Via Composer
composer create-project laravel/laravel example-app


### With global variable
laravel new example-app


### Run the server
php artisan serve



## Setting up laravel websockets by BeyondCode
### Install Laravel Websockets
composer require beyondcode/laravel-websockets


### Register the service provider (will be generate a new table migration)
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="migrations"


### Migrate the new table
php artisan migrate


### Publish WebSockets Config file (config/websockets.php)
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="config"


### Install the PUSHER PHP SDK
composer require pusher/pusher-php-server


### Change **BROADCAST_DRIVER** in **.env**
BROADCAST_DRIVER=pusher
