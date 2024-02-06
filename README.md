# Websockets-With-Beyondcode
Project requirment:
- Laravel 10
- Pusher
- Websockets
- MySQL
- NPM
- Composer
- Code Editor (Vscode, etc)

## Create a new laravel project 
#### Via Composer
```php 
composer create-project laravel/laravel example-app
```

#### With global variable
```php
laravel new example-app
```

#### Run the server
```php
php artisan serve
```

## Setting up laravel websockets by BeyondCode
#### Install Laravel Websockets
```php
composer require beyondcode/laravel-websockets
```

#### Register the service provider (will be generate a new table migration)
```php
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="migrations"
```

#### Migrate the new table
```php
php artisan migrate
```

#### Publish WebSockets Config file (config/websockets.php)
```php
php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="config"
```
#### Install the PUSHER PHP SDK
```php
composer require pusher/pusher-php-server
```

#### Change **BROADCAST_DRIVER** in **.env**
```php
BROADCAST_DRIVER=pusher
```


#### In `config/broadcasting.php`, modify the `pusher` configuration as follows:

```php
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
```

## Setting up PUSHER
#### Create pusher Channel https://pusher.com/ until you get **App Key**
```php
app_id = "your_app_id"
key = "your_key"
secret = "your_secret"
cluster = "your_cluster"
```

#### And modify the .env
```php
PUSHER_APP_ID=your_app_id
PUSHER_APP_KEY=your_key
PUSHER_APP_SECRET=your_secret
PUSHER_HOST=localhost
PUSHER_PORT=6001
PUSHER_SCHEME=http
PUSHER_APP_CLUSTER=your_cluster
```
