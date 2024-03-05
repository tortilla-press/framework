# not ready yet just showing progress
#### You should never need to edit anything in /private. If you need to you most likely don't or it's a bug that you should notify us of.
## Routing Examples (Route definitions are located in /routes/web.tortilla)
### Using controllers
```php
new Route("/", "HomeController@Home");
```
### Using direct view file
```php
new Route("/", "index.view.tortilla");
new Route("/hi/hello", "hi/hello.view.tortilla");
```
### Extending other view files (good for navbars you want seen globally)
```php
new Route("/", "index.view.tortilla", [
    "extend" => [
        "includes/nav.view.tortilla"
    ]
]);
new Route("/", "HomeController@Home", [
    "extend" => [
        "includes/nav.view.tortilla"
    ]
]);
```
## Controller Examples (Controller definitions are located in /controllers)
#### You can add as many controllers as you want as long as they have the specific .controller.tortilla file ending.
### This controller returns a view file when it's called by a route and defines a variable that can be used in the view file
```php
    namespace App\Controllers;
    class HomeController extends Tortilla{
        public function Home(){
            return view('index.view.tortilla', [
                "FrameworkName" => "Tortilla.Press"
            ]);
        }
    }
```
### This controller just returns a view file
```php
    namespace App\Controllers;
    class HomeController extends Tortilla{
        public function Home(){
            return view('index.view.tortilla');
        }
    }
```
## Model Examples (Controller definitions are located in /models)
### Get the first user
```php
User::where([['id', '=', '1']])->first();
```
