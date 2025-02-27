---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/02-object-oriented-programming-oop/11-traits/02-traits/","tags":["programming","php","webdevelopment","backend","OOP"],"created":"2024-11-09T11:30:32.113+08:00"}
---


---

> [!info] # Trait
>
> - **CAN'T INSTANTIATE** or **CREATE A NEW `OBJECT` directly from the `TRAIT`**

_CoffeeMaker.php_

```php
namespace App;

class CoffeeMaker
{
	public function makeCoffee()
	{
		echo static::class . ' is making coffee' . PHP_EOL;
	}
}
```

_LatteTrait.php_:

```php
namespace App;

trait LatteTrait
{
	public function makeLatte()
	{
		echo static::class . ' is making latte' . PHP_EOL;
	}
}
```

_LatteMaker.php_:

```PHP
namespace App;

class LatteMaker extends CoffeeMaker
{
	use LatteTrait; // to use the trait
}

```

_CappuccinoTrait_:

```php
namespace App;

trait CappuccinoTrait
{
	public function makeCappuccino()
	{
		echo static::class . ' is making cappuccino' . PHP_EOL;
	}

}
```

_CappuccinoMaker.php_:

```php
namespace App;

class CappuccinoMaker extends CoffeeMaker
{
	use CappuccinoTrait;
}
```

_AllInOneCoffeeMaker.php_:

```php
namespace App;

class AllInOneCoffeeMaker extends CoffeeMaker
{
	use CappuccinoTrait;
	use LatteTrait;
}
```

_Index.php_

```php
$coffeeMaker = new \App\CoffeeMaker();
$coffeeMaker->makeCoffee();

$latteMaker = new \App\LatteMaker();
$latteMaker->makeCoffee();
$latteMaker->makeLatte();

$cappucinoMaker = new \App\CappuccinoMaker();
$cappuccinoMaker->makeCoffee();
$cappuccinoMaker->makeCappuccino();

$allInOneCoffeeMaker = new \App\AllInOneCoffeeMaker();
$allInOneCoffeeMaker->makeCoffee();
$allInOneCoffeeMaker->makeLatte();
$allInOneCoffeeMaker->makeOriginalLatte();
$allInOneCoffeeMaker->makeCappuccino();
```
