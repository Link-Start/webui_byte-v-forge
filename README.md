# WebUI

`webui` 是 byte-v-forge 的 dashboard shell 与前端装载基础仓，提供统一布局、主题、导航、service catalog 和远程模块加载能力。

## 核心能力

- 提供平台 dashboard shell、基础路由、布局、主题和导航框架。
- 提供 service catalog Web/API 基础入口，支撑部署期声明式装载业务模块。
- 通过模块装载接口集成 GPT、Mailbox、SMS、GoPay、Proxy、Workflow 等服务拥有方前端。
- 前端基础组件、uikit 和通用数据驱动组件来自 `common-lib/ui`，本仓只保留 shell 与装载边界。
- 后端 server 只负责 shell/API gateway/service catalog 基础能力，不承载业务动作或 provider 状态机。

## 使用方式

业务页面、业务数据请求和资源详情归各业务仓；最终组合由 `deploy` 的 dashboard catalog 和部署配置声明。本仓通过 npm 包边界消费公共 UI 能力，不直接 import sibling repo 业务源码。

## 入口

- 前端源码：`src/`
- Shell server：`server/`
- 契约生成脚本：`scripts/generate-proto.sh`
- 静态资源：`public/`

## 常用检查

```sh
npm run proto:frontend
npm run lint
git diff --check
```
