---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/03-superglobals/01-basic-routing-using-server-info/01-basic-routing/","tags":["programming","php","webdevelopment","backend","SUPERGLOBALS"],"created":"2024-11-09T11:30:30.838+08:00"}
---


---

**THESE ARE JUST EXAMPLE**
**_NOT TO BE USE ON PRODUCTION!!!_**
https://www.php.net/manual/en/language.variables.superglobals.php

> [!example] > _index.php_:
>
> ```php
> require_once __DIR__ . '/../vendor/autoload.php';
>
> $router = new App\Router();
>
> $router->register('/', function() {
> 	echo 'Home';
> });
>
> $router->register('/invoices', function() {
> 	echo 'Invoices';
> });
>
> echo $router->resolve($_SERVER['REQUEST_URI']);
> ```
>
> _Router.php_
>
> ```php
> declare(strict_types=1);
>
> namespace App;
>
> class Router
> {
> 	private array $routes;
>
> 	public function register(string, $route, callable $action): self
> 	{
> 		$this->routes[$route] = $action;
>
> 		return $this;
> 	}
>
> 	public function resolve(string $requestUri)
> 	{
> 		$route = explode('?', $requestUri)[0];
>
> 		$action = this->$routes[$route] ?? null;
>
> 		if (! $action) {
> 			throw new RouteNotFoundException();
> 		}
>
> 		return call_user_func($action);
> 	}
> }
> ```
>
> _RouteNotFoundException.php_
>
> ```php
> namespace App\Exception;
>
> class RouteNotFoundException extends \Exception
> {
> 	protected $message = '404 Not Found';
> }
> ```

> [!example] >_index.php_
>
> ```php
> require_once __DIR__ . '/../vendor/autoload.php';
>
> $router = new App\Router();
>
> $router
> 	->register('/', [App\Classes\Home::class, 'index'])
> 	->register('/invoices', [App\Classes\Invoice::class, 'index'])
> 	->register('/invoices/create', [App\Classes\Invoice::class, 'create']);
>
> echo $router->resolve($_SERVER['REQUEST_URI']);
> ```
>
> - `->register('/', [App\Classes\Home::class, 'index'])`
>   - `'/'` - the path
>   - `[App\Classes\Home::class, 'index']`
>     - `App\Classes\Home::class` - the **_class_** file
>     - `'index` - the **method** name
>
> _Router.php_
>
> ```php
> declare(strict_types=1);
>
> namespace App;
>
> class Router
> {
> 	private array $routes;
>
> 	// added array
> 	public function register(string, $route, callable | array $action): self
> 	{
> 		$this->routes[$route] = $action;
>
> 		return $this;
> 	}
>
> 	public function resolve(string $requestUri)
> 	{
> 		$route = explode('?', $requestUri)[0];
>
> 		$action = this->$routes[$route] ?? null;
>
> 		if (! $action) {
> 			throw new RouteNotFoundException();
> 		}
>
>
> 		if (is_callable($action)) {
> 			return call_user_func($action);
> 		}
>
> 		if (is_array($action)){
> 			[$class, $method] = $action;
>
> 			if (class_exists($class)) {
> 				$class = new $class();
>
> 				if (method_exists($class, $method)) {
> 					return call_user_func_array([$class, $method], []);
> 				}
> 			}
> 		}
>
> 		throw new RouteNotFoundException();
> 	}
> }
> ```
