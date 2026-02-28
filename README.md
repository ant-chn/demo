# Vue 3.5 项目推荐 Node.js 版本

## 结论：推荐使用 Node.js 22.22.0（LTS）

在 Cursor 中自动创建 Vue 3.5 项目，推荐使用 **Node.js 22.22.0**。

---

## 官方文档依据

### 1. Vue.js 官方快速上手指南

> 来源：[https://vuejs.org/guide/quick-start](https://vuejs.org/guide/quick-start)

Vue.js 官方文档明确要求 Node.js 版本满足：

```
^20.19.0 || >=22.12.0
```

即：**Node.js 20.19.0 ~ 20.x.x** 或 **Node.js >=22.12.0**。

### 2. Vite 6（Vue 3.5 项目默认构建工具）

> 来源：[https://vitejs.dev/guide/migration.html](https://vitejs.dev/guide/migration.html)

Vite 6 已**不再支持 Node.js 18**，最低要求为 **Node.js 20.19+ 或 22.12+**。
由于 `create-vue` 脚手架生成的 Vue 3.5 项目默认使用 Vite 6，因此 Node.js 版本必须满足 Vite 6 的要求。

### 3. create-vue 脚手架工具

> 来源：[https://github.com/vuejs/create-vue](https://github.com/vuejs/create-vue)

`create-vue`（当前最新版 v3.19.0）的 `package.json` 中 `engines.node` 字段为 `>=v18.3.0`，但这只是脚手架本身的运行门槛。生成的项目依赖 Vite 6，实际要求更高。

---

## 推荐版本对照表

| 版本 | 推荐等级 | 说明 |
|------|---------|------|
| **Node.js 22.22.0** | **首选推荐** | 满足 `>=22.12.0` 要求；Maintenance LTS，支持至 2027 年 4 月；与 Vue 3.5 + Vite 6 生态兼容性良好，经过充分验证 |
| Node.js 20.20.0 | 备选 | 满足 `^20.19.0` 要求；Maintenance LTS，但 **2026 年 4 月 30 日即将 EOL**，不建议新项目长期使用 |

> **注意**：Node.js 24.14.0（当前 Active LTS）也满足版本要求（`>=22.12.0`），可用于新项目。但 Vue 3.5 生态对 Node 22 的测试覆盖更充分，稳定性更有保障。如果追求最新 LTS 支持周期（至 2028 年 4 月），可考虑 Node.js 24。

---

## 在 Cursor 中使用

在 Cursor 中创建 Vue 3.5 项目前，请确保本地 Node.js 版本为 **22.22.0**：

```bash
# 查看当前 Node 版本
node -v

# 使用 nvm 安装并切换到推荐版本
nvm install 22.22.0
nvm use 22.22.0

# 创建 Vue 3.5 项目
npm create vue@latest
```

---

## Node.js LTS 生命周期参考（截至 2026 年 2 月）

| 版本 | 代号 | 状态 | EOL 日期 |
|------|------|------|----------|
| Node.js 20 | Iron | Maintenance LTS | 2026-04-30 |
| Node.js 22 | Jod | Maintenance LTS | 2027-04-30 |
| Node.js 24 | Krypton | **Active LTS** | 2028-04-30 |

> 来源：[https://nodejs.org/en/about/releases/](https://nodejs.org/en/about/releases/)

---

## 总结

综合 Vue.js 官方文档、Vite 6 引擎要求、Node.js LTS 生命周期以及生态兼容性：

- **推荐版本：Node.js 22.22.0（LTS）** — 稳定、兼容、支持周期充足
- **备选版本：Node.js 20.20.0（LTS）** — 可用但即将 EOL，仅建议短期过渡使用