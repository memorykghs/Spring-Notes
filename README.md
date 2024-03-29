# SpringBoot Notes
## 01 - Spring Boot 入門
[0. 物件導向設計原則](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/0.%20%E7%89%A9%E4%BB%B6%E5%B0%8E%E5%90%91%E8%A8%AD%E8%A8%88%E5%8E%9F%E5%89%87.md)
[0.1. 環境設定](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/0.1.%20%E7%92%B0%E5%A2%83%E8%A8%AD%E5%AE%9A.md)
[0.2. Maven問題解決方式](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/0.2.%20Maven%E5%95%8F%E9%A1%8C%E8%A7%A3%E6%B1%BA%E6%96%B9%E5%BC%8F.md)

[01. Spring Boot Initializr](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/01.%20Spring%20Boot%20Initializr.md)

[02. SpringBoot架構](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/02.%20SpringBoot%E6%9E%B6%E6%A7%8B.md)

[03. Controller-簡介RESTful API](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/03.%20Controller-%E7%B0%A1%E4%BB%8BRESTful%20API.md)

[04. Controller-建立RESTful API](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/04.%20Controller-%E5%BB%BA%E7%AB%8BRESTful%20API.md)

[05. Service](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/05.%20Service.md)

[05.5. Service補充](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/05.5.%20Service%E8%A3%9C%E5%85%85.md)

[06. Configuration & RestTemplate](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/06.%20Configuration%20%26%20RestTemplate.md)

[07. JPA-Entity & Repository](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/07.%20JPA-Entity%20%26%20Repository.md)
  
[07.1. hashCode與equals](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/07.1.%20hashCode%E8%88%87equals.md)

[08. JPA-Service & Controller & Request](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/08.%20JPA-Service%20%26%20Controller%20%26%20Request.md)

[08.1. JPQL簡介 & 簡單查詢](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/08.1.%20JPQL%E7%B0%A1%E4%BB%8B%20%26%20%E7%B0%A1%E5%96%AE%E6%9F%A5%E8%A9%A2.md)

[08.2. JPQL - Query with Params](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/08.2.%20JPQL%20-%20Query%20with%20Params.md)

[08.3. Query with SQL File](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/08.3.%20Query%20with%20SQL%20File.md)

[08.4. JPQL - Query with Dynamic SQL](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/08.4.%20JPQL%20-%20Query%20with%20Dynamic%20SQL.md)

[09. 調整 DTO](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/09.%20%E8%AA%BF%E6%95%B4%20DTO.md)

[10. 例外處理](https://github.com/memorykghs/Spring-Boot-Notes/blob/main/10.%20%E4%BE%8B%E5%A4%96%E8%99%95%E7%90%86.md)

## Others 
* [Google Guava](https://wizardforcel.gitbooks.io/guava-tutorial/content/1.html)

#### CH 5
- [ ] CH5 高內具低耦合?介面宣告?
- [ ] Bean生命週期
- [ ] Postman圖片截圖 & 講義圖片更換
- [ ] 8.3. Query with SQL File 圖片
#### CH 6
- [ ] `@Component` v.s. `@Bean`
   * `@Component` 加在 Class 上
   * `@Bean` 通常搭配 `@Configuration` 使用，標註在方法上
   * 雖然最後都會成為 `@Bean`
- [ ] 如何控制 `@Configuration` 或是 `@ControllerAdvice` 只針對某幾個 Class?
#### CH 7
- [ ] ORM 表現層 v.s. 業務層
- [ ] `hashCode()` &rArr; Set 切入點?
- [ ] 除了 JPA 外什麼時候還會覆寫 `hashCode()` 跟 `equals()` 方法?
- [ ] 如果資料庫沒有 PK，是不是就不能在 field 上加 `@Id`?
#### CH 9
- [ ] ObjectMapper - MapperFeature
- [ ] ObjectMapper - DeserializationFeature
#### CH 10
- [ ] WebExceptionHandler運作以及如何抓到被丟出的Exception
- [ ] package名稱後墜與功能是否跟Annotation有關係

##### Valid
* https://morosedog.gitlab.io/springboot-20190402-springboot19/
* https://www.uj5u.com/houduan/261372.html

#### 先放著，有空再說
- [ ] Entity 映設
  * https://super-passbook-3e3.notion.site/JPA-Associations-7b46fe01bf04482c9fd4f53865884605
- [ ] @ConfigurationProperties & @EnableConfigurationProperties
- [ ] yml 檢查
```properties
management:
  endpoint:
    metrics:
      enabled: true
    prometheus:
      enabled: true
  endpoints:
    web:
      base-path: /
      exposure:
        include: health, info, env, prometheus, metrics, httptrace, threaddump, heapdump, loggers
  metrics:
    export:
      prometheus:
        enabled: true
```
-[ ] ObjectMapper
   * https://super-passbook-3e3.notion.site/ObjectMapper-2367ffacf7a14beca69ae869ccb13d9a
   * https://segmentfault.com/a/1190000023735093
   * https://kucw.github.io/blog/2020/6/java-jackson/
   ```java
   //讀入需要更新的目標實體
   ObjectReader objectReader = mapper.readerForUpdating(list.get(0));
   //轉json字串
   String insertJson = mapper.writeValueAsString(list.get(0));
   // 將源實體的值賦值到目標實體上
   // CarResponse2Data data = objectReader.readValue(insertJson);
   // CarResponse2Data data = new CarResponse2Data();
   CarResponse2Data data = objectReader.readValue(insertJson, CarResponse2Data.class);
   ```
   * Jackson：https://github.com/FasterXML/jackson-annotations/wiki/Jackson-Annotations
   * @JsonSetter、@JsonGetter
   * @JsonAlias

## SQL Format Properties

```yml
# show sql
spring.jpa.show-sql=true

# formatting
spring.jpa.properties.hibernate.format_sql=true

# show generate SQL 
spring.jpa.properties.hibernate.use_sql_comments=true

# printing parameter values in log
logging.level.org.hibernate.SQL=DEBUG
logging.level.org.hibernate.type.descriptor.sql.BasicBinder=TRACE
```
* https://codeleading.com/article/17931741758/

## Transaction
- [ ] Transactional Propagation
   * https://www.javainuse.com/spring/boot-transaction-propagation
   * https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/299872/

- [ ] EntityManager
   * https://openhome.cc/Gossip/EJB3Gossip/FirstContainerManagedJPA.html
   * https://openhome.cc/Gossip/EJB3Gossip/EntityManagerScope.html
   * [SharedEntityManager](https://docs.spring.io/spring-framework/docs/3.2.4.RELEASE_to_4.0.0.RELEASE/Spring%20Framework%203.2.4.RELEASE/org/springframework/orm/jpa/SharedEntityManagerCreator.html)
   
```java
EntityManager em = entityManagerFactory.createEntityManager();
EntityTransaction tx = em.getTransaction();

try {
  tx.begin();
  ...
  tx.commit();
  
} catch (Exception e) {
  if (tx != null) {
    tx.rollback();
  }
}
```
   
- [ ] Persistence Context
   * https://www.baeldung.com/jpa-hibernate-persistence-context

- [ ] [JPA 和 Hiberante 的 AUTO flush 的機制](https://blog.csdn.net/qq_19922839/article/details/120706487)

## Kafka
```
列出所有topic
./kafka-topics.sh --list --zookeeper localhost:2181
./kafka-topics.sh --list --zookeeper 88.249.45.5:2181

建立topic 名字test  (partition代表此topic希望能建立幾個分區，一般而言，分區愈多處理速度愈快；replication-factor是副本數量)
./kafka-topics.sh --create --bootstrap-server 88.249.45.5:9092 --replication-factor 1 --partitions 1 --topic topic2

使用producer發送訊息
./kafka-console-producer.sh --broker-list 88.249.45.5:9092 --topic topic1

使用consumer收訊息
./kafka-console-consumer.sh --bootstrap-server 88.249.45.5:9092 --from-beginning --topic topic1

刪除topic
./kafka-topics.sh --delete --zookeeper 88.249.45.5:2181 --topic test

---------------------------------------------------------------------------------
window kafka 指令

啟動zookeeper
D:\Zookeeper\bin\zkServer

啟動kafka
D:\kafka\bin\windows\kafka-server-start.bat D:\kafka\config\server.properties

創建topic (partition代表此topic希望能建立幾個分區，一般而言，分區愈多處理速度愈快；replication-factor是副本數量)
D:\kafka\bin\windows\kafka-topics.bat --create --bootstrap-server 88.8.125.252:9092 --replication-factor 1 --partitions 1 --topic topic1

創建producer
D:\kafka\bin\windows\kafka-console-producer.bat --broker-list 88.8.125.194:9092 --topic topic1

創建consumer (加上--from-beginning參數會消費從topic創建開始的所有訊息)
D:\kafka\bin\windows\kafka-console-consumer.bat --bootstrap-server 88.8.125.252:9092 --topic topic1

列出所有topic
D:\kafka\bin\windows\kafka-topics.bat --list --zookeeper 88.8.125.249:2181

刪除topic
D:\kafka\bin\windows\kafka-topics.bat --delete --zookeeper 88.8.125.194:2181 --topic __consumer_offsets

查找8080 PORT
netstat -ano | findStr "8080"

殺掉該PORT號的PID
taskkill /f /PID 6092

```

## Store Procedure
* https://iter01.com/471453.html

## 監控 & 其他
```xml
<!-- Spring boot actuator to expose metrics endpoint -->
<dependency>
 <groupId>org.springframework.boot</groupId>
 <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
<!-- Micrometer Monitoring -->
<dependency>
 <groupId>io.micrometer</groupId>
 <artifactId>micrometer-core</artifactId>
</dependency>
<dependency>
 <groupId>io.micrometer</groupId>
 <artifactId>micrometer-registry-prometheus</artifactId>
</dependency>

<!-- https://mvnrepository.com/artifact/org.owasp.antisamy/antisamy -->
<dependency>
 <groupId>org.owasp.antisamy</groupId>
 <artifactId>antisamy</artifactId>
 <version>1.6.3</version>
</dependency>
```

* [JVM應用度量框架Micrometer](https://iter01.com/437347.html)
* [Actuator+Prometheus+Grafana監控視覺化簡介](https://www.tpisoftware.com/tpu/articleDetails/2446)


#### 監控記憶體大小
* jconsole
* jol-core
  ```xml
  <dependency>
    <groupId>org.openjdk.jol</groupId>
    <artifactId>jol-core</artifactId>
    <version>0.10</version>
  </dependency>
  ```
  使用：
  ```java
  System.out.println(GraphLayout.parseInstance(map).toFootprint()); // map 是要監控的物件
  ```

## Log
* https://segmentfault.com/a/1190000037598528
* [Log4j2 RollingFileAppender example](https://rumenz.com/java-topic/log4j2/log4j2-rollingfileappender-example/index.html)
* [Spring Boot學習之Logback和Log4j2整合與日誌發展史](https://www.itread01.com/content/1543060749.html)
* [TimeBasedRollingPolicy 詳解](http://www.51gjie.com/javaweb/1118.html)

## 其它
* https://javabeat.net/spring-framework-interview-questions/
