# W1D1 — 把 Vue3 跑起来（2026-06-08 周一）

> 时长：2h ｜ 主题：环境 + 工程脚手架 + 第一个组件
> 今日核心一句话：**Vite 在开发时不打包，浏览器原生 ESM 按需请求模块——这是它启动快的根本原因。**

## 目标

建立"我能跑通 Vue3 工程"的肌肉记忆。**不**碰响应式原理、computed/watch、组件通信，那是 Day 2-3 的事。

## 任务清单（按时间顺序）

### 0:00–0:20 — 环境准备

- [ ] 安装 Node 18+（推荐 20 LTS）：https://nodejs.org/
- [ ] 安装 pnpm：`npm i -g pnpm`
- [ ] 验证：`node -v` ≥ 18，`pnpm -v` 能输出版本号
- [ ] 安装 VS Code 插件 **Vue - Official**（原 Volar）

> Python 类比：`node` ≈ `python` 解释器；`pnpm` ≈ `pip`（但更像 `poetry`，因为它管理 `node_modules` 像 `poetry` 管理虚拟环境）。

### 0:20–0:50 — 创建项目

- [ ] 在仓库根目录运行：
  ```bash
  cd weeks/week-01
  pnpm create vite@latest code -- --template vue-ts
  cd code
  pnpm install
  pnpm dev
  ```
- [ ] 浏览器打开 http://localhost:5173/，看到默认 Vue + Vite 欢迎页
- [ ] 不要关 dev server，整个 Day 1 都让它开着，体会 HMR

### 0:50–1:20 — 读懂脚手架

打开 `weeks/week-01/code/` 下这些文件，**逐一**理解：

- [ ] `package.json` — 项目元数据（≈ `pyproject.toml`）
- [ ] `vite.config.ts` — 构建/dev 服务器配置（≈ Django `settings.py` 但只管前端构建）
- [ ] `tsconfig.json` — TypeScript 编译选项
- [ ] `index.html` — **入口 HTML**（注意 `<script type="module" src="/src/main.ts">`，这是 Vite 工作的关键）
- [ ] `src/main.ts` — Vue 应用启动入口（≈ Flask 的 `app = Flask(__name__)` + `app.run()`）
- [ ] `src/App.vue` — 根组件（先看结构：`<script setup>` / `<template>` / `<style>` 三段式）

### 1:20–1:50 — 写第一个 Counter 组件

- [ ] 在 `src/components/` 下新建 `Counter.vue`：
  ```vue
  <script setup lang="ts">
  import { ref } from 'vue'

  const count = ref(0)
  const increment = () => count.value++
  </script>

  <template>
    <div>
      <p>当前计数：{{ count }}</p>
      <button @click="increment">+1</button>
    </div>
  </template>
  ```
- [ ] 在 `src/App.vue` 里 `import Counter from './components/Counter.vue'` 并在模板中用 `<Counter />`
- [ ] 浏览器点按钮，确认数字变化、HMR 工作
- [ ] **小实验**：试着把 `count.value++` 改成 `count++`，看报错；理解为什么 `ref` 在 `<script>` 里要 `.value`，但模板里不需要

### 1:50–2:00 — 提交 + 留痕

- [ ] 在 `weeks/week-01/` 下创建 `notes-day-01.md`，写 3 件事：
  1. 今天最让我"恍然大悟"的一点是？
  2. 还没完全搞懂的一点是？（标记 `TODO:` 留给 Day 2）
  3. Vite 的 dev server 为什么快？（用一句话解释，对照 Python dev server）
- [ ] 在 `weeks/week-01/ai-prompts.md` 记录今天问 AI 的关键 prompt（哪怕只问了一个）
- [ ] git commit：
  ```bash
  git add weeks/week-01/
  git commit -m "feat(w1d1): 搭建 Vite + Vue3 + TS 工程，完成 Counter 组件"
  ```

## 校验：今天学会了吗？

完成下面这些就算合格：

- [ ] `pnpm dev` 能起服务，能看到欢迎页
- [ ] Counter 组件可点击 +1，HMR 修改后无需手动刷新
- [ ] 能用一句话解释 `<script setup>`：它是 Vue3 的 Composition API 语法糖，文件顶层代码就是组件的 `setup()` 函数体
- [ ] 能用一句话解释 `ref`：包装一个值让 Vue 能追踪它的变化（脚本里访问要 `.value`，模板里自动解包）

## 不需要在今天搞懂的（留给后续）

- `reactive` 和 `ref` 的差异（Day 2）
- 为什么 Vue 要用 `Proxy` 实现响应式（Day 3 概念，深究放周末）
- 组件如何通信（Day 6）
- TypeScript 的复杂类型（Day 4）

## 参考

- [Vue 官方文档 - 快速上手](https://cn.vuejs.org/guide/quick-start.html)
- [Vite 官方文档 - 为什么选 Vite](https://cn.vitejs.dev/guide/why.html)
