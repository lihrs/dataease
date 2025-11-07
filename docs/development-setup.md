# DataEase 开发环境搭建指南

本文档提供了 DataEase 项目的开发环境搭建步骤，帮助开发者快速配置和运行项目。

## 项目结构

DataEase 项目主要包含以下核心组件：

- **core-backend**: 后端核心服务
- **core-frontend**: 前端应用
- **sdk**: SDK 组件和工具
- **drivers**: 数据库驱动
- **mapFiles**: 地图文件

## 环境要求

### 系统要求

- 操作系统: Windows/Linux/macOS
- 内存: 8GB 以上
- 磁盘空间: 10GB 以上

### 后端开发环境

- JDK 21
- Maven 3.8+
- MySQL 8.0+
- Redis 6.0+

### 前端开发环境

- Node.js 18+
- npm 9+

## 后端开发环境搭建

### 1. 安装 JDK 21

下载并安装 JDK 21，配置环境变量：

```bash
# 设置 JAVA_HOME 环境变量
# 将 JDK bin 目录添加到 PATH
```

### 2. 安装 Maven

下载并安装 Maven 3.8+，配置环境变量：

```bash
# 设置 MAVEN_HOME 环境变量
# 将 Maven bin 目录添加到 PATH
```

### 3. 安装 MySQL

安装 MySQL 8.0+，创建数据库：

```sql
CREATE DATABASE dataease DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
```

### 4. 安装 Redis

安装 Redis 6.0+，使用默认配置即可。

### 5. 编译后端项目

```bash
# 在项目根目录执行
mvn clean install -DskipTests
```

### 6. 运行后端服务

```bash
# 进入 core-backend 目录
cd core/core-backend

# 运行服务
mvn spring-boot:run
```

## 前端开发环境搭建

### 1. 安装 Node.js 和 npm

下载并安装 Node.js 18+，npm 会随 Node.js 一起安装。

### 2. 安装依赖

```bash
# 进入前端项目目录
cd core/core-frontend

#格式化
npm run lint:fix

# 安装依赖
npm install
```

### 3. 运行开发服务器

```bash
# 在前端项目目录下运行
npm run dev
```

前端开发服务器默认运行在 http://localhost:3000

## 开发工具推荐

### 后端开发

- IntelliJ IDEA
- Eclipse
- VS Code (安装 Java 扩展)

### 前端开发

- VS Code (推荐)
- WebStorm

## 常见问题

### 1. Maven 依赖下载失败

尝试配置国内 Maven 镜像，在 Maven 的 settings.xml 中添加：

```xml
<mirrors>
    <mirror>
        <id>aliyun</id>
        <name>aliyun Maven</name>
        <url>https://maven.aliyun.com/repository/public</url>
        <mirrorOf>central</mirrorOf>
    </mirror>
</mirrors>
```

### 2. npm 依赖安装慢

配置 npm 国内镜像：

```bash
npm config set registry https://registry.npmmirror.com
```

### 3. 后端服务启动失败

检查 MySQL 和 Redis 是否正常运行，检查数据库连接配置是否正确。

## 参考资源

- [Spring Boot 官方文档](https://spring.io/projects/spring-boot)
- [Maven 官方文档](https://maven.apache.org/guides/index.html)
- [Node.js 官方文档](https://nodejs.org/en/docs/)
