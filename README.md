# Laravel-Sanctum
Laravel 8 Snactum Authentication

# Laravel-Sanctum
Laravel 8 Snactum Authentication
<<<<<<< HEAD
Installation

Please check the official laravel installation guide for server requirements before you start.
https://laravel.com/docs/8.x/installation

Install all the dependencies using composer
 composer install

Install Postman Agent

 
 Copy the example env file and make the required configuration changes in the .env file
 .env.example .env
 
 Create Model for Product:
 php artisan make:model Product --migration
 
 Run This Command
 php artisan migrate
 
 After Run:
 php artisan make:controller Product controller--api
 
 Edit PostController file
 
 
 After that edit files , and run this command
 composer require laravel/sanctum
 
 
 Next, you should publish the Sanctum configuration and migration files using the vendor:publish Artisan command. The sanctum configuration file will be placed in your application's config directory:
 
 php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
 
 
 
 Finally, you should run your database migrations. Sanctum will create one database table in which to store API tokens:
 
 php artisan migrate
 
 
 Next, if you plan to utilize Sanctum to authenticate an SPA, you should add Sanctum's middleware to your api middleware group within your application's app/Http/Kernel.php file:
 
 'api' => [
     \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
     'throttle:api',
     \Illuminate\Routing\Middleware\SubstituteBindings::class,
 ],
 
 
 
 To begin issuing tokens for users, your User model should use the Laravel\Sanctum\HasApiTokens trait:
 
 use Laravel\Sanctum\HasApiTokens;
 
 class User extends Authenticatable
 {
     use HasApiTokens, HasFactory, Notifiable;
 }
 
 
 In Postman Agent in headers 
 Accept= the Keys
 value = application/json
 In Body 
 Put data
as key and value

Run this Command
php artisan make:controller AuthController

Start the local development server
php artisan serve

You can now access the server at http://localhost:8000




