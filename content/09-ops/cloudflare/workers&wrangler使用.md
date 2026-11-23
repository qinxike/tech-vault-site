# wrangler使用

**Cloudflare Workers** 是运行在 Cloudflare 全球边缘节点的无服务器计算平台，支持 JavaScript、TypeScript、Python 及 WebAssembly（如 Rust、Go），免费版每天提供 10 万次请求额度。
## 使用方式

###  方式一：网页后台快速部署

- 登录 [Cloudflare Workers](https://www.google.com/url?sa=i&source=web&rct=j&url=https://www.cloudflare.com/zh-cn/developer-platform/products/workers/&ved=2ahUKEwjqhcPbz5uYAxVaqFYBHUBbBAUQy_kOegoIAggACAAIDhAD&opi=89978449&cd&psig=AOvVaw2eZWojnpZV_nk7dDB1IW7J&ust=1795438487806000) 控制台并注册/登录账号。
- 点击 **Create application**（建立应用程式），选择基础模板或连接 Git 仓库。
- 在在线编辑器中编写或粘贴代码，点击 **Deploy**（部署）即可获得默认的 `*.workers.dev` 访问地址。
### 方式二：本地 CLI（Wrangler）开发部署

适合需要版本控制与本地调试的项目：
- **安装工具**：确保已安装 Node.js，执行 `npm install -g wrangler`。
- **登录账号**：运行 `wrangler login`，在浏览器中完成授权。
- **初始化项目**：运行 `npm create cloudflare@latest` 或 `wrangler init my-worker`，按提示选择模板与语言。
- **本地调试**：在项目目录执行 `npx wrangler dev`（或 `wrangler dev`）进行本地预览。
- **发布上线**：执行 `npx wrangler deploy` 将代码部署到全球边缘节点。

## 安装wrangler
npm install -g wrangler
