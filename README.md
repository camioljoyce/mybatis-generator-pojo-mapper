[![hackmd-github-sync-badge](https://hackmd.io/Cb6RMWZSQy6k5tlWofUm0g/badge)](https://hackmd.io/Cb6RMWZSQy6k5tlWofUm0g)
[Github連結](https://github.com/camioljoyce/mybatis-generator-pojo-mapper)
-
# 專案介紹 

使用Mybatis generator 產生POJO 和 Mapper.xml
# 使用說明
1.設定generatorConfig.xm的連線資訊 (ex: generatorConfig-Mysql ,這是與Mysql資料庫的連線)

```xml
 <jdbcConnection 
    	driverClass="com.mysql.cj.jdbc.Driver" 
    	connectionURL="jdbc:mysql://127.0.0.1:3306/stock?useUnicode=true&amp;characterEncoding=UTF-8&amp;serverTimezone=UTC" 
    	userId="root" 
    	password="1qaz@WSX" />
```
2.設定POJO和mapper.xml的路徑

```xml
 <javaModelGenerator targetPackage="camiol.pojo" targetProject="src/main/java" />
 <sqlMapGenerator targetPackage="mybtis.mapper" targetProject="src/main/resources" />
```
3.指定資料庫和POJO名稱

```xml
<table tableName="StockInfo"  domainObjectName="StockInfoDo">				
	    <property name="useActualColumnNames" value="true" />				
	 </table>
```

4.執行MybatisGenerator.java , refresh專案, 即可看到剛設定的路徑下會產生POJO和Mapper.xml

---
也可以使用run.bat來直接產生POJO和Mapper.xml

在generatorConfig-Mysql.xml 的第一行加上ClassPathEntry指定mysql的jar檔位置
```xml=
<!-- 可以在第一行加上ClassPathEntry 來使用run.bat來直接產生pojo和mapper.xml -->
	<classPathEntry location="C:\Users\A7024\.m2\repository\mysql\mysql-connector-java\8.0.21\mysql-connector-java-8.0.21.jar" />
```
將mybatis-generator-core-1.4.0.jar 放在跟POM檔同一層

新增一個文字文件，輸入
```
java -jar mybatis-generator-core-1.4.0.jar -configfile generatorConfig-Mysql.xml -overwrite
```
最後將他取名為run.bat, 一樣放在跟POM檔同一層

使用cmd 到該目錄下面，執行run.bat
![](https://i.imgur.com/0xCXqAN.jpg)

看到成功畫面後，POJO和mapper.xml就產生完成了

###### tags: `ORM` `Mybatis`



