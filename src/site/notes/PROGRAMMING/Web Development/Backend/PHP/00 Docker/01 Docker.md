---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/00-docker/01-docker/","tags":["programming","apache","php","docker"],"created":"2024-11-09T11:30:30.747+08:00"}
---

# Design

--- 
> [!info] Container
> Bundles up the applications with all of it's __dependencies__ and _configurations_
> ![Pasted image 20240325220346.png](/img/user/PROGRAMMING/Web%20Development/Backend/PHP/00%20Docker/attachments/Pasted%20image%2020240325220346.png)
> - __Dockerfile__: Where we tell which dependencies to install to run the application.
> 	- A text file with written instruction on how to build the __Docker Image__.
> - ___Docker Image___:  Read-only executable package includes everything needed like source code, dependencies etc.
> 	- Almost the same with _Container_ but read-only
> 	- Like the `Template` of __Dockerfile__
> - _Container_: Almost the same with ___Docker Image___ but needs it to run 
> ![Pasted image 20240326070410.png](/img/user/PROGRAMMING/Web%20Development/Backend/PHP/00%20Docker/attachments/Pasted%20image%2020240326070410.png)

