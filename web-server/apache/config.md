### Apache虚拟主机配置调试

---

&lt;httpd.conf&gt;documentRoot的路径为默认路径，是localhost的访问首页。

1.&lt;extra/http-vhosts.conf&gt;documentRoot是虚拟主机的根目录，启用之后会重写httpd.conf中的documentRoot

`<VirtualHost *:80>`

```
DocumentRoot "C:/xampp/htdocs"
```

`</VirtualHost>`

`<VirtualHost *:80>`

```
ServerName www.qishiwohenaini.comqishiwohenaini

ServerAlias qishiwohenaini

DocumentRoot "C:/xampp/htdocs"
```

`</VirtualHost>`

2.还需要在system32下的hosts中配置域名。端口号必须和httpd.conf中一致，一个软件只能监听一个端口，documentRoot可以换成其他的文件夹。但是会重写httpd.conf中的documentRoot

另外注意，若是找不到servername的域名则会默认显示第一个virtualHost的路径

3.DW CS6站点的设置：

本地站点设置，本地站点文件夹是存放页面的文件夹，设置在默认根目录下的子文件夹

服务器设置，服务器文件夹和站点文件夹相同，是服务器访问的文件夹

重点是web url设置，localhost访问的文件夹是默认根目录，所以要localhost/Demo

2016-12-19

