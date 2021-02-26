# Dependencies

- for password encrypt purpose, use druid

```
 <!-- Spring JPA-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>
        <!-- Mysql Connector -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.22</version>
        </dependency>
        <!-- https://mvnrepository.com/artifact/com.alibaba/druid-spring-boot-starter -->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid-spring-boot-starter</artifactId>
            <version>1.2.5</version>
        </dependency>
```

# data source yml

```
spring:
  datasource:
    type: com.alibaba.druid.pool.DruidDataSource
    driver-class-name: com.mysql.cj.jdbc.Driver
```

# jpa yml

- new property(database-platform) need to be set

```
spring
  jpa:
    show-sql: true
    hibernate:
      ddl-auto: update
    database-platform: org.hibernate.dialect.MySQL5InnoDBDialect
```

# druid yml

- for encrypt purpose
- filter.config.enabled: true

```
spring:
  datasource:
    druid:
      url: jdbc:mysql://a.b.c.d:3306/fund?tinyInt1isBit=false&useUnicode=true&autoReconnect=true&useSSL=false&characterEncoding=UTF8&allowMultiQueries=true&serverTimezone=Asia/Shanghai&nullCatalogMeansCurrent=true
      username: moma
      password: Pq6/hB/fom8njo8Pu7DdRmPVqud/Kna0RxQWaIyx6w1Ui8TcO/Cxr1rLYnXRypu4Oe5fLJWGgmUVB01A2n4b1g==
      connectionProperties: config.decrypt=true;config.decrypt.key=MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAPMvAZepxl9af6NzrGBkVR6kvj3ioOYjFUmjH9DFwxMaMZvDjKMKvowa4lH4fSpBPFeyMUwpv6vUuaTagTXBiPMCAwEAAQ==
      filter:
        config:
          enabled: true
```
