---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/00-docker/mod-php-v-php-fpm/","tags":["programming","apache","php","docker"],"created":"2024-11-09T11:30:30.794+08:00"}
---

# Design

--- 
## mod_php

![Pasted image 20240326074608.png](/img/user/PROGRAMMING/Web%20Development/Backend/PHP/00%20Docker/attachments/Pasted%20image%2020240326074608.png)

Each ___Apache___ process has __LARGE FOOTPRINTS__ 
- Because it requires more resources when _php interpreter_ is embedded within ___Apache___

The process __STILL CONTAINS__ _php interpreter_ even when the request is for `non-PHP files` like STATIC FILES (`css`, `images` etc.)

> [!done] Can be solved by:
> __CDN__ or Content Delivery Network
> To load assets



## PHP-FPM
PHP Fast cgi Process Manager

![Pasted image 20240326080707.png](/img/user/PROGRAMMING/Web%20Development/Backend/PHP/00%20Docker/attachments/Pasted%20image%2020240326080707.png)

- A gateway that sits in between your `web server` and `php code`
- When `PHP File` is requested, ___Nginx___ communicates with __PHP-FPM__
	- and sends ONLY the `PHP Files` and not the static files.
__PHP-FPM__ can also be used in ___Apache___