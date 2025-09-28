# realworld-spring-boot-native
> 本项目基于 [realworld-spring-boot-native](https://github.com/softwaremill/realworld-spring-boot-native) 搬运，遵循其开源协议（MIT License）。

> 一个较为不错的骨架级项目，接口标准明确，可用于做demo或快速搭后端

> 技术栈：Java 17 + Spring Boot 3 + Spring Data JPA……

## ![RealWorld Example App](logo.png)

> ### **Java 17 + Spring Boot 3 + 原生镜像** 包含真实案例（CRUD、认证、高级模式等）的代码库，遵循 [RealWorld](https://github.com/gothinkster/realworld) 规范和 API。

### [演示](https://demo.realworld.io/)&nbsp;&nbsp;&nbsp;&nbsp;[RealWorld](https://github.com/gothinkster/realworld)

这个代码库的创建目的是展示一个完整的全栈应用，使用 ****Java 17 + Spring Boot 3 作为原生应用**** 运行，并包含 CRUD 操作、用户认证、路由、分页等功能。

该应用基于 [Java 17 + Spring Boot 3 Real world application](https://github.com/shirohoo/realworld-java17-springboot3) ，仅针对原生应用运行做了改动。

> **注意：** 你只需要安装 JDK 17。
>
> **注意：** 如果在运行 gradle 任务时遇到权限不足，请执行 `chmod +x gradlew` 以授予权限。

## 使用 sdkman 安装 GraalVM 发行版

```shell
sdk install java 22.3.2.r17-nik
sdk use java 22.3.2.r17-nik
```

## 构建应用

```shell
./gradlew build
```

## 使用 native-image-agent 运行应用以收集可达性元数据

```shell
java -agentlib:native-image-agent=config-output-dir=./aot/META-INF/native-image/,experimental-class-define-support -Dspring.aot.enabled=true -jar ./build/libs/realworld.jar
```

## 在另一个终端窗口运行 API 集成测试

```shell
./api/run-api-tests.sh
```

## 关闭之前带有 native-image-agent 的运行应用
## 构建原生镜像

```shell
./gradlew nativeCompile
```

## 运行应用

```shell
./build/native/nativeCompile/realworld 
```
