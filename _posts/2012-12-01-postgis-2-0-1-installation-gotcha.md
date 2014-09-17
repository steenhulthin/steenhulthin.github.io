---
layout: blogpost
title: PostGIS 2.0.1 Installation Gotcha
lastupdated: 2014-09-16
categories: [GIS, PostGIS]
---
## PostGIS 2.0.1 Installation Gotcha

## createdb: could not connect to database template1: FATAL: password authentication failed for user "postgres"

### The short story If you are a hurry ***this is the essence of this post:*** 

*Problem:* 

You are trying to install PostGIS 2.0.1 on Windows, but you get an error and the error log says: `createdb: could not connect to database template1: FATAL:  password authentication failed for user "postgres"` 

*Reason:* 

There is a bug in the PostGIS installer which causes the installer to fail when the password of the postgres user contains certain special characters. 

*Workaround:* 

Change the password of the postgres users so that it does not contain special characters and then reinstall PostGIS. 

### The longer story 

If you have worked with GIS or spatial data you will most likely at some point run into PostGIS - the spatial extension for PostgreSql. 

You happily go ahead and install PostgreSql 9.2 and set the password of the postgres user (which is superuser for PostgreSql) to `pass^Word42`. Yeah, upper, lower, numbers and special characters - super secure. Well, ***there's you problem***. The PostGIS installer fails if the passwords containing `^`. When you go through your PostGIS installation wizard You'll see this: 

[<img src="http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer4.png" alt="postgis installer wizard on the database connection step" title="postgis_installer4" width="513" height="399" class="alignnone size-full wp-image-69" />][1] 

And then when you click next this: 

[<img src="http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer5.png" alt="Error mesage popup &quot;Database creation failed&quot; during PostGIS install" title="postgis_installer5" width="497" height="214" class="alignnone size-full wp-image-75" />][2] 

In the error log you'll see: `createdb: could not connect to database template1: FATAL:  password authentication failed for user "postgres"` 

[<img src="http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer6.png" alt="error log screenshot" title="postgis_installer6" width="578" height="292" class="alignnone size-full wp-image-76" />][3] 

The next dialog prompts you to continue or abort the installation (abort is clicking 'cancel'). 

[<img src="http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer7.png" alt="PostGIS installation warning - click cancel to abort installation" title="postgis_installer7" width="469" height="259" class="alignnone size-full wp-image-74" />][4] 

I think the easiest solution is to click cancel, change password for the postgres user to one without special characters and run the PostGIS installation again. 

Not all special characters present a problem during installation. `` $ \ / ` ' " ; . + * @ `` all work fine, but ` ^ ´ & > ` fail as described above. ` | ` failed and didn't write anything to the error log and the worst case ` < ` caused the installation to simply hang. 

PostGIS can be installed on top of PostgreSql directly from the PostGIS installer or using PostgreSql's stackbuilder. Stackbuilder is a GUI tool to help setting up the stack related to the PostgreSql database. But no matter if you install PostGIS from Stack Builder or from the PostGIS 2.0.1 installer directly this bug is present. 

The bug is semi-officially recognized - see [here][5] or [here][6] 

With that I wish you happy installation of PostGIS 2.0.1!

 [1]: http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer4.png
 [2]: http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer5.png
 [3]: http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer6.png
 [4]: http://steen.hulthin.dk/blog/wp-content/uploads/2012/12/postgis_installer7.png
 [5]: http://www.mail-archive.com/postgis-users@postgis.refractions.net/msg19175.html
 [6]: http://www.mentby.com/Group/postgis-users/installing-64-bit-postgis-201-with-windowsinstaller.html