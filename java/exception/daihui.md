### java.lang.NoClassDefFoundError: com/dao/DBconnector

---

> Exception: Servlet.service\(\) for servlet \[jsp\] in context with path \[/Session\] threw exception \[javax.servlet.ServletException: java.lang.NoClassDefFoundError: com/dao/DBconnector\] with root cause



experience：重新部署项目，将项目重新换一个服务器运行。会自动构建新的classpath，错误解决。



我们经常被java.lang.ClassNotFoundException和java.lang.NoClassDefFoundError这两个错误迷惑不清，尽管他们都与Java classpath有关，但是他们完全不同。NoClassDefFoundError发生在JVM在动态运行时，根据你提供的类名，在classpath中找到对应的类进行加载，但当它找不到这个类时，就发生了java.lang.NoClassDefFoundError的错误，而ClassNotFoundException是在编译的时候在classpath中找不到对应的类而发生的错误。ClassNotFoundException比NoClassDefFoundError容易解决，是因为在编译时我们就知道错误发生，并且完全是由于环境的问题导致。而如果你在J2EE的环境下工作，并且得到NoClassDefFoundError的异常，而且对应的错误的类是确实存在的，这说明这个类对于类加载器来说，可能是不可见的。

根据前文，很明显NoClassDefFoundError的错误是因为在运行时类加载器在classpath下找不到需要加载的类，所以我们需要把对应的类加载到classpath中，或者检查为什么类在classpath中是不可用的，这个发生可能的原因如下：

1.对应的Class在java的classpath中不可用

2.你可能用jar命令运行你的程序，但类并没有在jar文件的manifest文件中的classpath属性中定义

3.可能程序的启动脚本覆盖了原来的classpath环境变量

4.因为NoClassDefFoundError是java.lang.LinkageError的一个子类，所以可能由于程序依赖的原生的类库不可用而导致

5.检查日志文件中是否有java.lang.ExceptionInInitializerError这样的错误，NoClassDefFoundError有可能是由于静态初始化失败导致的

6.如果你工作在J2EE的环境，有多个不同的类加载器，也可能导致NoClassDefFoundError

