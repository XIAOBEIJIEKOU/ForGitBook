This page contains the following errors:

error on line 1 at column 2045: XML declaration allowed only at the start of the document

Below is a rendering of the page up to the first error.

使用纯粹的PHP代码生成字符串，并把这个字符串写入一个以XML为后缀的文件。这是最原始的生成XML的方法，不过有效！

PHP代码

`<?php`

`mysql_connect('localhost','root','');`

`mysql_query('use test');`

`$flag = mysql_query("select * from test2 where uid like '100%' ");`

`$String = "<?xml version='1.0' encoding='UTF-8'?>\n";//    特别注意要加换行符，其他的标签不加可以，但是第一行声明一定要加`

`$String .=  '<response>';`

`while($row = mysql_fetch_row($flag)){`

```
//注意php和Java对于字符串运算的区别+=和.=

$String.= '&lt;title&gt;'.$row\[1\].'&lt;/title&gt;';

}
```

`$String.= '</response>';`

`$file = fopen('title_correct.xml','a');`

`fwrite($file,$String);`

`fclose($file);`

`?>`

