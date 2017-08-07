1. 开启root用户



首先给root用户设置一个密码：



$ sudo passwd root\(设置root密码：qishiwohenaini\)

1

1. 开启root用户

2. 使用root用户登陆



$ sudo gedit /usr/share/lightdm/lightdm.conf.d/50-ubuntu.conf

1

1

在最后增加greeter-show-manual-login=true 

保存退出。注销后可看到登陆框已显示\(原来是guest的登录入口\)，可输入用户名。



3. 关闭guest用户



$ sudo gedit /usr/share/lightdm/lightdm.conf.d/50-ubuntu.conf

1

1

在最后增加allow-guest=false 

保存退出。注销后可看到已经没有guest用户登陆的选项。



4. 如果现在用root用户在图形界面登录会有错误，读取/root/.profile时发生错误：mesg:tty n 还需要做如下修改



sudu gedit /root/.profile



找到 mesg n

替换成 tty -s && mesg n

