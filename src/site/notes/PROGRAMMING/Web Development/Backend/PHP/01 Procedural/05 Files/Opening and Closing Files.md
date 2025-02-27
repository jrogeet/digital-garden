---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/01-procedural/05-files/opening-and-closing-files/","tags":["programming","php","webdevelopment","backend"],"created":"2024-11-09T11:30:30.659+08:00"}
---


--- 
#### Open files
```php
$file = fopen('foo.txt', 'r'); // r = read
```

> [!caution] Supressing Warnings
> NOT RECOMMENDED
> `@`
> ```php
> $file = @fopen('foobar.txt', 'r');
> 
> var_dump($file);
> ```
> RECOMMENDED:
> ```PHP
> if (! file_exists('foo.txt')) {
> 	echo 'File not found';
> 	
> 	return;
> }
> 
> $file = fopen('foobar.txt', 'r');
> 
> ```

> [!tip] Get lines and Loop through it:
> 
> ```php
> // this is a continuation of code above
> 
> while (($line = fgets($file)) !== false) {
> 	echo $line . 'br />';
> }
> 
> // CSV
> while (($line = fgetcsv($file)) !== false) {
> 	print_r($line);
> }
> ```
> `fgets`  gets each line from the file and store it in `$line`

#### Close file
```php
fclose($file);
```