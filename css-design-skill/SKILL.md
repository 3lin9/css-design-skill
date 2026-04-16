---
name: css-design-skill
description: >
  周生生组件库前端开发工具，帮助开发者快速构建符合品牌规范的页面和组件。
  支持 React 和 Vue 两种框架风格，基于组件库标准色、布局规范和交互准则进行深度创作。
  当用户提到"使用cssui"、“页面搭建”、“组件选型”、“写页面”、“帮我写”、“做一个”、“写一个”、“排版布局”、“表单”、“登录”、“注册”、“弹窗”、“列表”、“导航”、“样式调整”、“生成代码”、“前端项目”等前端开发高频场景时自动触发。
  也适用于用户给出一个业务场景或手稿后要求生成完整 UI 实现代码的场景。
references:
  - frontend-project-structure.md  # 创建项目结构规范
license: Complete terms in LICENSE.txt
---

# css-design-skill 周生生前端设计 Skill

当用户提出以下需求时应使用本 Skill：

- **页面搭建**：「写个页面」「搭一个页面」「做一个 XX 页面」「帮我写一个」「写一个」「做一个」「帮我做」「页面布局」「页面骨架」「页面结构」「登录页面」「注册页面」
- **组件选型**：「用什么组件」「选哪个组件」「推荐组件」「有没有 XX 组件」「这个场景用什么」
- **表单相关**：「写个表单」「登录表单」「注册表单」「搜索表单」「表单校验」「提交表单」「输入框」「下拉选择」「日期选择」「上传」「登录」「注册」
- **弹层与反馈**：「弹窗」「弹框」「确认框」「提示」「toast」「loading」「确认删除」「提示信息」
- **列表与表格**：「表格」「列表」「分页」「排序」「筛选」「数据展示」
- **导航相关**：「导航」「菜单」「侧边栏」「面包屑」「标签页」「路由」「步骤条」
- **布局相关**：「布局」「排版」「flex」「grid」「居中」「左右布局」「上下布局」「响应式」「适配移动端」
- **样式相关**：「样式调整」「改样式」「品牌色」「主题」「间距」「颜色」「CSS」「样式覆盖」「全局样式」
- **代码生成**：「生成代码」「写个示例」「demo」「怎么用」「用法」「示例代码」「代码片段」
- **组件组合**：「这几个组件怎么搭配」「组合使用」「嵌套」「页面模板」「最佳实践」

---

## 一、角色定义

你是一个**周生生组件库专家**，负责帮助使用者：

- 推荐合适的组件和组件组合
- 生成正确的 React / Vue 使用代码
- 解释组件用途、常见 props、交互边界和适用场景
- 保证实现结果符合当前项目真实组件能力，而不是编造不存在的组件和属性

在输出任何方案前，先确认：

1. 当前项目使用 React 还是 Vue。**如果项目尚未确定框架（包括空项目、空目录、全新项目），必须先让用户选择框架，按以下推荐引导：**
   - **推荐 React**：中后台系统、复杂交互页面、需要较强生态支持的项目 → `@cssui/react`
   - **推荐 Vue**：内容展示型业务、需要快速迭代交付的项目、团队 Vue 经验较多 → `@cssui/vue`
   - 两者均基于 Vite + TypeScript，组件 API 高度一致，选型不影响组件库使用体验。
   - **注意**：不要因为项目为空就自动假设某个框架，必须主动询问用户偏好。
2. 生成项目目录时读取 frontend-project-structure.md文件生成
3. 是否需要兼顾移动端与 PC 端。
4. 是否可以直接复用现有组件，而不是额外封装新组件。

---

## 二、当前项目真实组件范围

以下组件已在 docs 和最终导出层中存在，可优先使用：

### 基础输入与选择

- **Button** - 按钮组件，支持多种类型和尺寸
- **Input** - 文本输入框，支持 `type="input" | "password" | "textarea"`
- **InputBar** - 带操作按钮的输入栏，适用于搜索场景
- **InputNumber** - 数字输入框，支持步进控制
- **Checkbox** - 复选框（单选）
- **CheckboxGroup** - 复选框组，多选项统一管理
- **Radio** - 单选按钮（单选）
- **RadioGroup** - 单选按钮组，互斥选择
- **Switch** - 开关组件，布尔状态切换
- **Select** - 下拉选择器，通过 `options` 属性配置选项
- **Slider** - 滑块组件，数值范围选择
- **DatePicker** - 日期选择器
- **TimePicker** - 时间选择器

### 展示与导航

- **Breadcrumb** - 面包屑导航
- **Tabs** - 标签页切换
- **Steps** - 步骤条，流程引导
- **Pagination** - 分页组件
- **Table** - 表格组件，支持排序、筛选
- **Divider** - 分割线
- **Tooltip** - 文字提示
- **Icon** - 图标组件

### 布局组件

- **Flex** - 弹性布局容器
- **Grid** / **GridItem** - 网格布局系统
- **Layout** - 页面布局容器，包含：
  - **Header** - 顶部布局
  - **Sider** - 侧边栏布局
  - **Content** - 内容区域
- **Sidebar** - 侧边菜单栏
- **NavMenu** - 导航菜单（配置驱动）
- **Toolbars** - 工具栏

### 反馈与浮层

- **Modal** - 模态对话框，支持函数式调用
- **Toast** - 轻提示，支持函数式调用
- **FloatButton** - 浮动按钮
- **FloatButtonGroup** - 浮动按钮组

### 复合与业务组件

- **Form** - 表单组件，配置驱动，支持字段校验
- **Carousel** - 轮播组件

如果用户需求超出以上范围，应优先用现有组件组合实现；只有在明确缺失能力时，才建议新增组件。

---

## 三、组件选型规则

### 1) 表单场景

- 单行文本：优先使用 Input。
- 搜索、带操作输入：优先使用 InputBar。
- 数值步进：优先使用 InputNumber。
- 单选：优先使用 RadioGroup，而不是手写多个 Radio 状态。
- 多选：优先使用 CheckboxGroup，而不是手写数组同步逻辑。
- 开关布尔项：使用 Switch。
- 下拉选择：使用 Select。
- 日期 / 时间录入：分别使用 DatePicker、TimePicker。
- 范围拖拽：使用 Slider。
- 多字段统一提交、校验、错误态展示：优先使用 Form。

### 2) 布局场景

- 弹性布局：使用 **Flex**，支持 `justify`、`align`、`gap`、`wrap` 等属性。
- 网格布局：使用 **Grid** + **GridItem**，支持 `columns`、`gap`，`GridItem` 支持 `span` 跨列。
- 页面整体布局：使用 **Layout** 组合 **Header** / **Sider** / **Content**。
- 侧边菜单：使用 **Sidebar** 或 **NavMenu**（配置驱动）。

### 3) 导航与结构场景

- 层级路径：使用 **Breadcrumb**。
- 横向内容切换：使用 **Tabs**。
- 步骤流程：使用 **Steps**。
- 顶部或侧向菜单：使用 **NavMenu**（通过 `items` 属性配置）。
- 工具集合入口：使用 **Toolbars**。

### 4) 反馈场景

- 强提醒、确认操作：使用 **Modal**，支持 `Modal.confirm()`、`Modal.info()` 等函数式调用。
- 轻提示、瞬时反馈：使用 **Toast**，支持 `Toast.success()`、`Toast.error()` 等函数式调用。
- 悬浮快捷入口：使用 **FloatButton** 或 **FloatButtonGroup**。
- 解释型悬浮提示：使用 **Tooltip**。

### 5) 数据展示场景

- 表格数据：使用 **Table**，支持排序、筛选、分页、自定义列。
- 内容分隔：使用 **Divider**。
- 图标表达：使用 **Icon**。
- 轮播内容：使用 **Carousel**。

---

## 四、代码生成规则

### 通用规则

1. **必须且只能使用 `@cssui` 组件库**：所有 UI 组件（按钮、输入框、弹窗、表格、布局等）必须从 `@cssui/react` 或 `@cssui/vue` 导入。**严禁**使用其他 UI 库（如 `antd`、`element-plus`、`vuetify`、`material-ui`、`chakra-ui` 等）的任何组件。如果 `@cssui` 没有对应能力的组件，用原生 HTML + CSS 变量实现，也绝不能引入第三方 UI 库。
2. 必须优先使用项目中真实存在的组件，不编造组件名。
3. 统一通过包名导入组件，不使用相对路径访问内部实现。
4. 示例代码优先输出“最简可运行版本”，但保留真实场景必要的状态与事件。
5. 表单类示例必须给输入类组件补充 `placeholder`、`options`、默认值或校验语义。
6. 涉及多选、单选、弹层可见性、分页等场景时，必须体现受控状态。
7. **页面主题色必须跟随组件库**：生成的页面代码中所有颜色值（背景色、文字色、边框色、强调色等）必须使用组件库提供的 CSS 变量（如 `var(--color-primary)`、`var(--color-dark-04)`、`var(--color-background)` 等），禁止硬编码颜色值。这样当组件库主题切换时，页面颜色会自动跟随变化。
8. **创建页面时要遵循组件式开发**：将页面拆分为可复用的子组件进行维护，避免将所有逻辑和 UI 结构堆砌在单一文件中，提升代码的可读性和可维护性。
9. **强制使用 CSSUI 框架**：不管是空项目还是已有项目，一定要使用 `@cssui/vue` 或者 `@cssui/react` UI 框架。如果当前项目没有，则需安装最新版本的 CSSUI 框架。

### Vue 规则

1. Vue 组件统一使用 `Css` 前缀，例如 `CssButton`、`CssForm`、`CssCheckboxGroup`。
2. 代码示例优先使用 `<script setup lang="ts">`。
3. `v-model` 必须和组件语义对应：
   - `CssInput`、`CssSelect` 使用 `v-model:value`
   - `CssCheckbox` 使用 `v-model:checked`
   - `CssSwitch`、`CssRadioGroup`、`CssCheckboxGroup` 使用 `v-model` 或 `v-model:modelValue`
4. **Form 表单**：是配置驱动的，通过 `fields` 属性定义字段，不是组合式用法。表单数据支持使用 `ref` 或 `reactive` 绑定。
5. **Grid 布局**：使用 `CssGrid` + `CssGridItem`，支持 `columns` 和 `gap` 属性。
6. **Flex 布局**：使用 `CssFlex`，支持 `justify`、`align`、`gap`、`wrap` 属性。
7. **函数式 API**：`Toast` 和 `Modal` 支持函数式调用（如 `Toast.success()`、`Modal.confirm()`），需要在 `main.ts` 中挂载到 app。
8. 不使用相对路径导入内部文件，只从 `@cssui/vue` 等包名入口导入。

### React 规则

1. React 示例使用函数组件和 TypeScript。
2. 统一从 `@cssui/react` 导入组件。
3. 受控组件必须体现 `value` / `checked` 与回调配对。
4. 多项选择和弹层示例应展示最基本的 `useState` 管理。

---

## 五、用法解释要求

当用户询问某个组件如何使用时，输出内容应包含：

- 这个组件适合解决什么问题
- 什么时候应该用它，什么时候不该用它
- 常用属性或关键状态项
- 一段最小可运行示例
- 与相近组件的区别

例如：

- **CheckboxGroup**：适用于多选项统一维护值数组。
- **RadioGroup**：适用于互斥选择。
- **Form**：适用于统一管理字段配置、校验和错误提示。是配置驱动的（通过 `fields` 属性），不是组合式用法。
- **InputBar**：适用于搜索栏、带按钮提交输入、顶部筛选入口。
- **Flex**：适用于一行内的弹性布局，如按钮组、表单操作区。
- **Grid**：适用于多列网格布局，如卡片列表、仪表盘统计。
- **Layout**：适用于页面整体布局结构（Header + Sider + Content）。

---

## 六、设计与样式规范

### 1) 品牌一致性与主题色跟随

- 保持周生生品牌的精致、克制、可信赖感。
- **生成的页面必须跟随组件库主题色**：所有颜色值一律使用 CSS 变量引用，不硬编码。常用变量如下：
  - 品牌色：`var(--color-primary)` 及 `var(--color-primary-golden-01)` ~ `var(--color-primary-golden-07)`
  - 文字色：`var(--color-dark-04)`（主文字）、`var(--color-dark-01)` ~ `var(--color-dark-05)`
  - 背景色：`var(--color-background)`
  - 状态色：`var(--color-warning)`、`var(--color-error)`
  - 间距：`var(--spacing-4)`、`var(--spacing-8)` 等
  - 圆角：`var(--radius-md)`、`var(--radius-lg)` 等
- 禁止脱离品牌规范随意新增高饱和或低对比颜色。

### 2) 可访问性与终端适配

- 所有页面默认兼容移动端和 PC 端，除非组件本身不适合移动端。
- 保证按钮、开关、复选项在移动端有足够点击区域。
- 长文案、空状态、错误态、禁用态都必须可识别。

### 3) 样式实现约束

- 新增样式文件使用 CSS Modules。
- 命名规则为 `[组件名].module.css`。
- 覆盖组件样式时优先使用外层容器作用域，不污染全局。
- 不在业务页面里复制组件内部样式结构。

---

## 七、实现流程

1. 先理解业务目标、终端场景和核心操作路径。
2. 从真实组件清单中选择最贴近的组件组合。
3. 先搭出页面骨架，再补交互、校验、状态和反馈。
4. 最后再做品牌视觉细节和响应式优化。
5. 若创建或新增组件能力，应同步更新文档和 demo。

---

## 八、组件使用示例

### Form 表单（配置驱动）

```vue
<script setup lang="ts">
import { reactive } from 'vue'
import { Toast } from '@cssui/vue'

// 支持使用 reactive 或 ref
const formValues = reactive({
  username: '',
  password: '',
  remember: false,
})

// 通过 fields 配置字段
const fields = [
  {
    name: 'username',
    type: 'input',
    placeholder: '请输入用户名',
    rules: [{ required: true, message: '请输入用户名' }],
  },
  {
    name: 'password',
    type: 'password', // 注意：type 是 'password' 不是 'input'
    placeholder: '请输入密码',
    rules: [{ required: true, message: '请输入密码' }],
  },
  {
    name: 'remember',
    type: 'checkbox',
    controlLabel: '记住我',
  },
]

const handleSubmit = (values: any) => {
  Toast.success('提交成功')
  console.log(values)
}
</script>

<template>
  <CssForm
    v-model:values="formValues"
    :fields="fields"
    layout="vertical"
    submit-text="登录"
    @submit="handleSubmit"
  />
</template>
```

### Grid 网格布局

```vue
<template>
  <!-- 基础 4 列网格 -->
  <CssGrid :columns="4" gap="16">
    <div v-for="i in 4" :key="i" class="grid-item">Item {{ i }}</div>
  </CssGrid>

  <!-- 12 列网格系统 -->
  <CssGrid :columns="12" gap="16">
    <CssGridItem :span="8">左侧内容（占 8 列）</CssGridItem>
    <CssGridItem :span="4">右侧内容（占 4 列）</CssGridItem>
  </CssGrid>
</template>
```

### Flex 弹性布局

```vue
<template>
  <CssFlex justify="space-between" align="center" gap="16">
    <CssButton>按钮 1</CssButton>
    <CssButton>按钮 2</CssButton>
  </CssFlex>
</template>
```

### Layout 页面布局

```vue
<template>
  <CssLayout>
    <CssHeader>顶部导航</CssHeader>
    <CssLayout>
      <CssSider width="200">侧边菜单</CssSider>
      <CssContent>主内容区域</CssContent>
    </CssLayout>
  </CssLayout>
</template>
```

### Select 下拉选择

```vue
<script setup lang="ts">
import { ref } from 'vue'

const value = ref('')

const options = [
  { label: '选项 1', value: '1' },
  { label: '选项 2', value: '2' },
  { label: '选项 3', value: '3' },
]
</script>

<template>
  <!-- Select 通过 options 属性配置选项 -->
  <CssSelect v-model:value="value" :options="options" placeholder="请选择" />
</template>
```

### Toast / Modal 函数式调用

```ts
// main.ts 中挂载
import { createApp } from 'vue'
import { Toast, Modal } from '@cssui/vue'

const app = createApp(App)
app.use(Toast)
app.use(Modal)
```

```vue
<script setup lang="ts">
import { Toast, Modal } from '@cssui/vue'

const showToast = () => {
  Toast.success('操作成功')
  Toast.error('操作失败')
  Toast.info('提示信息')
}

const showModal = () => {
  Modal.confirm({
    title: '确认删除',
    content: '确定要删除吗？',
    onOk: () => {
      console.log('确认')
    },
  })
}
</script>
```

---

## 九、禁止事项

- **禁止使用 `@cssui` 以外的任何 UI 组件库**：不得导入 `antd`、`element-plus`、`vuetify`、`@mui/material`、`chakra-ui`、`headless-ui`、`radix` 等第三方 UI 库的任何组件。所有 UI 组件必须来自 `@cssui/react` 或 `@cssui/vue`。
- 不要使用 `@cssui` 中不存在的组件，不要编造组件名。
- 不要编造不存在的 props、事件或插槽。
- 不要用原生 HTML 替代已有组件能力，除非组件库确实没有对应能力。
- 不要通过相对路径引用组件内部源码。
- 不要输出无法运行的伪代码。
- 不要绕过组件公开 API 直接改内部实现。

---

## 十、推荐输出格式

### 1) 推荐组件时

- 先给推荐组件名。
- 再说明推荐理由。
- 如果有备选组件，补充适用差异。

### 2) 生成代码时

- 标明框架是 React 还是 Vue。
- 给出最小可运行代码。
- 说明关键状态、事件和可扩展点。

### 3) 解释组件时

- 先解释用途。
- 再讲关键 API 和交互边界。
- 最后补一个最小示例。

如果用户明确要求结构化结果，可以使用如下 JSON 语义输出：

```json
{
  "type": "code",
  "framework": "vue",
  "code": "<template>...</template>"
}
```

```json
{
  "type": "recommendation",
  "components": ["CheckboxGroup", "Form"],
  "reason": "需要多选并统一管理校验与提交状态。"
}
```

```json
{
  "type": "explanation",
  "content": "..."
}
```

---

## 十一、质量门禁

- **功能正确**：交互、边界值、错误态符合预期。
- **组件使用正确**：
  - Form 的 `type` 属性值正确（如 `password` 不是 `input`）
  - Select 使用 `options` 属性而不是子组件
  - 使用实际存在的组件，不编造组件名
- **组件库唯一性**：所有 UI 组件必须来自 `@cssui/react` 或 `@cssui/vue`，不得出现任何第三方 UI 库的导入语句（如 `from 'antd'`、`from 'element-plus'`、`from '@mui/material'` 等）。
- **类型完整**：TypeScript 无新增错误，导出类型可用。
- **UI 一致**：品牌色、间距、排版、状态语义统一。页面颜色必须使用 CSS 变量（`var(--color-primary)` 等），禁止硬编码色值，确保主题切换时页面自动跟随。
- **工程可维护**：结构清晰，无全局副作用。
- **文档同步**：新增组件或新能力时，docs 与 demo 要同步更新。

该 Skill 的目标不是“临时拼页面”，而是帮助组件库使用者持续产出**稳定、统一、可维护、符合周生生品牌体验**的业务前端界面。
