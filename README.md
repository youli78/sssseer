# 温暖守护慈善电商平台

温暖守护是一个专注于慈善事业的电商平台，通过销售商品来支持各种公益项目，让每一次购买都充满意义。

## 项目技术栈

### 前端
- React 18
- TypeScript
- Vite
- Redux Toolkit
- Framer Motion
- Styled Components
- React Router
- react-i18next

### 后端
- Node.js
- Express
- TypeScript
- TypeORM
- MySQL
- JWT
- bcryptjs

## 项目结构

```
├── backend/           # 后端服务
│   ├── src/           # 后端源代码
│   ├── package.json   # 后端依赖
│   └── tsconfig.json  # TypeScript配置
├── src/               # 前端源代码
│   ├── components/    # React组件
│   ├── pages/         # 页面组件
│   ├── store/         # Redux状态管理
│   ├── styles/        # 样式文件
│   ├── types/         # TypeScript类型定义
│   └── i18n/           # 国际化配置
├── package.json       # 前端依赖
└── warmguarddb.sql    # MySQL数据库脚本
```

## 环境要求

- Node.js >= 18.x
- MySQL >= 8.x

## 安装和运行

### 1. 数据库设置

1. 确保MySQL服务已启动
2. 执行以下命令创建数据库和初始化数据：

```bash
# 登录MySQL
mysql -u root -p

# 输入密码（默认为123456）
123456
# 执行数据库脚本
source /path/to/warmguarddb.sql
```

### 2. 后端服务

```bash
# 进入后端目录
cd backend

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 或构建生产版本
npm run build
npm start
```

后端服务将在 http://localhost:3000 运行。

### 3. 前端服务

```bash
# 回到项目根目录
cd ..

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 或构建生产版本
npm run build
npm run preview
```

前端服务将在 http://localhost:5173 运行。

## API文档

### 认证

所有需要认证的API都需要在请求头中包含 `Authorization: Bearer <token>`，其中 `<token>` 是通过登录API获取的JWT token。

### 主要API端点

| 资源 | 方法 | 端点 | 描述 | 需要认证 |
|------|------|------|------|----------|
| 商品 | GET | /api/v1/products | 获取商品列表 | 否 |
| 商品 | GET | /api/v1/products/:id | 获取商品详情 | 否 |
| 分类 | GET | /api/v1/categories | 获取分类列表 | 否 |
| 用户 | POST | /api/v1/users/register | 用户注册 | 否 |
| 用户 | POST | /api/v1/users/login | 用户登录 | 否 |
| 用户 | GET | /api/v1/users/me | 获取当前用户信息 | 是 |
| 用户 | PUT | /api/v1/users/me | 更新当前用户信息 | 是 |
| 订单 | GET | /api/v1/orders | 获取订单列表 | 是 |
| 订单 | GET | /api/v1/orders/:id | 获取订单详情 | 是 |
| 订单 | POST | /api/v1/orders | 创建订单 | 是 |

## 环境配置

### 后端环境变量

创建 `.env` 文件，配置以下环境变量：

```
# 数据库配置
DB_HOST=localhost
DB_PORT=3306
DB_USERNAME=root
DB_PASSWORD=123456
DB_NAME=warmguarddb

# 服务器配置
PORT=3000
HOST=0.0.0.0

# JWT配置
JWT_SECRET=warm_guardian_jwt_secret_key_2025
JWT_EXPIRES_IN=7d

# 环境配置
NODE_ENV=development

# CORS配置
CORS_ORIGIN=http://localhost:5173
```

## 开发说明

### 添加新功能

1. 首先在 `src/types` 中定义新的TypeScript类型
2. 在 `src/entities` 中创建对应的数据库实体
3. 在 `src/routes` 中实现API端点
4. 在 `src/components` 中创建对应的React组件
5. 在 `src/pages` 中创建对应的页面组件

### 运行测试

```bash
# 前端
npm run test

# 后端
cd backend
npm run test
```

### 代码质量

```bash
# 前端
npm run lint
npm run typecheck

# 后端
cd backend
npm run lint
npm run typecheck
```

## 国际化

项目支持中英文双语切换，翻译文件位于 `src/i18n/locales` 目录下。

## 贡献

欢迎通过Pull Request或Issues来贡献代码或提出建议。

## 许可证

MIT License

## 联系方式

如有任何问题或建议，请联系项目团队：

- 邮箱：contact@warmguardian.com
- 电话：400-888-9999

## 感谢

感谢所有为项目做出贡献的开发者和支持者！
