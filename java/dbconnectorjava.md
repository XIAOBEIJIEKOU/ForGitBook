package com.dao;



import java.sql.\*;



public class DBconnector {

	   //静态变量，final是因为一个项目里面不需要改变连接数据库的参数，更加准确的定义

	   private final static String driverName="com.mysql.jdbc.Driver";

	   private final static String driverUrl=

	   //防止中文乱码，与数据库交互的时候要设置字符编码

	              "jdbc:mysql://127.0.0.1/student\_management?useUnicode=true&characterEncoding=utf8";

	   private final static String username = "root";

	   private final static String password="";

	   

	   //静态方法，便于在main中测试

	   public static Connection getConnection\(\) throws SQLException{

	

			try {

				Class.forName\(driverName\);

			} catch \(ClassNotFoundException e\) {

				// TODO 自动生成的 catch 块

				e.printStackTrace\(\);

				System.out.println\("Cannot find driver!"\);

			}

			Connection con =DriverManager.getConnection\(driverUrl, username, password\);

			return con;

	   }

	   

	   //静态方法，便于在main中测试

	   public static ResultSet getSelect\(String sql\) throws SQLException{

		   Connection con=getConnection\(\);

		   Statement stmt=con.createStatement\(\);

		   ResultSet rs=stmt.executeQuery\(sql\);

		   /\*

		   单例模式关闭之后就无法访问了

		   \*/

		   //rs.close\(\);

		   //stmt.close\(\);

		   //con.close\(\);

		   return rs; 

	   }

	   

	   /\*\*public List&lt;Staff&gt; page\(int pagenum\) throws SQLException{

		   List&lt;Staff&gt; list= new ArrayList&lt;Staff&gt;\(\);

		   Connection con = getConnection\(\);

		   String sql="select \* from test2 limit ?,?";

		   PreparedStatement ps = con.prepareStatement\(sql\);

		   ps.setInt\(1, \(pagenum-1\)\*2\);

	

	   }\*/

	   public static void main\(String arg\[\]\){

		   try {

			//特别注意要注意字符编码！当被编译的Java代码中有中文特别注意

			String sql="select \* from student where StuID='142008080225'";

			//测试一下是否可以执行方法

			ResultSet rs= DBconnector.getSelect\(sql\);

			if\(rs.next\(\)\){

			    //注意返回的结果集是按照数据库设计的属性名

				//rs.getString\(String columnLabel\);

				//rs.getString\(int columnIndex\);

				System.out.println\(rs.getString\(2\)\);	

			}

		} catch \(SQLException e\) {

			// TODO 自动生成的 catch 块

			e.printStackTrace\(\);

		}

		   

	   }

	}



