---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/01-procedural/04-control-structures/05-return-declare-and-tickable-statements/","tags":["programming","php","webdevelopment","backend"],"created":"2024-11-09T11:30:30.296+08:00"}
---


--- 
- `Return`
```php
function sum(int $x, int $y) {
	$z = $x + $y;
	
	return $z;
}

$x = sum(5, 10); // 15
```


> [!abstract] Declare
> 3 Derectives:
>> [!info] Ticks
>> ```php
>> $x =3;
>> $y = 5;
>> $z = $x * $y;
>> // each statement above causes an event TICK
>> 
>> register_tick_function('onTick');
>> 
>> declare(ticks=3);
>> 
>> $i = 0;
>> $length = 10;
>> 
>> while($i < $length) {
>> 	echo $i++ . '<br />';
>> }
>> 
>> ```
>> Use-case:
>> - Benchmarking or Profiling on how efficient your code runs.
>> 
>
>> [!info] Encoding 
>
>
>> [!info] strict_types
>> - Applies to all the code below `declare()`
>> 	- doesn't apply to another file
>> ```php
>> declare(strict_types=1);
>> 
>> function sum(int $x, int $y) {
>> 	return $x + $y;
>> }
>> 
>> echo sum(5, 10); // 15
>> echo sum('5', 10); // ERROR!
>> ```
>>> [!example] 
>>> `declare()` should also be declared in another file to apply there.
>>> ```php
>>> <?
>>> ```
```
```
