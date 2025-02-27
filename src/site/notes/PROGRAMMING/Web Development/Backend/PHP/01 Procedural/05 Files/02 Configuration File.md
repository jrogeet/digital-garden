---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/01-procedural/05-files/02-configuration-file/","tags":["programming","php","webdevelopment","backend"],"created":"2024-11-09T11:30:30.633+08:00"}
---


--- 
https://www.php.net/manual/en/ini.list.php

> [!info]
> In `php.ini` or the Configuration File
>-  `[]` are IGNORED
>- `;` Semi-Colons are COMMENTS


> [!tip]
> ```php
> ini_get(); //  Get Directives
> 	ini_set(); // Change Directives
> ```
> - PHP_INI_PERDIR & PHP_INI_SYSTEM __cannot be changed__ DURING `RUNTIME`

> [!example] Some Directives:
>> [!tip] `error_reporting`
>> ```php
>> var_dump(ini_get('error_reporting')); // string(5) "3267"
>> var_dump(E_ALL); // int(32767)
>> 
>> ini_set('error_reporting', E_ALL & ~E_WARNING); // not (~)E_WARNING : IGNORES WARNING
>> ```
>
>
>>[!tip] `display_errors`
>>```php
>>ini_set('display_errors', 0);
>>```

