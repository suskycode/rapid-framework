# maven archetype 开发说明 #


## 示例: archetype.properties ##
```
archetype.groupId=com.googlecode.rapid-framework
archetype.artifactId=rapid-springmvc-mybatis-archetype
archetype.version=4.0

groupId=com.company.project
package=com.company.project
artifactId=demoproject
version=1.0-SNAPSHOT
```

**archetype.properties通过 archetype plugin插件声明引用**

```
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-archetype-plugin</artifactId>
	<version>2.0</version>
	<configuration>
		<propertyFile>archetype.properties</propertyFile>
	</configuration>
</plugin>
```

## 具体示例参考项目 ##
http://rapid-framework.googlecode.com/svn/trunk/rapid-mvn/rapid-archetype/rapid-springmvc-mybatis

## 项目目录结构 ##
```
src/main/java
src/main/webapp
src/main/flex  //如果有flex
src/main/generator_template/  //项目自定义模板存放目录
src/test/java
src/test/flex //如果有flex
```

## 项目common包 ##
com.company.project.common 用于存放公共代码

## 模板文件存放位置 ##
项目的模板文件统一存放在 rapid-generator-template项目，通过 classpath:generator/template/rapid的方式进行引用.

预留给客户端自定义的模板则存放在项目内,如:
```
src/main/generator_template/table/share/custom
  java_copyright.include
  java_description.include
  java_import.include
```