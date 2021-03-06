## 获取 Demo

 [Demo 下载 >> ](https://alon-deployment-gz-1257356411.cos.ap-guangzhou.myqcloud.com/tsf-demo-simple-1.16.0.zip) 


## 工程目录

`tsf-simple-demo`的工程目录如下：

```
|- consumer-demo：服务消费者
|- provider-demo：服务提供者
|- scg-demo：基于 Spring Cloud Gateway 的微服务网关示例（仅适用于 Finchley 版本 ）
|- zuul-demo：基于 Zuul 的微服务网关示例
|- cmq-producer-demo：CMQ 消息队列消息生产者示例
|- cmq-consumer-demo：CMQ 消息队列消息消费者示例
|- mongodb-demo：调用 MongoDB 的微服务示例
|- mysql-demo：调用 MySQL 的微服务示例
|- redis-demo：调用 Redis 的微服务示例
|- pom.xml
```

pom.xml 中定义了工程需要的依赖包（以下以基于 Spring Cloud Finchley 版本 SDK 举例说明）：

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

    <parent>
        <groupId>com.tencent.tsf</groupId>
        <artifactId>spring-cloud-tsf-dependencies</artifactId>
        <version><!-- 调整为 SDK 最新版本号 --></version>
    </parent>

	<groupId>com.tsf.demo</groupId>
	<artifactId>tsf-demo</artifactId>
	<version>1.12.0-Finchley-RELEASE</version>
	<packaging>pom</packaging>

	<modules>
		<module>provider-demo</module>
		<module>consumer-demo</module>
	</modules>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>1.8</java.version>
	</properties>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>
</project>
```

其中 parent 描述了`provider-demo`和`consumer-demo`共同的 TSF 依赖。

```xml
<parent>
        <groupId>com.tencent.tsf</groupId>
        <artifactId>spring-cloud-tsf-dependencies</artifactId>
        <version><!-- 调整为 SDK 最新版本号 --></version>
</parent>
```

关于 Maven 环境安装以及 TSF SDK 下载，请参考 [SDK 下载](https://cloud.tencent.com/document/product/649/20231) 和 [SDK 更新日志](https://cloud.tencent.com/document/product/649/20230) 。

## Demo 功能

- [服务注册与发现]( https://cloud.tencent.com/document/product/649/16617)
- [分布式配置](https://cloud.tencent.com/document/product/649/16620)
- [服务鉴权](https://cloud.tencent.com/document/product/649/16621)
- [服务限流](https://cloud.tencent.com/document/product/649/19019)
- [参数传递](https://cloud.tencent.com/document/product/649/18511)
- [调用链](https://cloud.tencent.com/document/product/649/16622)
