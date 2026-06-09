# Vue3 学习计划（6 周 / 30 天）

> 节奏：每天 2 小时，周一到周五，共 30 个学习日
> 起止：2026-06-08（W1D1）→ 2026-07-17（W6D5）
> 背景：Python 后端 → AI 辅助全栈

## 设计原则

- 每周节奏：**周一/二** 概念入门 → **周三/四** 深入用法 → **周五** 集成练习 + 复盘
- 每天严格控制在 2h，不超 3 个新知识点
- 周末不安排新内容（缓冲 / 补作业 / 自由探索）
- 每天产出落地到 `weeks/week-XX/day-XX.md` + `code/` 真实代码 + 一次 git commit
- AI 协同 prompt 记录到 `weeks/week-XX/ai-prompts.md`

---

## W1（06/08 – 06/12）Vite 工程化 + 响应式心智模型

| 日期 | 主题 | 核心知识 | 产出 |
|---|---|---|---|
| Mon 06/08 | 把 Vue3 跑起来 | Node/pnpm、Vite、`<script setup>`、`ref` 入门 | Counter 组件可运行 |
| Tue 06/09 | 模板语法 + 响应式基础 | 插值、`v-bind`/`v-on`/`v-if`/`v-for`、`ref` vs `reactive` | 表单输入双向绑定 demo |
| Wed 06/10 | 派生与监听 | `computed` 缓存 vs `watch` 副作用、`watchEffect` | 购物车小计 + 价格变动监听 |
| Thu 06/11 | TypeScript in Vue | 基础类型、`ref<T>`、`defineProps<{...}>`、`PropType` | Counter 组件加 TS 类型 |
| Fri 06/12 | W1 集成 + 复盘 | 整合本周所有概念 | TodoList（增删改查 + 持久化到 localStorage） |

**周末选作：** 阅读 [Vue 响应式原理](https://cn.vuejs.org/guide/extras/reactivity-in-depth.html) 文档，写 100 字理解笔记。

---

## W2（06/15 – 06/19）组件通信 + 生命周期 + Vitest 入门

| 日期 | 主题 | 核心知识 | 产出 |
|---|---|---|---|
| Mon 06/15 | 父子通信 | `defineProps` / `defineEmits` / `v-model` 自定义 | 受控 Input 组件 |
| Tue 06/16 | 跨层级通信 + 插槽 | `provide`/`inject`、默认/具名/作用域插槽 | 主题切换 + 通用 List 组件 |
| Wed 06/17 | 生命周期 | `onMounted`/`onUpdated`/`onUnmounted`、清理副作用 | 倒计时组件（不泄漏定时器） |
| Thu 06/18 | Vitest 入门 | 装配置、`describe`/`it`/`expect`、纯函数测试 | 工具函数库 + 测试覆盖 |
| Fri 06/19 | 组件测试 + 复盘 | `@vue/test-utils`、`mount`、触发事件 | Counter 与 Input 组件的测试用例 |

---

## W3（06/22 – 06/26）Vue Router + Pinia + 鉴权流转

| 日期 | 主题 | 核心知识 | 产出 |
|---|---|---|---|
| Mon 06/22 | 路由基础 | 路由配置、`<router-link>`、`<router-view>`、嵌套路由 | 多页面切换 demo |
| Tue 06/23 | 动态路由 + 守卫 | 参数路由、`beforeEach`、`meta`（≈ Django middleware） | 受保护路由 |
| Wed 06/24 | Pinia 入门 | `defineStore`、state/getters/actions | 全局计数器 + 用户 store |
| Thu 06/25 | Pinia 进阶 | 多 store 拆分、composable 模式、持久化 | 拆分后的 user/cart store |
| Fri 06/26 | 集成 + 复盘 | 路由 + Pinia 协同 | 登录 → 鉴权路由 → 状态保持 |

---

## W4（06/29 – 07/03）Element Plus + 表单/表格 + axios

| 日期 | 主题 | 核心知识 | 产出 |
|---|---|---|---|
| Mon 06/29 | Element Plus 接入 | 按需引入、主题、图标 | 配置完成 + 按钮/输入框样例 |
| Tue 06/30 | 复杂表单 | `el-form` + 校验规则 + 自定义校验 | 注册表单（密码确认/异步校验） |
| Wed 07/01 | 表格 | `el-table` + 分页 + 排序 + 远程数据 | 用户列表页 |
| Thu 07/02 | axios 封装 | 实例配置、请求/响应拦截器、错误统一处理 | `api/request.ts` 封装层 |
| Fri 07/03 | CRUD 集成 | 表格 + 表单 + axios 完整闭环 | 用户管理 CRUD 页面 |

---

## W5（07/06 – 07/10）全栈联调（FastAPI ↔ Vue）

> 用你熟悉的 Python（FastAPI）做后端，重点不是后端本身，而是**前后端协议、CORS、Mock、联调流程**。

| 日期 | 主题 | 核心知识 | 产出 |
|---|---|---|---|
| Mon 07/06 | 项目设计 | 选题（博客 or 任务管理）、API 接口设计 | `docs/api.md` 接口文档 |
| Tue 07/07 | 后端骨架 | FastAPI + SQLite + CORS | 后端可调用的 5 个接口 |
| Wed 07/08 | 列表/详情页 | 分页、加载态、错误态 | 文章列表 + 详情页 |
| Thu 07/09 | CRUD 流程 | 创建 / 编辑 / 删除 + 表单校验 | 完整 CRUD 闭环 |
| Fri 07/10 | 鉴权 + 复盘 | JWT 流转、401 拦截 | 带登录的完整应用 |

---

## W6（07/13 – 07/17）测试 + 性能 + 部署

| 日期 | 主题 | 核心知识 | 产出 |
|---|---|---|---|
| Mon 07/13 | 关键路径测试 | 给 W5 项目核心组件补测试 | 覆盖率报告 |
| Tue 07/14 | E2E 入门 | Playwright 装配 + 首个 e2e | 登录流程 e2e |
| Wed 07/15 | 性能优化 | 路由懒加载、`Suspense`、`KeepAlive`、`v-memo` | Lighthouse 跑分前后对比 |
| Thu 07/16 | 打包优化 | Vite 分包、依赖分析、生产构建 | `dist/` 体积优化报告 |
| Fri 07/17 | 部署 + 总结 | Vercel 或 Nginx + 环境变量 | 线上 URL + 完整 README |

---

## 风险与应对

- **某天没完成：** 周末补，不要堆到下周；如果连续两周延期，砍掉 W6 部署日改为缓冲
- **某周明显吃力：** 优先保留 W1/W2/W3，W4-W6 可压缩
- **AI 生成代码不理解：** 立刻停下来，让 AI 拆解到能用 Python 类比的程度再继续
