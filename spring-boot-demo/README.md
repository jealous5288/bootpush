# Spring Boot Demo Project

这是一个使用Spring Boot 3.2.0创建的演示项目，展示了基本的REST API功能。

## 项目特性

- **Spring Boot 3.2.0** - 最新的Spring Boot框架
- **Spring Web** - 用于构建REST API
- **Spring Data JPA** - 数据持久化
- **H2 Database** - 内存数据库（开发环境）
- **Spring Boot DevTools** - 开发工具，支持热重载

## 项目结构

```
src/
├── main/
│   ├── java/
│   │   └── com/
│   │       └── example/
│   │           ├── App.java                    # 主应用程序类
│   │           ├── controller/
│   │           │   ├── HelloController.java    # 基础控制器
│   │           │   └── UserController.java     # 用户管理控制器
│   │           ├── entity/
│   │           │   └── User.java               # 用户实体类
│   │           └── repository/
│   │               └── UserRepository.java     # 用户数据访问层
│   └── resources/
│       └── application.properties              # 应用配置文件
└── test/
    └── java/
```

## API 端点

### 基础端点
- `GET /api/hello` - 返回问候消息
- `GET /api/hello/{name}` - 返回个性化问候消息
- `GET /api/status` - 返回应用状态

### 用户管理端点
- `GET /api/users` - 获取所有用户
- `GET /api/users/{id}` - 根据ID获取用户
- `POST /api/users` - 创建新用户
- `PUT /api/users/{id}` - 更新用户信息
- `DELETE /api/users/{id}` - 删除用户

## 如何运行

1. 确保已安装Java 17和Maven
2. 在项目根目录运行：
   ```bash
   mvn spring-boot:run
   ```
3. 应用将在 http://localhost:8080 启动

## 数据库访问

项目使用H2内存数据库，可以通过以下方式访问：
- URL: http://localhost:8080/h2-console
- JDBC URL: jdbc:h2:mem:testdb
- 用户名: sa
- 密码: password

## 示例请求

### 创建用户
```bash
curl -X POST http://localhost:8080/api/users \
  -H "Content-Type: application/json" \
  -d '{"name":"张三","email":"zhangsan@example.com"}'
```

### 获取所有用户
```bash
curl http://localhost:8080/api/users
```

### 测试基础端点
```bash
curl http://localhost:8080/api/hello
curl http://localhost:8080/api/hello/世界
```

## 技术栈

- Java 17
- Spring Boot 3.2.0
- Spring Web
- Spring Data JPA
- H2 Database
- Maven