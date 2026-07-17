# Mlorr.online - Game 部分

实时多人花园对战 / 收集类游戏，浏览器内直接游玩。

备注：

1. 本项目基于 [Gardn] 项目开发，并遵循 AGPL-3.0 开源协议。根据该协议要求，任何基于本项目的衍生作品，在分发时必须公开其完整源代码，且需同步托管至 GitHub 等公开代码仓库。
2. 本项目是 Mlorr 总项目下的一个子模块。Mlorr.online 是一个项目聚合平台，汇集了多个相互独立、各自遵循不同开源许可协议的子项目。
3. 本项目是 Mlorr.online 的核心游戏服务处理器，负责管理全部游戏引擎逻辑及游戏内容渲染，但不包含任何在线服务功能。所有在线服务相关功能，请移步 Mlorr-Online 项目。
4. Mlorr-Online 服务与 Gardn 项目无任何关联，其仅作为 Mlorr-Game 项目的在线服务 API 提供方。如需使用在线服务相关功能，请访问对应项目页面获取详细信息。
4. 在线服务是 Mlorr-Game 的一项可选扩展功能，以子插件形式独立于主项目存在。

## 功能概览

- 多地图世界（花园、沙漠、海洋、丛林、冥界、世界等）  
- 花瓣装备、背包、图鉴与掉落系统  
- 合成、小地图、Boss 条等交互
- 客户端版本检测
- 聊天、商店、交易平台、Web 管理后台（已废弃）（请移步至项目 Mlorr-Online）

---

## 运行环境

- **Node.js** 18+（推荐 LTS）  
- 支持 64 位 Linux / Windows / macOS（Node 宿主 + WASM）  
- 开放一个 TCP 端口（默认 **25882**，可通过环境变量修改）

---

## 快速开始

```bash
cd Mlorr.online-V1.0
npm install --omit=dev
node start.js
```

首次启动会可选择连接至 **Mlorr-Online** 在线服务 API，并自动生成部分凭据文件。

启动成功后访问：

| 用途 | 地址示例 |
|------|----------|
| 游戏页面 | `http://127.0.0.1:25882/` |
| 管理后台 | `已废弃` |

**管理后台已废弃，如需使用，请移步至 Mlorr-Online 项目。**

自定义端口：

```bash
# Windows PowerShell
$env:GARDN_PORT="25882"; node start.js

# Linux / macOS
GARDN_PORT=25882 node start.js
```

### 公网 / 反向代理

1. 将 HTTP 反代到本服务端口。  
2. 在管理后台配置 **对外 WebSocket 地址**（`ws://` 或 `wss://`）。  
3. HTTPS 站点必须使用 **wss://**，并确保证书与 WebSocket 升级配置正确。  
4. 玩家若卡在旧缓存，使用 **Ctrl+F5**（Mac：Cmd+Shift+R）强制刷新。

---

## 版本信息

| 字段 | 值 |
|------|----|
| 产品 | Mlorr.online |
| 发行 | V1.0 |
| 版本字符串 | 1.0.0 |

客户端 `index.html` 内嵌版本需与 `/api/version` 对齐；升级后请提醒玩家硬刷新。

---

## 社区

- GitHub：https://github.com/Cheerimy-Studio/Mlorr-Game  
- QQ 群：741017717

---

## 项目预览

[预览入口](http://mlorr.online)

> 本项目基于 Gardn 开发，部分素材来自 M28，遵循 AGPL 3.0 协议。

*Mlorr.online*
