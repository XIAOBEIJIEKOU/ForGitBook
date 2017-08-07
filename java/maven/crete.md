

先要设置好用户.m.settings.xml文件之后才能开始create

mvn archetype:create -DgroupId=org.seckill -DartifactId=seckill -DarchetypeArtifactId=maven-archetype-webapp

archetype:create命令已经过期，需要使用 archetype:generate 来进行代替

maven-archetype-plugin 2.3版本的插件有问题，换其它版本进行创建（方案可行）

可以采用mvn org.apache.maven.plugins:maven-archetype-plugin:2.2:create -DgroupId=storm.test -DartifactId=teststorm -DpackageName=cn.dataguru.storm

