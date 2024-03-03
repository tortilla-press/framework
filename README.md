# not ready yet just showing progress
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
## Controller Examples (Controller definitions are located in /routes/web.tortilla)
### You can add as many controllers as you want as long as they have the specific .controller.tortilla file ending.
### This controller returns a view file when it's called by a route
```php
namespace App\Controllers;
class HomeController{
    public function Home(){
        view('index.view.tortilla');
    }
}
```
