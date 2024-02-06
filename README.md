# Websockets-With-Beyondcode
this project use Laravel 10

## Create a new laravel project 
#### Via Composer
composer create-project laravel/laravel example-app


#### With global variable
laravel new example-app


#### Run the server
php artisan serve



## Setting up laravel websockets by BeyondCode
#### Install Laravel Websockets
composer require beyondcode/laravel-websockets


#### Register the service provider (will be generate a new table migration)
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="migrations"


#### Migrate the new table
php artisan migrate


#### Publish WebSockets Config file (config/websockets.php)
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="config"


#### Install the PUSHER PHP SDK
composer require pusher/pusher-php-server


#### Change **BROADCAST_DRIVER** in **.env**
BROADCAST_DRIVER=pusher


#### In config/broadcasting.php change into this
'pusher' => [
  'driver' => 'pusher',
  'key' => env('PUSHER_APP_KEY'),
  'secret' => env('PUSHER_APP_SECRET'),
  'app_id' => env('PUSHER_APP_ID'),
  'options' => [
    'cluster' => env('PUSHER_APP_CLUSTER'),
    'encrypted' => true,
    'host' => '127.0.0.1',
    'port' => 6001,
    'scheme' => 'http'
  ],
],


## Setting up PUSHER

