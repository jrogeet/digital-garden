---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/01-procedural/02-data-types/04-float/","tags":["programming","php","webdevelopment","backend"],"created":"2024-11-09T11:30:29.938+08:00"}
---

# Float Data Type

--- 

>[!abstract] Float
>```php
>$x = 13.5;
>$x = 13_000.5;
>```
>
>> [!tip] Exponential Form
>> ```php
>> $x = 13.5e3; // 13500
>> $x = 13.5e-3; // 0.0135
>> ```
>
>
>> [!tip] Rounding
>> __Flooring__ / Round-down:
>> ```php
>> $x = floor((0.1 + 0.7) * 10); // 7
>> // ( 0.1 + 0.7 ) * 10 equals to 7.999...999118
>> ```
>> __Ceiling__ / Round-up
>> ```php
>> $x = ceil((0.1 + 0.7) * 10); // 8
>> 
>> $x = ceil((0.1 + 0.2) * 10); // 4
>> // (0.1 + 0.7) * 10 equals to 8.3000...00004
>> ```
>
>
>> [!tip] Check if `INF` or `NAN`
>> ```php
>> $x = PHP_FLOAT_MAX * 2;
>> var_dump(is_infinite($x)); // bool(true)
>> 
>> // check if it's FINITE
>> var_dump(is_finite($x)); // bool(false)
>> ```
>> NAN:
>> ```php
>> var_dump(is_nan($x)); // bool(false)
>> var_dump(is_nan(log (- 1))); // bool(t)
>> ```
>
>
>> [!tip] Conversion
>> ```php
>> $x = 5;
>> 
>> (float) $x
>> floatval($x)
>> ```




>[!info] NAN
>
