在网上搜索到的解决方案──“将/var/lib/apt/list/lock删除掉即可”──其实是一种极端的情况，也就是在上次更新没有正常关闭的情况下使用。



在大部分情况下，问题的原因在于其它的程序如系统的自动更新、新立得等正在使用apt-get进程，所以解决方法也就是将这一进程关闭。



具体如下：



1、ps-aux 查出apt-get进程的PID，通常是一个四位数字。



2、用sudo kill PID代码 杀死进程



3、用sudo apt-get update，sudo apt-get dist-upgrade升级。



方法一：



执行一下 sudo dpkg --configure -a



方法二（亲测可以用）：



sudo rm /var/lib/apt/lists/lock



方法三：



1、ps-aux 查出apt-get进程的PID,



2、用sudo kill PID代码 杀死进程\(我都是找出带apt字样的进程格杀勿论\)



---------------------------分割线---------------------------



E:Could not get lock /var/lib/apt/lists/lock - open \(11: Resource temporarily unavailable\)



出现这个问题的原因可能是有另外一个程序正在运行，导致资源被锁不可用。而导致资源被锁的原因，可能是上次安装时没正常完成，而导致出现此状况。

 

解决方法：输入以下命令

 

sudo rm /var/cache/apt/archives/lock

 

sudo rm /var/lib/dpkg/lock

