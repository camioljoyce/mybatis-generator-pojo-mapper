#專案介紹
使用Mybatis generator 與不同資料庫連線 產生POJO 和 Mapper.xml
#使用說明
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

