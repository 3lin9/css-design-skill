# React & Vue 项目结构规范

## 一、设计原则

### 1. 分层清晰

- 视图层（views/pages）
- 业务逻辑层（services / models）
- 状态管理层（store）
- 通用能力层（utils / hooks / composables）
- 基础设施层（request / config）

**禁止：**

- 组件中直接写 API 请求
- 页面中写复杂业务逻辑
- utils 变成“垃圾收纳箱”

---

## 二、React 项目结构

（适用于 React + TypeScript + Vite / Next.js + @cssui/react）

### 目录结构

```
├── src/
│ ├── assets/ # 资源文件
│ ├── components/
│ │ ├── common/ # 通用组件
│ │ │ ├── Button/
│ │ │ │ ├── Button.tsx
│ │ │ │ ├── Button.module.css
│ │ │ │ └── Button.test.tsx
│ │ │ └── Input/
│ │ └── business/ # 业务组件
│ ├── pages/ # 页面组件
│ │ ├── Home/
│ │ ├── User/
│ │ └── Product/
│ ├── layouts/ # 布局组件
│ ├── router/ # 路由配置
│ ├── store/ # 状态管理
│ │ ├── modules/ # 按模块划分
│ │ └── index.ts
│ ├── api/ # API接口
│ │ ├── request.ts # axios封装
│ │ └── modules/
│ ├── hooks/ # 自定义Hooks
│ ├── utils/ # 工具函数
│ ├── constants/ # 常量
│ ├── types/ # 类型定义
│ └── styles/ # 全局样式
├── public/  # 静态资源
├── .eslintrc.js
├── .prettierrc
├── vite.config.ts # 或 craco.config.js
└── package.json
```

---

### 模块内部规范

```
src/features/user/
├── index.ts             # 对外唯一出口
├── components/          # 私有组件（不可跨模块直接引用）
├── services/            # API
├── hooks/               # 业务 hooks
├── store/               # 状态管理（可选）
├── constants.ts
└── types.ts
```

**规则：**

- 页面路由入口建议放在 `pages/`（React）或 `views/`（Vue），业务能力沉淀在 `features/`
- 模块只能通过 `index.ts` 暴露
- 禁止跨模块直接引用内部文件（例如 `features/a/components/*` 不能被 `features/b` 直接 import）
- 公共复用逻辑优先上移到 `src/components` / `src/hooks` / `src/composables`

---

### Hooks 分层

```
src/hooks/useDebounce.ts
src/features/user/hooks/useUser.ts
```

---

### API 规范

```
src/features/user/services/user.service.ts
```

```ts
export const getUserInfo = () => request.get('/user')
```

---

### 状态管理建议

- 中小项目：Zustand
- 大型项目：Redux Toolkit

---

## 三、Vue 项目结构（Vue 3）

（Vue3 + TypeScript/JavaScript + Vite + Pinia + @cssui/vue）

### 目录结构

```
├── src/
│ ├── assets/ # 静态资源
│ ├── config/ # 配置文件
│ ├── layouts/ # 布局组件
│ ├── components/ # 公共组件
│ │ ├── base/ # 基础组件
│ │ │ └── BaseButton.vue
│ │ └── business/ # 业务组件
│ ├── views/ # 页面视图
│ │ ├── home/
│ │ │ └── index.vue
│ │ └── user/
│ │ └── index.vue
│ ├── router/ # 路由配置
│ │ └── index.ts
│ ├── store/ # Pinia/Vuex
│ │ ├── modules/
│ │ └── index.ts
│ ├── api/ # API接口
│ │ ├── request.ts
│ │ └── modules/
│ ├── composables/ # 组合式函数
│ ├── directives/ # 自定义指令
│ ├── utils/ # 工具函数
│ ├── constants/ # 常量
│ ├── types/ # 类型定义
│ └── styles/ # 全局样式
├── public/  # 静态资源
├── .eslintrc.js
├── .prettierrc
├── vite.config.ts
└── package.json
```

---

### Vue 特有规范

#### 1. 使用 composables 替代 mixin

```
src/features/user/composables/useUser.ts
```

---

#### 2. Pinia 模块化

```
src/features/user/store/user.store.ts
```

---

#### 3. SFC 规范

```vue
<script setup lang="ts"></script>

<template></template>

<style scoped></style>
```

---

#### 4. API 层

```
src/features/user/services/user.service.ts
```

---

## 四、推荐工具链

| 类别           | React                                          | Vue                               |
| :------------- | :--------------------------------------------- | :-------------------------------- |
| **构建工具**   | Vite / Next.js                                 | Vite / Nuxt                       |
| **包管理**     | pnpm / yarn                                    | pnpm / yarn                       |
| **类型检查**   | TypeScript                                     | TypeScript                        |
| **代码规范**   | ESLint + Prettier                              | ESLint + Prettier                 |
| **Git Hooks**  | husky + lint-staged                            | husky + lint-staged               |
| **测试框架**   | Vitest + Testing Library                       | Vitest + Vue Test Utils           |
| **E2E测试**    | Playwright / Cypress                           | Playwright / Cypress              |
| **组件库**     | @cssui/react                                   | @cssui/vue                        |
| **状态管理**   | Redux Toolkit / Zustand                        | Pinia / Vuex                      |
| **服务端状态** | TanStack Query (React Query)                   | TanStack Query (Vue Query)        |
| **路由**       | React Router v6 / Next.js Router               | Vue Router v4 / Nuxt Router       |
| **HTTP请求**   | Axios                                          | Axios                             |
| **样式方案**   | Tailwind CSS / CSS Modules / Styled-Components | Tailwind CSS / CSS Modules / SCSS |
| **组件文档**   | Storybook / Ladle                              | Storybook / Histoire              |
| **Monorepo**   | Turborepo / Nx                                 | Turborepo / Nx                    |

👉 **让错误无法扩散，让复杂度被隔离**
