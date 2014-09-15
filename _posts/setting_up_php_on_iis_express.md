Setting up php on IIS express
=============================

PHP runs just fine on IIS. In fact on [Azure](http://azure.com) you can very easily set up a php powered web site (example link?). So it makes sense to do your development in a very similar environment on your development box. You can do that with IIS express. You will to a few steps to get there, but it is not rocket science. 

Here are the steps that do the magic:
-------------------------------------

. Install IIS express. (It might be installed already if you have installed [visual studio](http://www.microsoft.com/visualstudio) or [webmatrix](http://www.microsoft.com/web/webmatrix/) - the default installation location is `C:\Program Files\IIS Express`)
. Install PHP (you can download it from the [PHP for windows download website](http://windows.php.net/download/) or via the [web platform installer](http://www.microsoft.com/web/downloads/platform.aspx) - note with the web platform installer you get the 32 bit version so you might want to download it directly from the mentioned PHP website.)
. open a command line prompt and type the following commands:
	. `cd /D "c:\Program Files\IIS Express"` (or whatever you specific IIS installation path is)
	. `appcmd set config -section:system.webServer/fastCgi /+"[fullPath='C:\Program Files (x86)\PHP\v5.3\php-cgi.exe',arguments='',maxInstances='4',idleTimeout='300',activityTimeout='30',requestTimeout='90',queueLength='1000',instanceMaxRequests='200',protocol='NamedPipe',flushNamedPipe='False',rapidFailsPerMinute='10']" /commit:apphost` the `fullPath='C:\Program Files (x86)\PHP\v5.3\php-cgi.exe'` part should of course point to the install path your particular `php-cgi.exe` file. 
	. `appcmd set config -section:system.webServer/handlers /+"[name='PHP-FastCGI',path='*.php',modules='FastCgiModule',verb='*', scriptProcessor='C:\Program Files (x86)\PHP\v5.3\php-cgi.exe']" /commit:apphost` and `scriptProcessor='C:\Program Files (x86)\PHP\v5.3\php-cgi.exe'` should agin point to your particular `php-cgi.exe` file.
	. `appcmd set config /section:defaultDocument /+files.[value='index.php']` 
. You can set up your site in a few ways (for instance for Visual Studio), but now that we are in command line let's do:
	. `appcmd add site /name:"sitename" /bindings:http/*:12345: /physicalPath:"C:\path\to\websitefolder"` where `sitename` is what you want IIS site name to be, `12345` is the port number (you can choose) and `C:\path\to\websitefolder` is the physical path to the web site on your local file system. 

That's it. Now when you start the webserver from the command line (if you don't run through Visual Studio for instance) you do: 
. c:\Program Files\IIS Express\iisexpress.exe /site:sitename
Now you can browse to `http://localhost:12345/` to see your site (If you have a default document on your site - a index.php file)

Fine, dude. But what happened.
------------------------------


