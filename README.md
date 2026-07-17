# Mlorr.online

实时多人花园对战 / 收集类游戏，浏览器内直接游玩。

- **官网 / 开源页**：https://github.com/Cheerimy-Studio/Mlorr.online  
- **版本**：`1.0.0`（见 `version.json`）

---

## 功能概览

- 多地图世界（花园、沙漠、海洋、丛林、冥界、世界等）  
- 花瓣装备、背包、图鉴与掉落系统  
- 局内聊天、小地图、Boss 条等交互  
- Web 管理后台（刷怪、稀有度区域、玩家与运维管理）  
- 客户端版本检测（版本过旧时提示 **Ctrl+F5** 强制刷新缓存）

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

首次启动会交互式创建管理员账号，并自动生成：

- `data/admin.json` — 管理员凭据  
- `data/server-config.json` — 模式、管理后台路径等  

启动成功后访问：

| 用途 | 地址示例 |
|------|----------|
| 游戏页面 | `http://127.0.0.1:25882/` |
| 管理后台 | `http://127.0.0.1:25882/<你设置的后台路径>` |

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

## 目录结构

```
.
├── index.html           # 游戏入口（版本门 + 加载页）
├── gardn-client.js      # 客户端胶水层（Release 压缩）
├── gardn-client.wasm    # 客户端核心（WASM）
├── gardn-server.js      # 服务端宿主 / API / WS
├── gardn-server.wasm    # 服务端核心（WASM）
├── admin.html           # 管理后台页面
├── start.js             # 启动脚本（首次配置管理员）
├── package.json         # Node 依赖（ws）
├── version.json         # 版本元数据
├── assets/              # 地图与贴图资源
├── data/                # 运行时数据
└── README.md
```

> 本项目基于 Gardn 开发，部分素材来自 M28，遵循 AGPL 3.0 协议。

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

- GitHub：https://github.com/Cheerimy-Studio/Mlorr.online  
- QQ 群：741017717

---

## 许可证与免责

- 以本仓库根目录 **LICENSE**（若有）为准；若无，权利默认归作者 / Cheerimy Studio 所有，未经许可不得声称「已获完整源码授权」。  
- 本发行包按「现状」提供，作者不对部署安全、数据丢失或第三方滥用承担责任。  
- 请合法合规运营，切勿将默认口令或后台路径暴露在公网而不更改。

---

## 项目预览

[预览入口](http://mlorr.online)

*Mlorr.online V1.0*
