# Websockets-With-Beyondcode
this project use Laravel 10

## Create a new laravel project 
#### Via Composer
_composer create-project laravel/laravel example-app_

#### With global variable
_laravel new example-app_

#### Run the server
_php artisan serve_


## Setting up laravel websockets by BeyondCode
#### Install Laravel Websockets
_composer require beyondcode/laravel-websockets_

#### Register the service provider (will be generate a new table migration)
_php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="migrations"_

#### Migrate the new table
_php artisan migrate_

#### Publish WebSockets Config file (config/websockets.php)
_php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="config"_

#### Install the PUSHER PHP SDK
_composer require pusher/pusher-php-server_


#### Change **BROADCAST_DRIVER** in **.env**
_BROADCAST_DRIVER=pusher_


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
#### Create pusher Channel https://pusher.com/
