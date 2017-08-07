### 所以在Java中一般报空指针异常的原因有以下几种：

1字符串变量未初始化；

2接口类型的对象没有用具体的类初始化，比如：

List lt；会报错

List lt = new ArrayList\(\)；则不会报错了

3当一个对象的值为空时，你没有判断为空的情况。你可以试着把下面的代码前加一行代码：

if\(rb!=null && rb!=""\)

改成：

if\(rb==null\);

if\(rb!==null&&rb!=""\) 或者if\(\(“”\).equals\(rb\)\)

空指针的解决办法：

```
   重点关注报错发生的所在行，通过空指针异常产生的两条主要原因诊断具体的错误。同时为了避免空指针的发生，最好在做判断处理时将“null”或者空值放于 设定的值之前。 
```

代码段1：

out.println\(request.getParameter\("username"\)\);

分析：代码段1的功能十分简单，就是输出用户输入"username"的值。

```
   说明：看上去，上面的语句找不出什么语法错误，而且在大多数情况下也遇不到什么问题。但是，如果某个用户在输入数据时并没有提供表单 域"username" 的值，或通过某种途径绕过表单直接输入时，此request.getParameter\("username"\)的值为空（注意不是空字符串，是空对象 null。），out对象的println方法是无法直接对空对象操作的，因此代码段1所在的JSP页面将会抛出 "Java.lang.NullPointerException"异常。而且即使对象可能为空时，也调用Java.lang.Object或 Object对象本身的一些方法如toString\(\)， equal\(Object obj\)等操作。 
```

代码段2：

String userName = request.getParameter\("username"\);

If \(userName.equals\("root"\)\)

{....}

分析：代码段2的功能是检测用户提供的用户名，如果是用户名称为"root"的用户时，就执行一些特别的操 作。

```
  说明：在代码段2中，如果有用户没有提供表单域"username"的值时，字符串对象userName为null值，不能够将一个null的对象与另一 个对象直接比较，同样，代码段2所在的JSP页面就会抛空指针错误。 
```

一个小技巧：如果要把某个方法的返回值与常量做比较，把常量放在前面，可以避免调用null对象的equals方法。譬如：

If \("root".equals\(userName\)\)

{....}

即使userName对象返回了null对象，这里也不会有空指针异常，可以照常运转。

代码段3：

String userName = session.getAttribute\("session.username"\).toString\(\);

```
    分析：代码段3的功能是将session中session.username的值取出，并将该值赋给字符串对象userName。 

   说明：在一般情况下，如果在用户已经进行某个会话，则不会出现什么问题；但是，如果此时应用服务器重新启动，而用户还没有重新登录，（也可能是用户关闭浏 览器，但是仍打开原来的页面。）那么，此时该session的值就会失效，同时导致session中的session.username的值为空。对一个 为 null的对象的直接执行toString\(\)操作，就会导致系统抛出空指针异常。 
```

代码段4：

public static void main\(String args\[\]\){

```
   Person p=null; 



    p.setName\("张三"\)； 



System.out.println\(p.getName\(\)\); 
```

}

分析：声明一个Person对象，并打印出该对象的中的Name名字。

说明：这个时候你的p就出现空指针异常，因为你只是声明了这个Person类型的对象并没有创建对象，所以它的堆里面没有地址引用，切忌你要用对 象掉用方法的时候一定要创建对象。

