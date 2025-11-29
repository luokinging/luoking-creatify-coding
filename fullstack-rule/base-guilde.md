# CLAUDE.md

## 全栈AI编程Agent指引

### 1. 项目边界快速识别

**重要提醒**：在根目录 `./` 下有多个项目，**严格只考虑以下两个项目目录**，忽略其他无关目录：

#### 前端项目：./main-web-ui
- **唯一前端项目目录**：`./main-web-ui/`
- **技术栈标志**：React + TypeScript + Vite + TanStack Router
- **关键文件**：`./main-web-ui/package.json`、`./main-web-ui/vite.config.ts`、`./main-web-ui/tsconfig.json`
- **目录特征**：`./main-web-ui/component/`、`./main-web-ui/feature/`、`./main-web-ui/lib/`、`./main-web-ui/hook/`、`./main-web-ui/manager/`
- **代码特征**：函数式组件、Zustand状态管理、Tailwind CSS样式
- **规范文件**：`./main-web-ui/CLAUDE.md`、`./main-web-ui/.cursor/rules/`

#### 后端项目：./webserver
- **唯一后端项目目录**：`./webserver/`
- **技术栈标志**：Django + Django REST Framework + Celery
- **关键文件**：`./webserver/manage.py`、`./webserver/requirements.txt`、`./webserver/pyproject.toml`
- **目录特征**：Django apps (`./webserver/accounts/`、`./webserver/api/`、`./webserver/assets/`、`./webserver/tools/`)
- **代码特征**：Django模型、视图、序列化器、Celery任务
- **规范文件**：`./webserver/CLAUDE.md`

#### 禁止事项
- **严格禁止**：修改根目录下的任何其他项目或目录
- **严格禁止**：在非指定目录下进行任何开发工作
- **严格禁止**：考虑除 `./main-web-ui` 和 `./webserver` 之外的其他目录

#### 需求范围判断
- **纯前端需求**：UI组件、页面布局、状态管理、用户交互
- **纯后端需求**：API接口、数据库操作、业务逻辑、异步任务
- **全栈需求**：前后端协作的完整功能（如用户认证、文件上传、数据展示）

### 2. 项目规范遵循

#### 严格遵循各项目现有规范
- **前端规范**：严格遵循 `./main-web-ui/CLAUDE.md` 和 `.cursor/rules/` 中的所有规范
- **后端规范**：严格遵循 `./webserver/CLAUDE.md` 中的所有规范和约定
- **遵循优先级**：项目具体规范 > 全局指引

#### 开发执行前必须阅读
在开始任何开发工作前，必须先阅读并理解对应项目的完整规范：

1. **前端任务** → 阅读 `./main-web-ui/CLAUDE.md` 和 `./main-web-ui/.cursor/rules/` 下的所有规则文件
2. **后端任务** → 阅读 `./webserver/CLAUDE.md`
3. **全栈任务** → 同时阅读前后端项目的所有规范文件

#### 核心规范引用
- **前端关键规范**：编程指引、项目配置、MVC架构、组件标准、目录组织
- **后端关键规范**：开发工作流、代码质量、测试编写、API开发模式、任务处理
- **代码质量保证**：前端 `bun precommit`、后端 `ruff check --fix && ruff format .`

#### 禁止事项
- **不得违反项目规范**：任何修改都必须严格遵循各项目的现有规范
- **不得重复规范内容**：本指引仅提供跨项目协调，具体开发规范以各项目为准
- **不得假设开发方式**：不确定时必须先阅读对应项目的规范文件