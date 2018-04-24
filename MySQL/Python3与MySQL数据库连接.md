CID操作

1、原子性：要么都做，要么都不做（两条数据(写入和存储)一步未成功，整体回滚）

2、一致性：数据库的状态改变（两条数据(写入和存储)均成功，符合原子性，但未保持相互一致，不符合一致性）

3、隔离性：写入数据不互相影响

4、持久性：数据只能修改，不能返回（不能进行'Ctrl+C'操作）




### Python3与MySQL 数据库连接
本文(以下代码)首先确定创建choice数据库，创建学生表TbStudent、课程表 TbCourse及选课信息表TbSC

##### 安装PyMySQL模块
```
pip install pymysql
```

##### 数据库连接

```PYTHON
# -*- coding: utf-8 -*-

import pymysql

# 1.连接到数据库
db = pymysql.Connect(
    host='localhost',
        user='root',
	    password='123456',
	        db='choice',
		    port=3306,
		        charset='utf8'
			)

			# 2.获取游标: 使用 cursor() 方法创建一个游标对象 cursor
			cursor = db.cursor()

			# 3.执行结果: 使用 execute()  方法执行 SQL 查询
			cursor.execute("select * from TbStudent")

			# 4.获取结果: 使用 fetchall() 方法获取所有数据.
			data = cursor.fetchall()

			# 获取一条结果: : 使用 fetchone() 方法获取单条数据.
			# data1 = cursor.fetchone()

			for i in data:
			    print('id:%s name:%s' % (i[0], i[1]))

			    # 6.关闭数据库连接
			    db.close()
			    ```
			    ##### 数据库插入操作
			    ```
			    # -*- coding:utf-8 -*-

			    import pymysql

			    db = pymysql.connect(
			    host = 'localhost',
			    user = 'root',
			    passwd = '123456',
			    db = 'choice',
			    port = 3306,
			    charset = 'utf8'
			    )

			    # 游标
			    cursor = db.cursor()

			    # 执行
			     try:
			      sql = '''insert into TbCourse values
			       (7777, 'c222语言程序设计', 3, '大神级讲师')'''
			        cursor.execute(sql)

				 db.commit()
				  except:

				   # 回滚（如果执行不成功）
				    db.rollback()

				     # 关闭
				      db.close()
				      ```

				      ##### 删除操作
				      ```
				      # 删除数据(前面代码同插入操作执行以前的代码)
				      try:
				      sql = '''delete from tbstudent where stuid=1002;'''
				      cursor.execute(sql)
				      db.commit()
				      except:
				      db.rollback()

				      # 关闭
				      db.close()
				      ```
				      ##### 创建数据库表
				      如果数据库连接存在我们可以使用execute()方法来为数据库创建表，如下所示创建表employee：
				      ```
				      # -*- coding:utf-8 -*-
				       
				       import pymysql
				        
					# 打开数据库连接
					db = pymysql.connect(
					host = 'localhost',
					user = 'root',
					passwd = '123456',
					db = 'choice',
					port = 3306,
					charset = 'utf8'
					)
					 
					 # 使用 cursor() 方法创建一个游标对象 cursor
					 cursor = db.cursor()
					  
					  # 使用 execute() 方法执行 SQL，如果表存在则删除
					  cursor.execute("DROP TABLE IF EXISTS EMPLOYEE")
					   
					   # 使用预处理语句创建表
					   sql = """CREATE TABLE EMPLOYEE (
					            FIRST_NAME  CHAR(20) NOT NULL,
						             LAST_NAME  CHAR(20),
							              AGE INT,  
								               SEX CHAR(1),
									                INCOME FLOAT )"""
											 
											 cursor.execute(sql)
											  
											  # 关闭数据库连接
											  db.close()
											  ```
