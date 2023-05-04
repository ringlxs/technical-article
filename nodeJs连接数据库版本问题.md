图示：

<img src="C:\Users\20837\AppData\Roaming\Typora\typora-user-images\image-20211005120303120.png" alt="image-20211005120303120" style="zoom:80%;" />

##### 1.找到安装所在目录

```
C:\Program Files\MySQL\MySQL Server 8.0\bin
```

##### 2. 按下shift+右键打开 PowerShell

可到 cmd 窗口：

```
start cmd
```

##### 3.先登录数据库，输入当前数据库密码

```
mysql -u root -p
```

##### 4.然后粘进去按回车

```
ALTER USER 'root'@'localhost' IDENTIFIED BY 'password' PASSWORD EXPIRE NEVER;
```

##### 5.再然后改密码

```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '你自己设置的新密码';
```

##### 6.最后刷新

```
 FLUSH PRIVILEGES;
```
