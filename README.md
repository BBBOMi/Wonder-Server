# bring(구 Wonder_server)

![bring_logo.PNG](https://github.com/BBBOMi/Wonder-Server/blob/master/img/bring_logo.PNG)

- 2018 SOPT 23기 Take-Out 원격 주문 서비스 'bring'
- 프로젝트 기간 : 2018년 12월 23일 ~ 2019년 1월 12일
- 맡은 역할 : 백 엔드 서버 개발, DB 모델링, API 문서 작성, 배포
- 사용 기술 : Spring-boot, MyBatis, FCM, AWS
- **API** - (<https://github.com/Bring-SOPT/Wonder-Server/wiki>)  
- E-R Diagram
  ![bring_ER_Diagram.PNG](https://github.com/BBBOMi/Wonder-Server/blob/master/img/bring_ER_Diagram.PNG)

<br>

## 시작하기

모든 소스코드는 IntelliJ + Windows10 + Java 8 환경에서 작성되었습니다.<br>

이 프로젝트에는 아래와 같은 **MAVEN 의존성 프로젝트**가 포함되어 있습니다.

```
<dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
            <version>1.3.2</version>
        </dependency>

        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
        </dependency>
        
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <optional>true</optional>
        </dependency>
        
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>

        <!-- AWS -->
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-aws</artifactId>
            <version>2.0.1.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-aws-context</artifactId>
            <version>1.2.1.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-aws-autoconfigure</artifactId>
            <version>1.2.1.RELEASE</version>
        </dependency>

        <!-- AOP -->
        <dependency>
            <groupId>org.aspectj</groupId>
            <artifactId>aspectjweaver</artifactId>
            <version>1.8.11</version>
        </dependency>

        <!-- JWT -->
        <dependency>
            <groupId>com.auth0</groupId>
            <artifactId>java-jwt</artifactId>
            <version>3.4.0</version>
        </dependency>
        <dependency>
            <groupId>commons-io</groupId>
            <artifactId>commons-io</artifactId>
            <version>2.4</version>
        </dependency>
        <dependency>
            <groupId>commons-io</groupId>
            <artifactId>commons-io</artifactId>
            <version>2.5</version>
        </dependency>
        
        <!--json-->
        <dependency>
            <groupId>org.json</groupId>
            <artifactId>json</artifactId>
            <version>20180813</version>
        </dependency>
</dependecies>
```


<br>

## 실행하기

**window 10 환경 기준**
- 8080 포트를 사용합니다.
- `jdk8` 과 `maven` 을 설치합니다.
- `JAVA_JOME` 환경변수 설정을 합니다.
- `Path`에 `maven` 환경변수 설정을 합니다.
- 내장 톰캣을 이용해 서버를 배포 합니다.
- `application.properties` 파일이 필요합니다.
- spring boot 앱 실행
```
mvn spring-boot:run
```
- 중지하려면, 키보드에서 `Ctrl + C`를 누릅니다. 


<br>

**AWS EC2 Ubuntu 환경**
- 8080 포트를 사용합니다.
- `jdk8` 과 `maven` 을 설치합니다.
- 내장 톰캣을 이용해 서버를 배포 합니다.
- `application.properties` 파일이 필요합니다.
- 백 그라운드 spring boot 앱 실행

```
nohup mvn spring-boot:run&
```
- 중지하려면, `netstat -tnlp` 명령어를 통해 프로세스를 kill 하십시오.

<br>

## 배포

- AWS EC2 - 애플리케이션 서버
- AWS RDS - db 서버
- AWS S3 - 저장소 서버

<br>

## 사용된 도구

- [Spring-boot](https://spring.io/projects/spring-boot) - Spring-boot 웹 프레임워크
- [Maven](https://maven.apache.org/) - 의존성 관리 프로그램
- [Tomcat](http://tomcat.apache.org/) - 웹 애플리케이션 서버
- [IntelliJ IDEA](https://www.jetbrains.com/idea/) - IDE
- [Mybatis](http://www.mybatis.org/mybatis-3/ko/index.html) - SQL 지원 Persistence 프레임워크
- [Mysql](https://www.mysql.com/) - DataBase
- [AWS EC2](https://aws.amazon.com/ko/ec2/?sc_channel=PS&sc_campaign=acquisition_KR&sc_publisher=google&sc_medium=english_ec2_b&sc_content=ec2_e&sc_detail=aws%20ec2&sc_category=ec2&sc_segment=177228231544&sc_matchtype=e&sc_country=KR&s_kwcid=AL!4422!3!177228231544!e!!g!!aws%20ec2&ef_id=WkRozwAAAnO-lPWy:20180412120123:s) - 클라우드 환경 컴퓨팅 시스템
- [AWS RDS](https://aws.amazon.com/ko/rds/) - 클라우드 환경 데이터베이스 관리 시스템
- [AWS S3](https://aws.amazon.com/ko/s3/?sc_channel=PS&sc_campaign=acquisition_KR&sc_publisher=google&sc_medium=english_s3_b&sc_content=s3_e&sc_detail=aws%20s3&sc_category=s3&sc_segment=177211245240&sc_matchtype=e&sc_country=KR&s_kwcid=AL!4422!3!177211245240!e!!g!!aws%20s3&ef_id=WkRozwAAAnO-lPWy:20180412120059:s) - 클라우드 환경 객체 스토리지
- [FCM](https://firebase.google.com/docs/cloud-messaging/?hl=ko) - 클라우드 메시징 시스템

<br>

## 개발자

- **김보미** - [BBBOMi](https://github.com/BBBOMi)
- **박다예** - [parkdaye](https://github.com/parkdaye)
- **신지우** - [jiwoooooo](https://github.com/jiwoooooo)
- **서영은** - [YoungEuny](https://github.com/YoungEuny)

[기여자 목록](https://github.com/BBBOMi/Wonder-Server/graphs/contributors)을 확인하여 이 프로젝트에 참가하신 분들을 보실 수 있습니다.

<br>

## bring의 다른 프로젝트

- [ANDROID](https://github.com/Bring-SOPT/Wonder-Android)
- [IOS](https://github.com/Bring-SOPT/Wonder-iOS)
- [SERVER-OWNER](https://github.com/Bring-SOPT/Wonder-Server-Owner)
- [ANDROID-OWNER](https://github.com/Bring-SOPT/Wonder-Android-Owner)

<br>

## 수상

- 2018 SOPT 제 23기 APPJAM 장려상 수상
------
