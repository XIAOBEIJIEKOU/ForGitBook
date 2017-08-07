### Java解决中文乱码调试

---

#### `request.setCharacterEncoding("UTF-8");`

#### `response.setCharacterEncoding("UTF-8");`

#### `<meta http-equiv="Content-Type" content="text/html; charset=utf-8">`

#### `<%@ page language="java" contentType="text/html; charset=utf-8" pageEncoding="utf-8"%>`

设置与数据库连接的字符类型

#### `driverUrl = "jdbc:mysql://127.0.0.1/student_management?useUnicode=true&characterEncoding=utf8";`



