---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/01-procedural/08-arrays/02-array-combine/","tags":["programming","php","webdevelopment","backend"],"created":"2024-11-09T11:30:30.463+08:00"}
---


--- 
> [!info] Syntax:
> Creates a __NEW ARRAY__ where:
> - It Uses the __First `Array`__ as `keys`
> - And ___Second `Array`___ as `values`
> ```php
> array_combine($array1, $array2);
> ```
> 
>> [!warning] Length doesn't match
>> If the __size or length__ of both `array` ___DIDN'T MATCH___
>> IT WILL THROW AN `ERROR`!
>> ```php
>> $array1 = ['a', 'b', 'c', 'd'];
>> $array2 = [5, 10, 15];
>> 
>> array_combine($array1, $array2);
>> ```

