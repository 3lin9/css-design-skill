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

（适用于 React + TypeScript + Vite / Next.js）

### 目录结构

```
src/
├── app/                  # 应用初始化
│   ├── router/
│   ├── store/
│   └── providers/
│
├── modules/              # ⭐ 业务模块核心
│   ├── user/
│   │   ├── pages/
│   │   ├── components/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── store/
│   │   ├── types.ts
│   │   └── index.ts
│   │
│   ├── order/
│   └── product/
│
├── common/               # ⭐ 通用能力
│   ├── components/
│   ├── hooks/
│   ├── utils/
│   ├── constants/
│   └── types/
│
├── services/
│   ├── request.ts
│   └── api.ts
│
├── assets/
├── styles/
├── config/
├── routes/
├── main.tsx
└── App.tsx
```

---

### 模块内部规范

```
modules/user/
├── pages/           # 页面组件
├── components/      # 私有组件（不可跨模块引用）
├── services/        # API
├── hooks/           # 业务 hooks
├── store/           # 状态管理
├── types.ts
└── index.ts         # 对外唯一出口
```

**规则：**

- 模块只能通过 `index.ts` 暴露
- 禁止跨模块直接引用内部文件

---

### Hooks 分层

```
common/hooks/useDebounce.ts
modules/user/hooks/useUser.ts
```

---

### API 规范

```
modules/user/services/user.service.ts
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

（Vue3 + TypeScript + Vite + Pinia）

### 目录结构

```
src/
├── app/
│   ├── router/
│   ├── store/
│   └── plugins/
│
├── modules/
│   ├── user/
│   │   ├── views/
│   │   ├── components/
│   │   ├── composables/
│   │   ├── services/
│   │   ├── store/
│   │   ├── types.ts
│   │   └── index.ts
│   │
│   ├── order/
│   └── product/
│
├── common/
│   ├── components/
│   ├── composables/
│   ├── utils/
│   └── constants/
│
├── services/
│   ├── request.ts
│
├── directives/
├── assets/
├── styles/
├── config/
├── main.ts
└── App.vue
```

---

### Vue 特有规范

#### 1. 使用 composables 替代 mixin

```
modules/user/composables/useUser.ts
```

---

#### 2. Pinia 模块化

```
modules/user/store/user.store.ts
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
modules/user/services/user.service.ts
```

---

👉 **让错误无法扩散，让复杂度被隔离**
