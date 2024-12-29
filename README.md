# HelloGit
# 项目技术文档

## 1. 项目架构
### 前端技术栈
- Vue 3
- Vue Router
- Pinia (状态管理)
- Axios (HTTP请求)
- Element Plus (UI组件库)
- Node.js v16+
- npm/yarn (包管理器)

### 后端技术栈
- SpringBoot 2.7+
- Spring Security (认证和授权)
- MyBatis Plus (ORM框架)
- Maven (项目管理)
- JDK 17

### 数据库
- MySQL 8.0+

## 2. 项目结构

### 前端目录结构
```
src/
├── api/                # API 接口
├── assets/            # 静态资源
├── components/        # 公共组件
├── router/           # 路由配置
├── stores/           # Pinia 状态管理
├── utils/            # 工具函数
├── views/            # 页面视图
└── App.vue           # 根组件
```

### 后端目录结构
```
src/main/java/
├── config/           # 配置类
├── controller/       # 控制器
├── entity/          # 实体类
├── mapper/          # MyBatis映射接口
├── service/         # 服务层
│   ├── impl/        # 服务实现
├── utils/           # 工具类
└── Application.java # 启动类
```

## 3. 环境配置

### 前端环境配置
```bash
# 安装依赖
npm install

# 开发环境运行
npm run dev

# 生产环境打包
npm run build
```

### 后端环境配置
```yaml:application.yml
server:
  port: 8080

spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/database_name?useSSL=false&serverTimezone=UTC
    username: root
    password: your_password
```

## 4. 开发规范

### 前端规范
1. 组件命名采用大驼峰命名法（PascalCase）
2. API 接口统一管理在 api 目录下
3. 使用 ESLint 进行代码格式化
4. 组件属性顺序：props, data, computed, methods

### 后端规范
1. 类名采用大驼峰命名法
2. 方法名采用小驼峰命名法
3. 常量全大写，单词间用下划线分隔
4. 遵循 RESTful API 设计规范

## 5. 接口规范

### 响应格式
```json
{
    "code": 200,
    "message": "success",
    "data": {
        // 响应数据
    }
}
```

### 状态码说明
- 200: 成功
- 400: 请求参数错误
- 401: 未授权
- 403: 禁止访问
- 404: 资源不存在
- 500: 服务器内部错误

## 6. 安全配置
- 使用 Spring Security 进行身份认证
- 实现 JWT token 鉴权
- 密码加密存储
- 防止 XSS 和 CSRF 攻击

## 7. 部署说明
1. 前端打包后的文件放置在 Nginx 服务器
2. 后端打包成 jar 包部署到服务器
3. 配置跨域和反向代理
4. 数据库备份和定时任务配置

