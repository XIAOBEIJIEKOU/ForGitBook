tomcat\_home\conf\server.xml 

从标签元素组成来理解，所谓servlet容器就是一个大的处理web应用的整体，对应其中的server元素（也就是根元素）下的service元素，

容器的名字叫Catalina，处理从客户端发来的请求。

接着service下有Connector元素（确定端口的连接）与

Engine元素（也就是引擎，负责做具体处理的，比如管理你所了解的servlet生命周期）

容器相当于小轿车，引擎也就是发动机（干实事的）

Engine下有不同主机即&lt;host&gt;元素来区分，通常一个的话就是localhost

host下有不同应用：即我们通常的Context 元素，可为每个应用配置虚拟目录，就是对应每个应用即你的 打包war文件

