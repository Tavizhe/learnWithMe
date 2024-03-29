# Laravel 8 & 9

## some experience

do env like bellow:

```php
APP_NAME=Real_Estate
APP_ENV=local
APP_KEY=base64:X+E/JpxTGsruglxe/0ZEXvTFsLGukcfpnyf0vWyUfms=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=mellkg_done
DB_USERNAME=mellkg_done
DB_PASSWORD=msaCh8OirM=$

BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

MEMCACHED_HOST=127.0.0.1

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=mt1

VITE_APP_NAME="${APP_NAME}"
VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
VITE_PUSHER_HOST="${PUSHER_HOST}"
VITE_PUSHER_PORT="${PUSHER_PORT}"
VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"

```

do your index like bellow and place it in public_html:

```php

<?php

use Illuminate\Contracts\Http\Kernel;
use Illuminate\Http\Request;

define('LARAVEL_START', microtime(true));

/*
|--------------------------------------------------------------------------
| Check If The Application Is Under Maintenance
|--------------------------------------------------------------------------
|
| If the application is in maintenance / demo mode via the "down" command
| we will load this file so that any pre-rendered content can be shown
| instead of starting the framework, which could cause an exception.
|
*/

if (file_exists($maintenance = __DIR__.'/storage/framework/maintenance.php')) {
    require $maintenance;
}

/*
|--------------------------------------------------------------------------
| Register The Auto Loader
|--------------------------------------------------------------------------
|
| Composer provides a convenient, automatically generated class loader for
| this application. We just need to utilize it! We'll simply require it
| into the script here so we don't need to manually load our classes.
|
*/

require __DIR__.'/vendor/autoload.php';

/*
|--------------------------------------------------------------------------
| Run The Application
|--------------------------------------------------------------------------
|
| Once we have the application, we can handle the incoming request using
| the application's HTTP kernel. Then, we will send the response back
| to this client's browser, allowing them to enjoy our application.
|
*/

$app = require_once __DIR__.'/bootstrap/app.php';

$kernel = $app->make(Kernel::class);

$response = $kernel->handle(
    $request = Request::capture()
)->send();

$kernel->terminate($request, $response);
```

do add .htaccess file like this in public_html:

```php
<IfModule mod_rewrite.c>
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]
</IfModule>
```

do not add node_mudules in zip files.
do not use persian charecters as file names!

## Pre Requirements

1. Xampp (version is depended on what laravel version do we need - **3.3.0 for laravel 9**)
2. php (by installing xampp it will be installed - **8.2.4 for laravel 9**)
3. nodejs (simply download and install it from it's site - **18.16.1 for laravel 9**)
4. composer (simply download and install it from it's site - **2.5.8 for laravel 9**)
5. 7-Zip and php-zip (for installing laravel project)

To install the php-zip extension for PHP on Windows, you can follow these steps:

Locate the php.ini file used by your PHP installation. Open the php.ini file in a text editor. Search for the line ;extension=zip (without the semicolon at the beginning). Remove the semicolon to uncomment the line and enable the zip extension. Save the php.ini file. Restart your web server (e.g., Apache or Nginx) or the PHP service if you're using PHP in a standalone mode.

---
To start first install Xampp application then add php directory to your path in environment variables. Later check `php -v` in command line (CMD) to see the right version of php.

Next is time to install Composer. First download `Composer-Setup.exe` from [Composer Site](https://getcomposer.org/download/) then simply install it. After check composer version with Command Line with following command `composer -V`.

## Creating New Laravel Project Using Composer

To create a new project using Composer run in Command Line:

```shell
cd C:\xampp\htdocs
composer create-project laravel/laravel="*" Project_Name
composer create-project laravel/laravel="9.*" Laravel_Project_9
# don't forget to add your exact laravel version instead of "*" 
# or it will install latest related version instead.
```

In order to use localhost to check your made website use following command:

```shell
php artisan serve
```

by using this command in Command line or Power Shell (It's better to be used vscode terminal), an Host with an IP will be shown like `http://127.0.0.1:8000`. by clicking on it you will be directed to desired laravel website.

## Laravel Root Directory Structure

| Directory | Description                                                                                                                                    |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| app       | The app directory holds the base code for your Laravel application.                                                                            |
| bootstrap | The bootstrap directory contains all the bootstrapping scripts used for your application.                                                      |
| config    | The config directory holds all your project configuration files (.config).                                                                     |
| database  | The database directory contains your database and migration files.                                                                                           |
| public    | The public directory helps start your Laravel project and maintains other necessary files such as JavaScript, CSS, and images of your project. |
| resources | The resources directory holds all the Sass files, language (localization) files, and templates (if any).                                       |
| routes    | The routes directory contains all your definition files for routing, such as console.php, api.php, channels.php, etc.                          |
| storage   | The storage directory holds your session files, cache, compiled templates, and miscellaneous files generated by the framework.                 |
| test      | The test directory holds all your test cases.                                                                                                  |
| vendor    | The vendor directory holds all composer dependency files.                                                                                      |

- You will need the `.env` file in the project's root directory to configure your application's environment. You can configure the database (and email) for your application using the `config/database.php` file of your project.

### App Directory Structure

| Directory     | Description                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Console       | The Console directory contains all your project artisan commands.                                                                                                                                                          |
| Events        | The Events directory holds event files that your laravel application may pop up. Events are used for sending messages or signals to other parts of the laravel project that any action has taken place within the project. |
| Exceptions    | The Exceptions directory holds your laravel project's exception handling files, which handle all the exceptions thrown by your Laravel project.                                                                            |
| Http          | The Http directory holds different filters, requests, and controllers.                                                                                                                                                     |
| Jobs          | The Jobs directory holds all lineup jobs in this directory. But it does not get created initially; instead, you need to type and run this artisan command:`make:job`                                                       |
| Listeners     | The Listeners directory holds all your project's handler classes used for receiving and handling events.                                                                                                                   |
| Mail          | The Main directory holds all the emails sent through your Laravel project, and this directory needs to be created using the command: `make:mail`                                                                           |
| Notifications | The Notifications directory contains all your transactional notifications sent through your Laravel project, and this directory needs to be created using the command: `make:notification`                                 |
| Policies      | The policies directory holds different policies for your laravel project.                                                                                                                                                  |
| Providers     | The Providers directory is used to contain different service providers.                                                                                                                                                    |
| Rules         | The Rules directory holds all the different objects related to custom validation rules, and this directory needs to be created using the command: `make:rule`                                                              |

### Artisan

Artisan is a command-line interface (CLI) included with the Laravel PHP framework that provides several helpful commands for speeding up development workflows. use `php artisan list`
to see all commands.

> we can make our own commands and add them in artisan. first make scaffolding `php artisan make:command SendEmails` then implement your php codes in it.

## Routing

Routes are defined inside the Route folder in `api.php` and `web.php` files. in `api.php` we use to just use to return `JSON` in `API` formats.
Routing in Laravel allows you to route all your application requests to their appropriate controller and views. The application's route file gets defined in the `app/Http/routes.php` file. The general routing in Laravel for each of the possible requests looks something like this:

![Routes in laravel](Laravel%20Images%20Reference/1.png)

```php
<!-- http://localhost/ --> 
Route:: get ('/', function () {
   return view('Home');
})->('Home.index'); // this is how you can name your routes so they make sense by reading it

/*
'/' is the uri (means anything that comes after your root domain) 
and func is a controller that can be a method in our class or anonymous function! 
*/

<!-- Another Example -->
// Defining a route that only renders a Blade template
Route::view('/Home'); // Without parameters
Route::view('/Home', ['data' => 'value']); // With parameters
```

> Use `use Illuminate\Support\Facades\Route` in order to use routes in project.

- Roots that just returns HTML and don't require any parameters or any extra work, you can simplify like bellow:

```php
<!-- Before -->
Route::get('/', function() {
    return view('home,index', [])
})=>name('home.index');

<!-- After -->
Route::view('/', 'home.index')=>name('home.index');
```

- `php artisan route:list` Command shows all of routes in our project.

### The routing happens in three different steps

1. First of all, you have to create and run the root URL of your project.
2. The URL you run needs to be matched exactly with your method defined in the root.php file.
3. The function invokes the template files. It then calls the `view()` function with the file name located in `resources/views/`.

It is good to know that routes have 6 functionalities like :`get()`,`post()`,`put()`, `delete()`, `patch()` and `option()`. As in order:

- When you want to fetch some of the content, then you have to use the `get()` method.
- When you want to insert some data into the database, then you have to use the `post()` method.
- When you want to update some data into the database, then you have to use `put()` method.
- when you want to delete data, then you can use `delete()` method.
- When you want to update one single field in the database, then you have to use `patch()` method.

![Route-functionalities](Laravel%20Images%20Reference/2.png)

#### Route Parameters

Laravel provides two ways of capturing the passed parameter:

- Required parameter (can be used for ids, postNumbers, ...): You sometimes had to work with a segment(s) of your project's URL (Uniform Resource Locator). Route parameters are encapsulated within {} (curly-braces) with alphabets inside. Let us take an example where you have to capture the customer's ID or employee from the generated URL. For Example:

```php
Route::get("posts/{id}", function ($id) {
  echo "Blog post " . $id;
});
```

- Optional Parameter (can be useful for time when name parameter is not provided) - Many parameters do not remain present within the URL, but the developers had to use them. So such parameters get indicated by a "?" (question mark sign) following the parameter's name. For Example:

```php
Route::get("emp/{name?}", function ($name = "Guest") {
  echo $name;
});
Route::get("/recent-posts/{days_ago?}", function ($daysAgo = 20) {
  // it is necessary to have argument in optional parameters.
  return "Posts from " . $daysAgo . " days ago";
});
```

> Note - always name your routes! It is always wise to name our blade templates (views) as routes connected to them! Happy Coding.

In last Example the required parameter have to be a number, we can specify in route so it always be a number like Example bellow:

```php
Route :: get ('posts/{id}', function ($id) {
    echo 'Blog post '.$id;
})-> where([
    'id' => [0-9]+ // by using regular expressions. + means it should have a length of at least 1.
])->name('posts.show'); // don't forget to name your routes :)
```

## Views and Layouts

A view is a file containing a mix of PHP code, HTML markup, and Blade templates. These templates contain placeholders for dynamic content and are used to define the structure and layout of a web page. By default, Laravel comes with a set of predefined views, such as `welcome.blade.php` and `errors/404.blade.php`.

> Note: Views are stored in the `resources/views`.

### Creating a View

To create a view in Laravel, follow these steps:

1. Navigate to the `resources/views` directory in your Laravel project.
2. Create a new file with a `fileName.blade.php` extension. This extension tells Laravel to use the Blade template engine to parse the view.
3. In the view file, add the HTML, PHP, and/or Blade templates that define the structure and layout of the page. You can use placeholders for dynamic content, such as or.

For Example:

```php
<!-- resources/views/greeting.blade.php -->

<h1>Hello, {{$name}}!</h1> // $name is a placeholder for dynamic content
```

### Rendering a View

**View helper functions** can be used to display a view in a Laravel application. This function takes the name of the view as its first argument and an array of data as its second argument. For Example:

```php
// in a Laravel controller
return view("greeting", ["name" => "Alex"]);

// in routes/greeting.php
Route::get("/greeting", function () {
  return view("greeting", ["name" => "Alex"]);
});
```

As an alternative to passing a complete array of data to the view helper function, you may use the with method to add individual pieces of data to the view.

```php
return view('greeting')
            ->with('name', 'Victoria')
            ->with('occupation', 'Astronaut');
// or
<!-- web.php -->
Route::get('/posts/{id}', function($id){
    $posts = [
        1 => [
            'title' => 'Intro To laravel',
            'content' => 'This is a short intro to laravel'
        ],
        2 => [
            'title' => 'Intro to PHP',
            'content' => 'This is a short intro to PHP'
        ]
    ];
    abort_if(!isset($posts[$id]), 404); // this is a laravel helper function - generate an error (here is 404 not found) when this condition (inputted post id is not available) is met.
    return view('posts.show', ['post' => $posts[$id]]);
    });
<!-- Resources/views/posts/show.blade.php explained more in ### Layouts Usage -->
@extends('layouts.app')

@section('title', $post['title'])

@section('content')
<h1>{{ $post['title'] }}</h1>
<p>{{ $post['content'] }}</p>
@endsection
```

> "Dot" notation may be used to reference nested views. For example, if your view is stored at `resources/views/admin/profile.blade.php`, you may return it from one of your application's routes / controllers like so: `return view('admin.profile', $data);`
> Note: View directory names should not contain the `.` character.

### Sharing Data With All Views

Occasionally, you may need to share data with all views that are rendered by your application. You may do so using the `View` facade's `share` method in `App\Providers\AppServiceProvider`.

```php
namespace App\Providers;

use Illuminate\Support\Facades\View;

class AppServiceProvider extends ServiceProvider
{
  /**
   * Register any application services.
   */
  public function register(): void
  {
    // ...
  }

  /**
   * Bootstrap any application services.
   */
  public function boot(): void
  {
    View::share("key", "value");
  }
}
```

### Layouts Usage

while coding a site there is always a chance that we are using the same html or any frontend code over and over, layouts simplify this method using directives like `@yield`. Directives always start with an at sign like `@` followed by the directive name and optionally they can have arguments.

- Yield Directive - The Yields Directive takes the name of the section it should render in the layout file, Using `@extends(`layout_file_name`)` and `@section('content')` ends with `@endsection`. Now, inside these two section directives, you can put all the HTML and content that should be rendered from.
  > Note: Layouts are stored in the `resources/layouts`. For Example:

```php
<!-- in resources/views/layouts/app.blade.php -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laravel App - @yield('title')</title>
</head>
<body>
    <div>
        @yield('content')
    </div>
</body>
</html>

<!-- in resources/views/index.blade.php or any other place we want to use `app.blade.php` as our layout -->
@extends('layouts.app')

@section('title', 'Home Page')

@section('content')
<h1>Hello World</h1>
@endsection
```

### Conditional Rendering

Sometimes our templates need some logic, for example, only if certain condition is true, you want to display some content, like is user logged in?

```php
Route::get('/posts/{id}', function($id){
    $post = [
        1 => [
            'title' => 'Intro To laravel',
            'content' => `This is a short intro to laravel`,
            'is_new' => true
        ],
        2 => [
            'title' => 'Intro to PHP',
            'content' => 'This is a short intro to PHP',
            'is_new' => false
        ]
    ];
    abort_if(!isset($post[$id]), 404);
    return view('posts.show', ['post' => $post[$id]]);
    });

<!-- show.blade.php to render content based on a condition, we will use the if directive. -->

@extends('layouts.app')

@section('title', $post['title'])

@section('content')
@if($post['is_new'])
<div>A new blog post, using if</div>
@elseif(!$post['is_new'])
<div> Blog post is old</div>
@endif
<h1>{{ $post['title'] }}</h1>
<p>{{ $post['content'] }}</p>
@endsection
```

- alternatively, to use Conditional Rendering using right Directive called `@unless()` that condition has to be false and no other alternatives, then `endunless()`.

```php
<!-- in this example we use last question answered in `@unless()` condition. -->
@unless ($post['is_new'])
    <p>There is newer post using unless Directive</p>
@endunless
```

- we can also add comments using `isset()` Directive like bellow:

```php
@extends('layouts.app')

@section('title', $post['title'])

@section('content')

@unless ($post['is_new'])
    <p>There is newer post using unless Directive</p>
@endunless

@isset($post['has_comments'])
    <div>this post has some comments. using `isset()` directives</div>
@endisset
```

> there are more Directives that uses further laravel knowledge that we will add later.

#### loops

```php
@for ($i = 0; $i < 10; $i++)
    The current value is {{ $i }}
@endfor

@foreach ($users as $user)
    <p>This is user {{ $user->id }}</p>
@endforeach

@forelse ($users as $user)
    <li>{{ $user->name }}</li>
@empty
    <p>No users</p>
@endforelse

@while (true)
    <p>I'm looping forever.</p>
@endwhile
```

| Property           | Description                                            |
| ------------------ | ------------------------------------------------------ |
| `$loop->index`     | The index of the current loop iteration (starts at 0). |
| `$loop->iteration` | The current loop iteration (starts at 1).              |
| `$loop->remaining` | The iterations remaining in the loop.                  |
| `$loop->count`     | The total number of items in the array being iterated. |
| `$loop->first`     | Whether this is the first iteration through the loop.  |
| `$loop->last`      | Whether this is the last iteration through the loop.   |
| `$loop->even`      | Whether this is an even iteration through the loop.    |
| `$loop->odd`       | Whether this is an odd iteration through the loop.     |
| `$loop->depth`     | The nesting level of the current loop.                 |
| `$loop->parent`    | When in a nested loop, the parent's loop variable.     |

### Partial(sub view) Templates

Blade's @include directive allows you to include a Blade view from within another view, also helps you extract parts of your templates into smaller chunks, which is easier to manage in long term.

> All variables that are available to the parent view will be made available to the included view

## Requests & Response

Laravel has ways to build our proper HTTP response with all its features like response codes, setting cookies and setting response headers. Check Example bellow:

```php
Route::get("/fun/responses", function () use ($posts) {
  return response($posts, 201)
    ->header("Content-Type", "application/json")
    ->cookie("MY_COOKIE", "Fard", 3600);
});
```

the response function will create a new response object. This object has methods like header or cookie.

- The response function accepts the Three parameters, all optional, first is the content to return, Second, the status code and third is an array of response headers.

So posts will be a content and 201 in our response code. The Header method sets the response header like contents type, telling the browser what to expect from their content, whether it is HTML or JSON. Cookie sets the browser cookies. Cookies are useful to keep users specific data on the browser side. we can render blade views while adding headers cookies and changing the status code.

### Redirect Responses

Sometimes the route needs to do something and then go to another page. For example:

```php
Route::get("/fun/redirect", function () {
  return redirect("/contact");
});
```

The `back` helper function will redirect to the last address. It's useful with one time actions like for input storying. For example:

```php
Route::get("/fun/back", function () {
  return back();
});
```

Sometimes you need to return only the data from the response without any HTML and in such cases most of the time you wanted in the Json format. For example:

```php
Route::get("/fun/json", function () use ($posts) {
  return response()->json($posts);
});
```

It's easy to force the browser to download a file, using the download method of the response object.

```php
Route::get("/fun/download", function () {
  return response()->download(
    public_path("/chingcho Chang.jpg"),
    "ChingChoChang.jpg"
  );
});
```

### Group Routes

Group Routes can have the same prefix, the same roots, name prefix or the same middleware applied.

```php
Route::prefix("/fun")
  ->name("fun.")
  ->group(function () use ($posts) {
    // Testing Requests & Response
    Route::get("responses", function () use ($posts) {
      return response($posts, 201)
        ->header("Content-Type", "application/json")
        ->cookie("MY_COOKIE", "Fard", 3600);
    })->name("responses");
    Route::get("redirect", function () {
      return redirect("/contact");
    })->name("redirect");
    Route::get("back", function () {
      return back();
    })->name("back");
    Route::get("named-route", function () {
      return redirect()->route("posts.show", ["id" => 1]);
    })->name("named-route");
    Route::get("away", function () {
      return redirect()->away("https://google.com");
    })->name("away");
    Route::get("json", function () use ($posts) {
      return response()->json($posts);
    })->name("json");
    Route::get("download", function () {
      return response()->download(
        public_path("/chingcho Chang.jpg"),
        "ChingChoChang.jpg"
      );
    })->name("download");
  });
```

### Request Input

Apart from the root parameters, we can accept input as the Query parameters data sent through an HTML form or request body interface and `Json` format. This Input is accessible using the request object methods. There are two ways

- using the request function `request()`.
- by type printing argument with the request `function(Request $request)`.
- later we can change logo by navigating to `resources/views/components/application-logo.blade.php`.

```php
<img src="{{ asset('logo/logoName.png') }}" width="100px">
```

> Make sure to use `use Illuminate\Http\Request;`

#### `request()->all()` Method

The `all()` method will give us access to all the inputs (as an array), but not the actual route parameters.
for example:

let's Try adding some query parameters like page and limit, often used as results`127.0.0.1:8000/posts?limit=10&page=5`. In order to see the results we use `dd()` function.

- `dd()` can be used to dump data.

```php
Route::get("/posts", function () use ($posts) {
  dd(request()->all());
  return view("posts.index", ["posts" => $posts]);
});
```

we can also use `dd(request()->input('page', 1));` to allows us to specify a default value to ask the second parameter. there is a special query method if you want to get the value only from a query parameter `dd((int)request()->query('page', 1));`. works the same as the input method does. input will look for the names in all the possible input. Sources like Query Parameters, a form or Jason and query.

### Middleware

Middleware is a mechanism that filter requests going through your application like a guard.

![Request flow with middleware](Laravel%20Images%20Reference/3.png)

An example BEFORE middleware

```php
namespace App\Http\Middleware;
use Closure;

class BeforeMiddleware
{
  public function handle($request, Closure $next)
  {
    // Do something here before the request is handled by Controller/Closure...

    // Calling $next with $request parameter
    return $next($request);
  }
}
```

An example AFTER middleware

```php
namespace App\Http\Middleware;
use Closure;

class AfterMiddleware
{
  public function handle($request, Closure $next)
  {
    // Calling $next with $request parameter
    $response = $next($request);

    // Do something here after the request is handled by Controller/Closure
    return $response;
  }
}
```

Middleware should call the passed `Closure` `$next` with the `$request` parameter to allow further processing, or `throw` an `Exception` or do a redirect to stop further processing of the `Request`.

Middleware examples:

- Authentication (verifying if user is authenticated)
- CSRF protection
- CORS middleware

![Middleware](Laravel%20Images%20Reference/4.png)

One of the Route object methods is middleware. we can apply to a group of routes or a specific route. in `kernel.php` file there is `$routeMiddleware` and inside it defines a thing called Elias, Now using this, you can easily apply middleware using the middleware method and passing those. Like below:

```php
Route::get("/posts/{id}", function ($id) use ($posts) {
  abort_if(!isset($posts[$id]), 404);

  return view("posts.show", ["post" => $posts[$id]]);
})
  ->name("posts.show")
  ->middleware("auth"); //the user needs to be authenticated to visit this route.
```

#### Creating a middleware

we can use `php artisan make:middleware middlewareName` for like ensureTokenIsValid. Next we need to add it in `app\Http\Kernel.php` at `$routeMiddleware` like `'ensureTokenIsValid' => \App\Http\Middleware\ensureTokenIsValid::class`. when we want to use this middleware in a route use this code:

```php
Route::get('/about', 'index')->name('about.page')->middleware('ensureTokenIsValid');
```

### laravel Breeze middleware

breeze is laravel default authentication system. in order to install it use `composer require laravel/breeze --dev` next run following code

```shell
php artisan breeze:install

npm install
npm run dev
php artisan migrate #remember to make a database before using this code
```

- now we can add `{{ Auth::user()->name }}` in view that we want.
- it will be useful to add to users model `implements MustVerifyEmail` in `use Illuminate\Contracts\Auth\MustVerifyEmail;` class for email verification like in users model. this will force user to verify email first before using his/her account.

> selfNote 1: as i'm doing my own examples, for adding like username to users table of breeze, do `php artisan migrate:rollback` then do add username in users table and its model also in controller and migrate once again.
> selfNote 2: we can make email for our site via mailtrap.io. after registration go to inbox settings and in SMTP sector change integration to laravel+7. then copy and paste given info in related values in `.env` file. (Don't forget thats its all in local not internet). So how to add authentication in my pages? well as default add `,'verified'` next to `'auth'` in `routes/web.php` in places that router needs to do authentication first like dashboard in my case.
>
## Controllers

Controllers are an alternative to Closures for defining the application logic

![Controllers](Laravel%20Images%20Reference/5.png)

- To Generating a new Controller `php artisan make:controller folder/controllerName`.

> Controllers are stored inside the `app/Http/Controllers` folder.

An example controller class:

```php
<!-- In Controller -->
namespace App\Http\Controllers;
use App\Http\Controllers\Controller;

class HomeController extends Controller
{
  public function index()
  {
    return view("home");
  }

  public function contact()
  {
    return view("contact");
  }
}

<!-- In Routes -->
Route::get("/", "HomeController@home");
// or
Route::get('/', [HomeController::class, 'home'])->name('home.index');

Route::get("/contact", "HomeController@contact");
//or
Route::get('/contact', [HomeController::class, 'contact'])->name('home.contact');
```

We don't have to specify the full controller namespace in `web.php`. It's enough to specify everything after `App\Http\Controllers`. RouteServiceProvider will is responsible for prepending the `App\Http\Controllers` namespace to controller names in routes.

### Single Action Controllers

For controllers that handle just a single action:

- `php artisan make:controller HomeSingleController --invokable`

```php
<!-- In Controller -->
namespace App\Http\Controllers;
use App\Http\Controllers\Controller;

class HomeSingleController extends Controller
{
  public function __invoke()
  {
    return view("home");
  }
}

<!-- In Routes -->
Route::get("home", "HomeSingleController");
// or
Route::get('/single', HomeSingleController::class);

```

The `__invoke` is a magic PHP method that allows the object to be called like a function, eg.

```php
$controller = new HomeSingleController();
$controller();
```

![Controller](Laravel%20Images%20Reference/5.png)

### Laravel 9 version

```php
/* in routes/web.php */
<!-- Laravel 8 -->
Route::get('/home', [DemoController::class, 'index'])->name(`index`);
Route::get('/contract', [DemoController::class, 'ContactMethod'])->name(`Contacts`);

<!-- Laravel 9 -->
Route::controller(DemoController::class)->group(function () {
    Route::get('/home', 'Index')->name(`index.page`);
    Route::get('/contact', 'ContactMethod')->name(`Contacts.page`);
});

/* in resources\views\welcome.blade.php */
<a href="{{ route('index.page') }}"> Makes a link to home page (index) </a>
<a href="{{ route('contacts.page') }}"> Makes a link to contact page </a>
# there is a url version that is not recommended.
```

#### Crude

code bellow will add All possible crude actions for us.

```bash
php artisan make:controller PostsController --resource
```

it is easy to define the routs for this resource controller.

```php
Route::resource("/posts", PostsController::class)->only(["index"], ["show"]); //or except
// only helps us to use only some of crude actions.
```

later we need to implement two methods, index and show.

```php
public function index()
{
  return view('posts.index', ['posts' => $this->posts]);
}

public function show($id)
{
    abort_if(!isset($this->posts[$id]), 404);
    return view('posts.show', ['post' => $this->posts[$id]]);
}
```

## Configuration & Environment

Laravel, configuration files are stored inside the config folder that's for all default.

![Configuration](Laravel%20Images%20Reference/6.png)

in order to see if database is connected to our project is to run `php artisan migrate`.

### Database

Let's take a bird's eye overview of the tools available in the Laravel framework to make it easy to work with databases.

![Database](Laravel%20Images%20Reference/7.png)

Database Migration's is the tool to change the database schema. every time you need to create a new table or add new columns to an existing table, you should create a new migration file.

![Database](Laravel%20Images%20Reference/8.png)

Schema and blueprint schema has methods to create, change and delete database tables. Blueprint is used to create or modify or delete individual table columns.

![ORM Models](Laravel%20Images%20Reference/9.png)

Tinker is a command line tool that lets you play around with parts of your Laravel up, it's useful to quickly check out how things work and will be handy to learn how models work.

#### Laravel Tinker

Laravel Tinker allows you to interact with a database without creating the routes. Laravel tinker is used with a `php artisan` to create the objects or modify the data. Tinker is a command tool that works with a php artisan. A tinker plays around the database means that it allows you to create the objects, insert the data, etc.

To enter the Tinker environment, run `php artisan tinker` in terminal.

##### Creating data

We can create the records in database tables by using the command-line tool that inserts the data directly in the database table.

```bash
php artisan tinker
$post=App\Post::create(['title'=>'Fard','body'=>'Fard is a software developer']);
```

We can view the inserted data in a phpMyAdmin. We can also use another way to insert the data by creating an object.

- First, we create the object.

```bash
php artisan tinker
$post= App\Post
=> App/Post {#3019}
$post->title="Alireza"
=> "Alireza"
$post->body="Fard"
=> "Fard"
$post->save();
$post
=> App/Post {#3019
  title="Alireza",
  body="Fard",
  Updated_at: "..."
  Created_at: "..."
  id: 1}
```

##### Finding Record

We can retrieve the records from the database in three ways:

- The first way is to use the find() method.

```bash
$post=App\Post::find(1)
=> App/Post {#3019
  title="Alireza",
  body="Fard",
  Updated_at: "..."
  Created_at: "..."
  Deleted_at: "null"
  id: 1}
```

- The second way is to use the constraint, i.e., where clause.

```bash
$post=App\Post::where(1)->first()
=> App/Post {#3019
  title="Alireza",
  body="Fard",
  Updated_at: "..."
  Created_at: "..."
  Deleted_at: "null"
  id: 1
  }
# first() method is used to retrieve the single record.
$post=App\Post::where('id','>',0)->get()
=> App/Post {#3019
  title="Alireza",
  body="Fard",
  Updated_at: "..."
  Created_at: "..."
  Deleted_at: "null"
  id: 1
  }
#get() method is used when an array of records is retrieved.
```

- The third way is to use whereId().

```bash
$post=App\Post::whereId(1)->first()
=> App/Post {#3019
  title="Alireza",
  body="Fard",
  Updated_at: "..."
  Created_at: "..."
  Deleted_at: "null"
  id: 1
  }
```

##### Updating data

- First, we find out the object which we want to update.

```bash
$post=App\Post::find(1)
=> App/Post {#3019
  title="Alireza",
  body="Fard",
  Updated_at: "..."
  Created_at: "..."
  Deleted_at: "null"
  id: 1}
```

- Now we update the values of two columns, title, and body.

```bash
$post->title="Alireza-1"
=> "Alireza-1"
$post->title="Fard-1"
=> "Fard-1"
$post->save()
```

##### Deleting data

first, we apply the delete() on the $post object.

```bash
$post->delete()
=> true
```

The above screen shows that the delete() method returns true value, which means that the record has been deleted.

> To delete the record permanently. `$post->onlyTrashed()` then `$post->forceDelete()`.

##### Using The Query Builder

```bash
User::factory()->count(5)->create();
# This will create and save five user models with randomly generated data using Laravel Model Factory.
User::where('id;','>=', 2)->orderBy('id', 'desc')->get();
# shows model by desc id
```
<!-- ## Introduction to Database: Query Builder documentation from laravel.com

The Laravel query builder protects your application against SQL injection attacks.

## Retrieving data in DB

### Retrieving All Rows From A Table

You may use the `table` method provided by the `DB` facade to begin a query. The `table` method returns a fluent query builder instance for the given table, allowing you to chain more constraints onto the query and then finally retrieve the results of the query using the `get` method:

```php
namespace App\Http\Controllers;

use App\Http\Controllers\Controller;
use Illuminate\Support\Facades\DB;
use Illuminate\View\View;

class UserController extends Controller
{
  /**
   * Show a list of all of the application's users.
   */
  public function index(): View
  {
    $users = DB::table("users")->get();

    return view("user.index", ["users" => $users]);
  }
  /* You may access each column's value by accessing the column as a property of the object */
  $users = DB::table("users")->get();
  foreach ($users as $user) {
    echo $user->name;
  }
}
```

#### Retrieving A Single Row / Column From A Table

If you just need to retrieve a single row from a database table, you may use the `DB` facade's `first` method.

```php
$user = DB::table("users") // Selecting the "users" table from the database
  ->where("name", "John") // Filtering the results to only include records with the name "John"
  ->first(); // Retrieving the first matching record
  /* or */
  ->value("email"); // Retrieving the value of the "email" column from the query result

return $user->email; // Returning the email property of the retrieved user
```

To retrieve a single row by its `id` column value, use the `find` method:

```php
$user = DB::table("users")->find(3); // Retrieving user data from the "users" table where the id is 3 and assigning it to the variable $user

```

#### Retrieving A List Of Column Values

If you would like to retrieve an `Illuminate\Support\Collection` instance containing the values of a single column, you may use the `pluck` method. In this example, we'll retrieve a collection of user titles:

```php
use Illuminate\Support\Facades\DB;

$titles = DB::table("users")->pluck("title"); // Retrieving all values of the "title" column from the "users" table and assigning them to the variable $titles
/* or */
$titles = DB::table("users")->pluck("title", "name"); // Retrieving values from the "title" column, using the "name" column as the key

foreach ($titles as $title) {
  echo $title;
}
```

### Chunking Results

let's retrieve the entire `users` table in chunks of 100 records at a time:

```php
use Illuminate\Support\Collection;
use Illuminate\Support\Facades\DB;

DB::table("users") // Selecting the "users" table
  ->orderBy("id") // Sorting the results in ascending order of the "id" column
  ->chunk(100, function (Collection $users) { // Retrieving the users in chunks of 100 and processing each chunk using a callback function
    foreach ($users as $user) { // Iterating over each user in the current chunk
      // ...
      // You may stop further chunks from being processed by returning `false` from the closure:
      return false;
    }
  });

```

If you are updating database records while chunking results, your chunk results could change in **unexpected ways**. If you plan to update the retrieved records while chunking, it is always best to use the `chunkById` method instead. This method will automatically paginate the results based on the record's primary key:

```php
// Select the "users" table from the database
DB::table("users")
  // Filter the records where the "active" column is false
  ->where("active", false)
  // Process the records in chunks of 100
  ->chunkById(100, function (Collection $users) {
    // Loop through each user record within the chunk
    foreach ($users as $user) {
      // Update the "active" column to true for the current user
      DB::table("users")
        ->where("id", $user->id)
        ->update(["active" => true]);
    }
  });

```

> **Warning**
> When updating or deleting records inside the chunk callback, any changes to the primary key or foreign keys could affect the chunk query. This could potentially result in records not being included in the chunked results.

### Streaming Results Lazily

The `lazy` method works similarly to [the `chunk` method](#chunking-results) in the sense that it executes the query in chunks. However, instead of passing each chunk into a callback, the `lazy()` method returns a [`LazyCollection`](/docs/{{version}}/collections#lazy-collections), which lets you interact with the results as a single stream:

```php
use Illuminate\Support\Facades\DB;

DB::table("users") // Selecting the "users" table
  ->orderBy("id") // Sorting the results in ascending order of the "id" column
  ->lazy() // Enable lazy loading Lazy loading is a technique where records are loaded into memory one at a time as they are needed
  ->each(function (object $user) {
    // Process each user object...
    
    // ...
  });

```

Once again, if you plan to update the retrieved records while iterating over them, it is best to use the `lazyById` or `lazyByIdDesc` methods instead. These methods will automatically paginate the results based on the record's primary key:

```php
DB::table("users")
  ->where("active", false)
  ->lazyById()
  ->each(function (object $user) {
    DB::table("users")
      ->where("id", $user->id)
      ->update(["active" => true]);
  });
```

> **Warning**
> When updating or deleting records while iterating over them, any changes to the primary key or foreign keys could affect the chunk query. This could potentially result in records not being included in the results.

### Aggregates

The query builder also provides a variety of methods for retrieving aggregate values like `count`, `max`, `min`, `avg`, and `sum`. You may call any of these methods after constructing your query:

```php
use Illuminate\Support\Facades\DB;

// Retrieve the total count of records in the "users" table
$users = DB::table("users")->count();

// Retrieve the maximum value of the "price" column from the "orders" table
$price = DB::table("orders")->max("price");

```

Of course, you may combine these methods with other clauses to fine-tune how your aggregate value is calculated:

```php
$price = DB::table("orders")
  ->where("finalized", 1)
  ->avg("price");
```

#### Determining If Records Exist

Instead of using the `count` method to determine if any records exist that match your query's constraints, you may use the `exists` and `doesntExist` methods:

```php
// Check if there are any records in the "orders" table where the "finalized" column is equal to 1
if (
  DB::table("orders")
    ->where("finalized", 1)
    ->exists()
) {
  // Code block to be executed if the condition is true
  // ...
}

// Check if there are no records in the "orders" table where the "finalized" column is equal to 1
if (
  DB::table("orders")
    ->where("finalized", 1)
    ->doesntExist()
) {
  // Code block to be executed if the condition is true
  // ...
}

```

## Select Statements in DB

### Specifying A Select Clause

You may not always want to select all columns from a database table. Using the `select` method, you can specify a custom "select" clause for the query:

```php
use Illuminate\Support\Facades\DB;

// Retrieve data from the "users" table in the database
// Select the "name" column and rename it as "user_email" for the result set
$users = DB::table("users")
  ->select("name", "email as user_email")
  ->get();
  /* or */
  ->distinct() //The `distinct` method allows you to force the query to return distinct (specific) results
  ->get();
```

If you already have a query builder instance and you wish to add a column to its existing select clause, you may use the `addSelect` method:

```php
// Create a new query builder instance and select the "name" column from the "users" table
$query = DB::table("users")->select("name");

// Extend the existing query to also select the "age" column from the "users" table
$users = $query->addSelect("age")->get();

```

## Raw Expressions in DB

Sometimes you may need to insert an arbitrary string into a query. To create a raw string expression, you may use the `raw` method provided by the `DB` facade:

```php
// Retrieve a query builder instance for the "users" table
$users = DB::table("users")

  // Select the count of all rows as "user_count" and the "status" column
  ->select(DB::raw("count(*) as user_count, status"))

  // Add a where clause to filter out rows with a "status" value of 1
  ->where("status", "<>", 1)

  // Group the results by the "status" column
  ->groupBy("status")

  // Execute the query and fetch the results into the "$users" variable
  ->get();

```

> **Warning**
> Raw statements will be injected into the query as strings, so you should be extremely careful to avoid creating SQL injection vulnerabilities.

### Raw Methods

Instead of using the `DB::raw` method, you may also use the following methods to insert a raw expression into various parts of your query. **Remember, Laravel can not guarantee that any query using raw expressions is protected against SQL injection vulnerabilities.**

#### `selectRaw`

The `selectRaw` method can be used in place of `addSelect(DB::raw(/* ... */))`. This method accepts an optional array of bindings as its second argument:

```php
# Assigning the result of a database query to the variable "orders"
$orders = DB::table("orders")

# Selecting a calculated column in the query using selectRaw() method
# The calculated column is the product of "price" and a tax rate of 1.0825
# The result is aliased as "price_with_tax" 
->selectRaw("price * ? as price_with_tax", [1.0825])

# Executing the query and retrieving the results
->get();
```

#### `whereRaw / orWhereRaw`

The `whereRaw` and `orWhereRaw` methods can be used to inject a raw "where" clause into your query. These methods accept an optional array of bindings as their second argument:

```php
# Assigning the result of a database query to the variable "orders"
$orders = DB::table("orders")

# Adding a condition to the query using whereRaw() method
# The condition is based on the value of the "state" column:
## If the state is "TX", compare the "price" column with the provided value (200)
## Otherwise, compare the "price" column with 100
->whereRaw('price > IF(state = "TX", ?, 100)', [200])

# Executing the query and retrieving the results
->get();
```

#### `havingRaw / orHavingRaw`

The `havingRaw` and `orHavingRaw` methods may be used to provide a raw string as the value of the "having" clause. These methods accept an optional array of bindings as their second argument:

```php
# Assigning the result of a database query to the variable "orders"
$orders = DB::table("orders")

# Selecting the "department" column and calculating the sum of prices as "total_sales"
->select("department", DB::raw("SUM(price) as total_sales"))

# Grouping the results by the "department" column
->groupBy("department")

# Adding a condition to the grouped results using the havingRaw() method
# The condition checks if the sum of prices is greater than 2500
->havingRaw("SUM(price) > ?", [2500])

# Executing the query and retrieving the results
->get();
```

#### `orderByRaw`

The `orderByRaw` method may be used to provide a raw string as the value of the "order by" clause:

```php
# Assigning the result of a database query to the variable "orders"
$orders = DB::table("orders")

# Sorting the results based on the difference between the "updated_at" and "created_at" columns in descending order
->orderByRaw("updated_at - created_at DESC")

# Executing the query and retrieving the results
->get();
```

### `groupByRaw`

The `groupByRaw` method may be used to provide a raw string as the value of the `group by` clause:

```php
# Assigning the result of a database query to the variable "orders"
$orders = DB::table("orders")

# Specifying the columns "city" and "state" to be selected from the table
->select("city", "state")

# Grouping the results based on the combination of "city" and "state" columns
->groupByRaw("city, state")

# Executing the query and retrieving the results
->get();
```

## Joins in DB

### Inner Join Clause

To perform a basic "inner join", you may use the `join` method on a query builder instance. The first argument passed to the `join` method is the name of the table you need to join to, while the remaining arguments specify the column constraints for the join. You may even join multiple tables in a single query:

```php
use Illuminate\Support\Facades\DB;

# Assigning the result of a database query to the variable "users"
$users = DB::table("users")

# Joining the "contacts" table using the "id" column from "users" table and "user_id" column from "contacts" table
->join("contacts", "users.id", "=", "contacts.user_id")

# Joining the "orders" table using the "id" column from "users" table and "user_id" column from "orders" table
->join("orders", "users.id", "=", "orders.user_id")

# Selecting all columns from the "users" table, along with the "phone" column from the "contacts" table and the "price" column from the "orders" table
->select("users.*", "contacts.phone", "orders.price")

# leftJoin & rightJoin

# Performing a left join between the "users" table and the "posts" table using the "id" column from "users" table and "user_id" column from "posts" table
->leftJoin("posts", "users.id", "=", "posts.user_id")

# Performing a right join between the "users" table and the "posts" table using the "id" column from "users" table and "user_id" column from "posts" table
->rightJoin("posts", "users.id", "=", "posts.user_id")

# cartesian (dekarty) crossJoin

# Performing a cross join between the "sizes" table and the "colors" table
->crossJoin("colors")

# Executing the query and retrieving the results
->get();
```

#### Advanced Join Clauses

You may also specify more advanced join clauses. The closure will receive a `Illuminate\Database\Query\JoinClause` instance which allows you to specify constraints on the "join" clause:

```php
# Selecting records from the "users" table and joining it with the "contacts" table
DB::table("users")

# Defining the join operation using a closure function that takes a JoinClause object as an argument
->join("contacts", function (JoinClause $join) {

  # Specifying the join condition, linking the "id" column of "users" table to the "user_id" column of the "contacts" table
  $join->on("users.id", "=", "contacts.user_id")

  # Adding an additional join condition using the "orOn" method. The specific condition is not provided here.
  ->orOn(/* ... */);
})

# Executing the query and retrieving the results
->get();

```

If you would like to use a "where" clause on your joins, you may use the `where` and `orWhere` methods provided by the `JoinClause` instance. Instead of comparing two columns, these methods will compare the column against a value:

```php
# Selecting records from the "users" table and joining it with the "contacts" table
DB::table("users")

# Defining the join operation using a closure function that takes a JoinClause object as an argument
->join("contacts", function (JoinClause $join) {

  # Specifying the join condition, linking the "id" column of "users" table to the "user_id" column of the "contacts" table
  $join->on("users.id", "=", "contacts.user_id")

  # Adding a WHERE condition to the join, filtering the records based on the "user_id" column of the "contacts" table being greater than 5
  ->where("contacts.user_id", ">", 5);
})

# Executing the query and retrieving the results
->get();
```

#### Subquery Joins

You may use the `joinSub`, `leftJoinSub`, and `rightJoinSub` methods to join a query to a subquery. Each of these methods receives three arguments: the subquery, its table alias, and a closure that defines the related columns. In this example, we will retrieve a collection of users where each user record also contains the `created_at` timestamp of the user's most recently published blog post:

```php
# Selecting the latest posts with their creation date and user ID from the "posts" table
$latestPosts = DB::table("posts")
  ->select("user_id", DB::raw("MAX(created_at) as last_post_created_at"))

  # Adding a WHERE condition to filter only published posts
  ->where("is_published", true)

  # Grouping the posts by user ID
  ->groupBy("user_id");

# Joining the "users" table with the subquery result from $latestPosts using a closure function
$users = DB::table("users")
  ->joinSub($latestPosts, "latest_posts", function (JoinClause $join) {

    # Specifying the join condition, linking the "id" column of "users" table to the "user_id" column of the subquery result
    $join->on("users.id", "=", "latest_posts.user_id");
  })
  ->get();
```

## Unions in DB

The query builder also provides a convenient method to "union" two or more queries together. For example, you may create an initial query and use the `union` method to union it with more queries:

```php
use Illuminate\Support\Facades\DB;

# Selecting all rows from the "users" table where the "first_name" column is NULL
$first = DB::table("users")->whereNull("first_name");

# Selecting all rows from the "users" table where the "last_name" column is NULL
$users = DB::table("users")

  # Adding a WHERE condition to filter only rows where the "last_name" column is NULL
  ->whereNull("last_name")
  
  # Combining the previous query results with the $first query using UNION
  ->union($first)
  
  # Getting the final result set
  ->get();

```

## Basic Where Clauses in DB

### Where Clauses (rule)

You may use the query builder's `where` method to add "where" clauses to the query. The most basic call to the `where` method requires three arguments. The first argument is the name of the column. The second argument is an operator, which can be any of the database's supported operators. The third argument is the value to compare against the column's value.

For example, the following query retrieves users where the value of the `votes` column is equal to `100` and the value of the `age` column is greater than `35`:

```php
$users = DB::table("users")
  ->where("votes", "=", 100)
  ->where("age", ">", 35)
  ->get();
```

You may also pass an array of conditions to the `where` function. Each element of the array should be an array containing the three arguments typically passed to the `where` method:

```php
# Selecting all rows from the "users" table with certain conditions
$users = DB::table("users")

  # Adding a WHERE condition to filter rows based on multiple conditions
  ->where([
    ["status", "=", "1"],     # Filtering rows where the "status" column is equal to 1
    ["subscribed", "<>", "1"]  # Filtering rows where the "subscribed" column is not equal to 1
  ])
  
  # Getting the final result set
  ->get();

```

> **Warning**
> PDO does not support binding column names. Therefore, you should never allow user input to dictate the column names referenced by your queries, including "order by" columns.

### Or Where Clauses

When chaining together calls to the query builder's `where` method, the "where" clauses will be joined together using the `and` operator. However, you may use the `orWhere` method to join a clause to the query using the `or` operator. The `orWhere` method accepts the same arguments as the `where` method:

```php
// Retrieve the "users" table from the database using the DB facade
$users = DB::table("users")

  // Filter the result to include only users with "votes" count greater than 100
  ->where("votes", ">", 100)

  // Alternatively, include users with the name "John"
  ->orWhere("name", "John")

  // Get all the matching records
  ->get();

```

If you need to group an "or" condition within parentheses, you may pass a closure as the first argument to the `orWhere` method:

```php
// Retrieve the "users" table from the database using the DB facade
$users = DB::table("users")

  // Filter the result to include only users with "votes" count greater than 100
  ->where("votes", ">", 100)

  // Alternatively, include users with both the name "Abigail" and 
  // a vote count greater than 50 by using a nested query
  ->orWhere(function (Builder $query) {
    $query->where("name", "Abigail")->where("votes", ">", 50);
  })

  // Get all the matching records
  ->get();

```

The example above will produce the following SQL:

```sql
select * from users where votes > 100 or (name = 'Abigail' and votes > 50)
```

> **Warning**
> You should always group `orWhere` calls in order to avoid unexpected behavior when global scopes are applied.

### Where Not Clauses

The `whereNot` and `orWhereNot` methods may be used to negate a given group of query constraints. For example, the following query excludes products that are on clearance or which have a price that is less than ten:

```php
$products = DB::table("products")
  ->whereNot(function (Builder $query) {
    $query->where("clearance", true)->orWhere("price", "<", 10);
  })
  ->get();
```

### JSON Where Clauses

Laravel also supports querying JSON column types on databases that provide support for JSON column types. Currently, this includes MySQL 5.7+, PostgreSQL, SQL Server 2016, and SQLite 3.39.0. To query a JSON column, use the `->` operator:

```php
// Query the "users" table from the database
$users = DB::table("users")
  // Filter the users based on a condition
  ->where("preferences->dining->meal", "salad")
  // Retrieve the results of the query
  ->get();

```

You may use `whereJsonContains` to query JSON arrays. This feature is not supported by SQLite database versions less than 3.38.0:

```php
// Query the "users" table from the database
$users = DB::table("users")
  // Filter the users based on a condition using whereJsonContains method
  ->whereJsonContains("options->languages", "en")
  /* or */
  ->whereJsonContains("options->languages", ["en", "de"]) //in the MySQL or PostgreSQL databases
  // Retrieve the results of the query
  ->get();
```

You may use `whereJsonLength` method to query JSON arrays by their length:

```php
$users = DB::table("users")
  ->whereJsonLength("options->languages", 0)
  ->get();

$users = DB::table("users")
  ->whereJsonLength("options->languages", ">", 1)
  ->get();
```

### Additional Where Clauses

whereBetween / orWhereBetween

The `whereBetween` method verifies that a column's value is between two values:

```php
$users = DB::table("users")
  ->whereBetween("votes", [1, 100])
  ->get();
```

whereNotBetween / orWhereNotBetween

The `whereNotBetween` method verifies that a column's value lies outside of two values:

```php
$users = DB::table("users")
  ->whereNotBetween("votes", [1, 100])
  ->get();
```

whereBetweenColumns / whereNotBetweenColumns / orWhereBetweenColumns / orWhereNotBetweenColumns

The `whereBetweenColumns` method verifies that a column's value is between the two values of two columns in the same table row:

```php
// Query the "patients" table from the database
$patients = DB::table("patients")
  // Filter the patients based on a range between two columns
  ->whereBetweenColumns("weight", [
    "minimum_allowed_weight",
    "maximum_allowed_weight",
  ])
  // Retrieve the results of the query
  ->get();
```

The `whereNotBetweenColumns` method verifies that a column's value lies outside the two values of two columns in the same table row:

```php
$patients = DB::table("patients")
  ->whereNotBetweenColumns("weight", [
    "minimum_allowed_weight",
    "maximum_allowed_weight",
  ])
  ->get();
```

whereIn / whereNotIn / orWhereIn / orWhereNotIn

The `whereIn` method verifies that a given column's value is contained within the given array:

```php
$users = DB::table("users")
  ->whereIn("id", [1, 2, 3])
  ->get();
```

The `whereNotIn` method verifies that the given column's value is not contained in the given array:

```php
$users = DB::table("users")
  ->whereNotIn("id", [1, 2, 3])
  ->get();
```

You may also provide a query object as the `whereIn` method's second argument:

```php
$activeUsers = DB::table("users")
  ->select("id")
  ->where("is_active", 1);

$users = DB::table("comments")
  ->whereIn("user_id", $activeUsers)
  ->get();
```

The example above will produce the following SQL:

```sql
select * from comments where user_id in (
    select id
    from users
    where is_active = 1
)
```

> **Warning**
> If you are adding a large array of integer bindings to your query, the `whereIntegerInRaw` or `whereIntegerNotInRaw` methods may be used to greatly reduce your memory usage.

whereNull / whereNotNull / orWhereNull / orWhereNotNull

The `whereNull` method verifies that the value of the given column is `NULL`:

```php
$users = DB::table("users")
  ->whereNull("updated_at")
  ->get();
```

The `whereNotNull` method verifies that the column's value is not `NULL`:

```php
$users = DB::table("users")
  ->whereNotNull("updated_at")
  ->get();
```

whereDate / whereMonth / whereDay / whereYear / whereTime

The `whereDate` method may be used to compare a column's value against a date:

```php
$users = DB::table("users")
  ->whereDate("created_at", "2016-12-31")
  ->get();
```

The `whereMonth` method may be used to compare a column's value against a specific month:

```php
$users = DB::table("users")
  ->whereMonth("created_at", "12")
  ->get();
```

The `whereDay` method may be used to compare a column's value against a specific day of the month:

```php
$users = DB::table("users")
  ->whereDay("created_at", "31")
  ->get();
```

The `whereYear` method may be used to compare a column's value against a specific year:

```php
$users = DB::table("users")
  ->whereYear("created_at", "2016")
  ->get();
```

The `whereTime` method may be used to compare a column's value against a specific time:

```php
$users = DB::table("users")
  ->whereTime("created_at", "=", "11:20:45")
  ->get();
```

whereColumn / orWhereColumn

The `whereColumn` method may be used to verify that two columns are equal:

```php
$users = DB::table("users")
  ->whereColumn("first_name", "last_name")
  ->get();
```

You may also pass a comparison operator to the `whereColumn` method:

```php
$users = DB::table('users')
  ->whereColumn('updated_at', '>', 'created_at')
  ->get();
```

You may also pass an array of column comparisons to the `whereColumn` method. These conditions will be joined using the `and` operator:

```php
$users = DB::table('users')
  ->whereColumn('first_name', '=', 'last_name')
  ->where('updated_at', '>', 'created_at')
  ->get();
`
```

### Logical Grouping

Sometimes you may need to group several "where" clauses within parentheses in order to achieve your query's desired logical grouping. In fact, you should generally always group calls to the `orWhere` method in parentheses in order to avoid unexpected query behavior. To accomplish this, you may pass a closure to the `where` method:

```php
$users = DB::table('users')
    ->where('name', '=', 'John')
    ->where(function (Builder $query) {
        $query->where('votes', '>', 100)
            ->orWhere('title', '=', 'Admin');
    })
    ->get();
```

As you can see, passing a closure into the `where` method instructs the query builder to begin a constraint group. The closure will receive a query builder instance which you can use to set the constraints that should be contained within the parenthesis group. The example above will produce the following SQL:

```sql
select * from users where name = 'John' and (votes > 100 or title = 'Admin')
```

> **Warning**
> You should always group `orWhere` calls in order to avoid unexpected behavior when global scopes are applied.

## Ordering, Grouping, Limit & Offset in DB

### Ordering

#### The `orderBy` Method

The `orderBy` method allows you to sort the results of the query by a given column. The first argument accepted by the `orderBy` method should be the column you wish to sort by, while the second argument determines the direction of the sort and may be either `asc` or `desc`:

```php
$users = DB::table('users')
            ->orderBy('name', 'desc')
            ->get();
            
# To sort by multiple columns
$users = DB::table('users')
    ->orderByDesc('name')
    ->orderBy('email')
    ->get();

```

#### The `latest` & `oldest` Methods

The `latest` and `oldest` methods allow you to easily order results by date. By default, the result will be ordered by the table's `created_at` column. Or, you may pass the column name that you wish to sort by:

```php
$user = DB::table('users')
         ->orderBy('created_at', 'desc')
         ->first();

```

#### Random Ordering

The `inRandomOrder` method may be used to sort the query results randomly. For example, you may use this method to fetch a random user:

```php
$randomUser = DB::table('users')
                  ->inRandomOrder()
                  ->first();
```

#### Removing Existing Orderings

The `reorder` method removes all of the "order by" clauses that have previously been applied to the query:

```php
$query = DB::table('users')->orderBy('name');
$unorderedUsers = $query->reorder()->get();

#You may pass a column and direction when calling the `reorder` method in order to remove all existing "order by" for new one
$query = DB::table('users')->orderBy('name');
$usersOrderedByEmail = $query->reorder('email', 'desc')->get();
```

### Grouping

#### The `groupBy` & `having` Methods

As you might expect, the `groupBy` and `having` methods may be used to group the query results. The `having` method's signature is similar to that of the `where` method:

```php
$users = DB::table('users')
              ->groupBy('account_id', 'status')
              ->having('account_id', '>', 100)
              ->get();
              
#`havingBetween` method to filter the results within a given range:
$report = DB::table('orders')
                    ->selectRaw('count(id) as number_of_orders, customer_id')
                    ->groupBy('customer_id')
                    ->havingBetween('number_of_orders', [5, 15])
                    ->get();
```

### Limit & Offset

#### The `skip` & `take` Methods

You may use the `skip` and `take` methods to limit the number of results returned from the query or to skip a given number of results in the query:

```php
# Fetching data from the 'users' table in the database
$users = DB::table('users')

# Skipping the first 10 rows of data 
->skip(10)

# Taking only the next 5 rows of data 
->take(5)

# Retrieving the selected data from the table
->get();

# alternatives
$users = DB::table('users')
            ->offset(10)
            ->limit(5)
            ->get();
```

## Conditional Clauses in DB

Sometimes you may want certain query clauses to apply to a query based on another condition. For instance, you may only want to apply a `where` statement if a given input value is present on the incoming HTTP request. You may accomplish this using the `when` method:

```php
# Retrieving the value of the 'role' parameter from the HTTP request 
$role = $request->string('role');

# Fetching data from the 'users' table in the database 
$users = DB::table('users')

    # Conditionally applying a filter to the query based on the value of the 'role' parameter
    ->when($role, function ($query) use ($role) {
        #Filtering the query to only include rows with a matching 'role_id'
        $query->where('role_id', $role);
    })
    
    # Retrieving the selected data from the table
    ->get();

```

The `when` method only executes the given closure when the first argument is `true`. If the first argument is `false`, the closure will not be executed. So, in the example above, the closure given to the `when` method will only be invoked if the `role` field is present on the incoming request and evaluates to `true`.

You may pass another closure as the third argument to the `when` method. This closure will only execute if the first argument evaluates as `false`. To illustrate how this feature may be used, we will use it to configure the default ordering of a query:

```php
$sort_by_votes = $request->boolean('sort_by_votes');

$users = DB::table('users')
    ->when($sort_by_votes, function (Builder $query) {
        $query->orderBy('votes');
    }, function (Builder $query) {
        $query->orderBy('name');
    })
    ->get();
```

## Insert Statements DB

The query builder also provides an `insert` method that may be used to insert records into the database table. The `insert` method accepts an array of column names and values:

```php
DB::table('users')->insert([
        ['email' => 'picard@example.com', 'votes' => 0],
        ['email' => 'janeway@example.com', 'votes' => 0],
    ]);
```

The `insertOrIgnore` method will ignore **errors while inserting records into the database**. When using this method, you should be aware that duplicate record errors will be ignored and other types of errors may also be ignored depending on the database engine. For example, `insertOrIgnore` will bypass MySQL's strict mode:

```php
DB::table('users')->insertOrIgnore([
        ['id' => 1, 'email' => 'sisko@example.com'],
        ['id' => 2, 'email' => 'archer@example.com'],
    ]);
```

The `insertUsing` method will insert new records into the table while using a subquery to determine the data that should be inserted:

```php
DB::table('pruned_users')->insertUsing([
        'id', 'name', 'email', 'email_verified_at'
    ], DB::table('users')->select(
        'id', 'name', 'email', 'email_verified_at'
    )->where('updated_at', '<=', now()->subMonth()));
```

### Auto-Incrementing IDs

If the table has an auto-incrementing id, use the `insertGetId` method to insert a record and then retrieve the ID:

```php
$id = DB::table('users')->insertGetId(
        ['email' => 'john@example.com', 'votes' => 0]
    );
```

> **Warning**
> When using PostgreSQL the `insertGetId` method expects the auto-incrementing column to be named `id`. If you would like to retrieve the ID from a different "sequence", you may pass the column name as the second parameter to the `insertGetId` method.

### Upserts

The `upsert` method will insert records that do not exist and update the records that already exist with new values that you may specify. The method's first argument consists of the values to insert or update, while the second argument lists the column(s) that uniquely identify records within the associated table. The method's third and final argument is an array of columns that should be updated if a matching record already exists in the database:

```php
DB::table('flights')->upsert(
        [
            ['departure' => 'Oakland', 'destination' => 'San Diego', 'price' => 99],
            ['departure' => 'Chicago', 'destination' => 'New York', 'price' => 150]
        ],
        ['departure', 'destination'],
        ['price']
    );
```

In the example above, Laravel will attempt to insert two records. If a record already exists with the same `departure` and `destination` column values, Laravel will update that record's `price` column.

> **Warning**
> All databases except SQL Server require the columns in the second argument of the `upsert` method to have a "primary" or "unique" index. In addition, the MySQL database driver ignores the second argument of the `upsert` method and always uses the "primary" and "unique" indexes of the table to detect existing records.

## Update Statements in DB

In addition to inserting records into the database, the query builder can also update existing records using the `update` method. The `update` method, like the `insert` method, accepts an array of column and value pairs indicating the columns to be updated. The `update` method returns the number of affected rows. You may constrain the `update` query using `where` clauses:

```php
$affected = DB::table('users')
                  ->where('id', 1)
                  ->update(['votes' => 1]);
```

### Update Or Insert

Sometimes you may want to update an existing record in the database or create it if no matching record exists. In this scenario, the `updateOrInsert` method may be used. The `updateOrInsert` method accepts two arguments: an array of conditions by which to find the record, and an array of column and value pairs indicating the columns to be updated.

The `updateOrInsert` method will attempt to locate a matching database record using the first argument's column and value pairs. If the record exists, it will be updated with the values in the second argument. If the record can not be found, a new record will be inserted with the merged attributes of both arguments:

```php
DB::table('users')
        ->updateOrInsert(
            ['email' => 'john@example.com', 'name' => 'John'],
            ['votes' => '2']
        );
```

### Updating JSON Columns

When updating a JSON column, you should use `->` syntax to update the appropriate key in the JSON object. This operation is supported on MySQL 5.7+ and PostgreSQL 9.5+:

```php
$affected = DB::table('users')
                  ->where('id', 1)
                  ->update(['options->enabled' => true]);
```

### Increment & Decrement

The query builder also provides convenient methods for incrementing or decrementing the value of a given column. Both of these methods accept at least one argument: the column to modify. A second argument may be provided to specify the amount by which the column should be incremented or decremented:

```php
DB::table('users')->increment('votes');

DB::table('users')->increment('votes', 5);

DB::table('users')->decrement('votes');

DB::table('users')->decrement('votes', 5);
```

If needed, you may also specify additional columns to update during the increment or decrement operation:

```php
DB::table('users')->increment('votes', 1, ['name' => 'John']);

#  using the `incrementEach` and `decrementEach` methods:
DB::table('users')->incrementEach([
        'votes' => 5,
        'balance' => 100,
    ]);
```

## Delete Statements in DB

The query builder's `delete` method may be used to delete records from the table. The `delete` method returns the number of affected rows. You may constrain `delete` statements by adding "where" clauses before calling the `delete` method:

```php
$deleted = DB::table('users')->delete();

$deleted = DB::table('users')->where('votes', '>', 100)->delete();
```

If you wish to truncate an entire table, which will remove all records from the table and reset the auto-incrementing ID to zero, you may use the `truncate` method:

```php
DB::table('users')->truncate();
```

## Pessimistic Locking in DB

The query builder also includes a few functions to help you achieve "pessimistic locking" when executing your `select` statements. To execute a statement with a "shared lock", you may call the `sharedLock` method. A shared lock prevents the selected rows from being modified until your transaction is committed:

```php
# Fetching records from the 'users' table in the database
DB::table('users')
    # Adding a condition to only retrieve rows where the 'votes' column value is greater than 100
    ->where('votes', '>', 100)
    
    # Applying a shared lock to the query, preventing other processes from modifying the selected rows until the transaction completes
    ->sharedLock()
    
    # Executing the query and returning the results as a collection of records
    ->get();

```

Alternatively, you may use the `lockForUpdate` method. A "for update" lock prevents the selected records from being modified or from being selected with another shared lock:

```php
DB::table('users')
            ->where('votes', '>', 100)
            ->lockForUpdate()
            ->get();
```

## Debugging in DB

You may use the `dd` and `dump` methods while building a query to dump the current query bindings and SQL. The `dd` method will display the debug information and then stop executing the request. The `dump` method will display the debug information but allow the request to continue executing:

```php
DB::table('users')->where('votes', '>', 100)->dd();

DB::table('users')->where('votes', '>', 100)->dump();
```
-->

## Forms (Markup, CSRF, Validation, Errors, Flash Messages, Mass Assignment)

To add or modify data in your application, you need to accept user input using forms. Let's make a view called create for the posts.

```php
<!-- posts/create.blade.php -->
@extends('layouts.app')

@section('title', 'Create the post')

@section('content')
<form action="{{ route('posts.store') }}" method="POST">
    <div><input type="text" name="title"></div>
    <div><textarea name="content"></textarea></div>
    <div><input type="submit" value="Create" class="btn btn-primary btn-block"></div>
</form>
@endsection

<!-- web.php -->
Route::resource('/posts', PostsController::class)->only(['index', 'show', 'create', 'store']);

<!-- Controllers\PostsController.php -->
public function create()
{
  return view('posts.create');
}
```

### CSRF Protection and Validation

To protect your users from the most basic malicious actions from third parties, you need to Generate CRF Token for every form on your website. we can generate one with `@csrf` Directive. it is added hiddenly and stores it self in session.

> CSRF forms need to be added in `/Http/Middleware/VerifyCsrfToken.php`
> To check is code renderer has successfully reached any method, we can add `dd($request);` in it.
> in our last example lets add `@csrf`.

```php
<!-- posts/create.blade.php -->
@extends('layouts.app')

@section('title', 'Create the post')

@section('content')
<form action="{{ route('posts.store') }}" method="POST">
    @csrf
    <div><input type="text" name="title"></div>
    <div><textarea name="content"></textarea></div>
    <div><input type="submit" value="Create" class="btn btn-primary btn-block"></div>
</form>
@endsection
<!-- Http/controller/PostsController.php -->

public function store(Request $request)
    {
        dd($request);
    }
```

now if we check resources in chrome elements we see a hidden token like bellow:

![Hidden Token](Laravel%20Images%20Reference/10.png)

### how to save data & validating

First, to store the data, we need to create its model instance.

```bash
php artisan make:model BlogPosts -m #-m adds migration with the model.
```

after making the model we need to add tables in `up()` function at migration.

```php
<!-- database\migrations\*_create_blog_posts_table.php -->
public function up(): void
{
    Schema::create('blog_posts', function (Blueprint $table) {
      $table->id();
      $table->timestamps();
      $table->string('title');
      $table->text('content');
      });
}

<!-- Http\controller\PostsController.php -->
use App\Models\BlogPost;
  public function store(Request $request)
  {
    $request->validate([ //Validations
      'title'=>'bail|required|min:5|max:100',
      'content'=>'min:10',
    ]);
    $post = new BlogPost();
    $post->title = $request->input('title');
    $post->content = $request->input('content');
    $post->save();

    return redirect()->route('posts.show', ['post' => $post->id]);
  }

<!-- resources\views\Posts\create.blade.php -->
// Showing errors
@extends('layouts.app')

@section('title', 'Create the post')

@section('content')
<form action="{{ route('posts.store') }}" method="POST">
    @csrf
    {{-- @include('posts.partials.form') --}}
    <div><input type="text" name="title"></div>
    @error('title')
    <div>{{ $message }} تایتل خالیست </div>
    @enderror
    <div><textarea name="content"></textarea></div>
    @if($errors->any())
        <div>
            <ul>
                @foreach ($errors->all() as $error)
                    <li>{{ $error }}</li>
                @endforeach
            </ul>
        </div>
    @endif
    <div><input type="submit" value="Create" class="btn btn-primary btn-block"></div>
</form>
@endsection
```

### Form Request Classes

request classes are an alternative to way to putting validation rules directly inside the controller. when we are adding form request, change request to `RequestFormName`(in this example `StorePost`). the rule method is placement of validations.

- to make a request validation : `php artisan make:request StorePost`. makes a request class in `/app/http/requests` folder.

```php
<!-- app\Http\Controllers\PostsController.php -->
public function store(StorePost $request)
    {
        $validated = $request->validate();
        $post = new BlogPosts();
        $post->title = $validated['title'];
        $post->content = $validated['content'];
        $post->save();

        return redirect()->route('posts.show', ['post' => $post->id]);
    }
<!-- app\Http\Requests\StorePost.php -->
public function rules(): array
    {
        //Validations
        return [
            'title' => 'bail|required|min:5|max:100',
            'content' => 'min:10'
        ];
    }
```

form request can also check if the user is allowed to send data in this form(authorized).

### Session Flash Messages

Flash messages are one time messages, they get created, displayed once and then
immediately deleted using request variable session method flash. using `session()->flash('status','The Massage')` in controller with redirected return.

```php
<!-- app\Http\Controllers\PostsController.php -->
    public function store(StorePost $request)
    {
        $validated = $request->validated();
        $post = new BlogPosts();
        $post->title = $validated['title'];
        $post->content = $validated['content'];
        $post->save();

        session()->flash('status', 'Flash Message');
        return redirect()->route('posts.show', ['post' => $post->id]);
    }
<!-- resources\views\Layouts\app.blade.php -->
// then in layouts for redirection
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laravel App - @yield('title')</title>
    <style>
        .status {
            background: red;
            color: white;
        }
    </style>
</head>
<body>
    <div>
        @if(session()->has('status'))
            <div class="status">
                {{ session('status') }}
            </div>
        @endif
        @yield('content')
    </div>
</body>
</html>
```

It is very useful feature to keep the input entered by the user if the validations failed,
especially if the forms are larger and contain more fields. all we have to do is to set the `value="{{ old('title') }}"`

```php
<!-- resources\views\Posts\create.blade.php -->
<form action="{{ route('posts.store') }}" method="POST">
  @csrf
    <div><input type="text" name="title" value="{{ old('title') }}"></div>
    <div>
        <textarea name="content" value="{{ old('content') }}"></textarea>
    </div>
      ...
        <div><input type="submit" value="Create" class="btn btn-primary btn-block"></div>
</form>
```

we might create models that have more columns than just a couple, models allowed to perform mass assignment as a solution. **this is potentially a security vulnerability** so we use `fillable` property in our models
there are 3 ways to mass assignment when we are making a new model:

- `BlogPost::create();` - create will create a new model instance, feel all of its properties with the input and immediately try to save the model to the database. (UseCase: if we need all the properties at a time)
- `BlogPost::make();` - Make will create their model, feel its properties, but it would not try to save the model to the database. (UseCase: if we don't have all the properties values yet)

both of this solutions will create a new instance of middleware class. if we use create we don't need to `save()` model, but in make we got to.

- `fill()` - The third way is to use the fill method. (UseCase: when we already have existing model instance)

```PHP
<!-- app\Models\BlogPosts.php -->
class BlogPosts extends Model
{
    protected $fillable = ['title', 'content'];

    use HasFactory;
}
<!-- app\Http\Controllers\PostsController.php -->
public function store(StorePost $request)
    {
        $validated = $request->validated();
        $post = BlogPost::create($validated);
        session()->flash('status', 'Flash Message');

        return redirect()->route('posts.show', ['post' => $post->id]);
    }
```

## CRUD - Editing, Updating and Deleting

First we make a form in partial called `form.blade.php`, then we add edit, create, show, delete, index in Like Posts folder.

>Don't forget to routes. (`Route::resource('/posts', PostsController::class)->only(['index','show', 'create', 'store', 'edit']);`)

```php
<!-- Routes -->
Route::resource('/posts', PostsController::class)->only(['index','show', 'create', 'store', 'edit']);
// or if we are using all 5, we can remove only part.
Route::resource('/posts', PostsController::class);

<!-- Controllers -->
<!-- app\Http\Controllers\PostsController.php -->
use App\Http\Requests\StorePost;
use App\Models\BlogPosts;
use Illuminate\Support\Facades\DB;
class PostsController extends Controller
{
    public function index()
    {
        return view('posts.index', ['posts' => BlogPosts::all()]);
        //return all the posts in order of oldest to newest.
    }
    public function create()
    {
        return view('posts.create');
    }
    public function store(StorePost $request)
    {
        $validated = $request->validated();
        $post = BlogPosts::create($validated);
        session()->flash('status', 'Flash Message');

        return redirect()->route('posts.show', ['post' => $post->id]);
    }
    public function show($id)
    {
        return view('posts.show', ['post' => BlogPosts::findOrFail($id)]);
    }
    public function edit(string $id)
    {
        return view('Posts.edit', ['post' => BlogPosts::findOrFail($id)]);
    }
    public function update(StorePost $request, string $id)
    {
        $post = BlogPosts::findOrFail($id);//if not exits will show 404 page.
        $validated = $request->validated();
        $post->fill($validated);
        $post->save();

        session()->flash('status', 'Blog post was Updated!');

        return redirect()->route('posts.show', ['post' => $post->id]);
    }
    public function destroy(string $id)
    {
        $post = BlogPosts::findOrFail($id);
        $post->delete();

        session()->flash('status', 'Post was Deleted!');

        return redirect()->route('posts.index');
    }
}

<!-- Views -->
<!-- resources\views\Posts\Partials\form.blade.php -->
<div class="form-group">
    <label for="title">Title</label>
    <input id="title" type="text" name="title" class="form-control"
        value="{{ old('title', optional($post ?? null)->title) }}">
</div>
@error('title')
    <div class="alert alert-danger">{{ $message }}</div>
@enderror
<div class="form-group">
    <label for="content">Content</label>
    <textarea class="form-control" id="content" name="content">{{ old('content', optional($post ?? null)->content) }}</textarea>//old function here helps to keep data received from user. with optional we can access its properties, whether the object is null or not. `?? null` It returns the value on the left or the value on the right, if the value on the left is null or does not exist.
</div>
@if ($errors->any())
    <div class="mb-3">
        <ul class="list-group">
            @foreach ($errors->all() as $error)
                <li class="list-group-item list-group-item-danger">{{ $error }}</li>
            @endforeach
        </ul>
    </div>
@endif

<!-- resources\views\Posts\create.blade.php -->
@extends('layouts.app')

@section('title', 'Create the post')

@section('content')
<form action="{{ route('posts.store') }}" method="POST">
    @csrf
    @include('posts.partials.form')
    <div><input type="submit" value="Create" class="btn btn-primary btn-block"></div>
</form>
@endsection

<!-- resources\views\Posts\edit.blade.php -->
@extends('layouts.app')

@section('title', 'Update the post')

@section('content')
    <form action="{{ route('posts.update', ['post' => $post->id]) }}" method="POST">
        @csrf
        @method('PUT')
        @include('posts.partials.form')
        <div><input type="submit" value="Update" class="btn btn-primary btn-block"></div>
    </form>
@endsection

<!-- resources\views\Posts\show.blade.php -->

@extends('layouts.app')

@section('title', $post->title)

@section('content')
<h1>{{ $post->title }}</h1>
<p>{{ $post->content }}</p>
<p>Added {{ $post->created_at->diffForHumans() }}</p>

@if(now()->diffInMinutes($post->created_at) < 5)
<div class="alert alert-info">New!</div>
@endif
@endsection

<!-- resources\views\Posts\Partials\post.blade.php -->
@extends('layouts.app')

@section('title', 'Blog Posts')

@section('content')
    @forelse ($posts as $key => $post)
        @break($key >= 2)
        @continue($key == 1)

        @if ($loop->even)
            <div>{{ $key }}. {{ $post->title }}</div>
        @else
            <div style="background-color: silver">{{ $key }}. {{ $post->title }}</div>
        @endif
        <div>
            <form action="{{ route('posts.destroy', ['post' => $post->id]) }}" method="POST">
                @csrf //needed when we are using spoofing method
                @method('DELETE')
                <input type="submit" value="Delete!">
            </form>
        </div>
    @empty
        <div>No Posts Found!</div>
    @endforelse
@endsection

```

- method spoofing - The method attribute can stay exposed, but you need to add the method directive (`@method('PUT')`) with the actual method. this would add a hidden underscore method field to the form and will let Laravel understand that you intended to hit the put or patch and point even though the actual method use post.
-

## Assets & Styling

Laravel comes equipped with tools for asset management, even though our application is written in their style sheet and a JavaScript asset management is done using nodejs , the JavaScripts runtime comes with their NPM, the note package manager for JavaScript. It is what the composer is to be.

![Nodejs](Laravel%20Images%20Reference/11.png)

### Installing Bootstrap CSS Framework

in the project directory run `composer require Laravel/ui 3.0.0` and specify an exact version, then we can run `php artisan ui bootstrap` to configure bootstrap, Also make sure to run `php artisan ui:controllers`, This would generate authentication comptrollers

### Using NPM and Compiling Assets With MixWebpack

All front and libraries you need are configured inside the package JSON file of your project.
It's like a composer Json, but for the front end.

- `npm install` - This would download all libraries in their specified version to the node modules folder, and later it would create a package log file.
- `npm run dev` - compile all the assets for the first time.
- `npm run` - lets us run custom NPM actions defined in the `package.json` file. You can find `dev, Prod, watch` and more.

#### Prod action

is for production, so assets are minified and compiled in production mode for the fastest performance, **that's not useful in your development environment**.

#### watch action

is like running the dev action, but it keeps watching for changes and recompile everything automatically for you.**This is the preferred way to work.**

at the end run `npm run dev`.

### Including Assets in Views
