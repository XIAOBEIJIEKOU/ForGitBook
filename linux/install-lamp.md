1.apt-get install apache2\(位置在所有用户/etc\)

apahce2 -v



2.apt-get install php

php -v

apache 通过加载 libphp.so的模块连接php

cat /etc/apache/mods-enabled/php.load



3.apt-get install mysql-server

php通过mysql.ini加载mysql，但是默认不加载这个module，手动添加

apt-get install php-mysql



4.重启两项服务

service mysql restart



5.tasksel install lamp-server

