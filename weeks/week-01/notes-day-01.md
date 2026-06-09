# 今日心得
1. HMR是hot module replacement的缩写，即热模块替换，是Vite的默认功能，当源代码发生改变时，Vite会自动重新编译并刷新浏览器，无需手动刷新。
2. pnpm类似于python中的poetry，用于管理项目依赖，与npm类似，但npm的依赖管理方式基于npm的包管理器，而pnpm基于node的包管理器。其create命令创建项目时，会自动安装依赖，并生成package.json文件以及其他初始化的目录和文件。
3. Vite 的 dev server 为什么快？（用一句话解释，对照 Python dev server）
Vite 的 dev server 运行在 Node.js 上，而 Python 的 dev server 运行在 Python 的解释器上。Node.js 是一个 JavaScript 运行环境，而 Python 是一种解释型语言。Node.js 的运行速度更快，因此 Vite 的 dev server 运行速度更快。
4. npm和pnpm的指令有何区别？
npm和pnpm都是Node.js的包管理工具，用于安装、更新、删除和搜索包。区别在于npm是官方的包管理工具，pnpm是社区维护的包管理工具。pnpm提供了一些额外的功能，如自动缓存依赖项，并支持多线程下载。
