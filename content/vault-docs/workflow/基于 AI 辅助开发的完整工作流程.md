# 基于 AI 辅助开发的完整工作流程（需求到上线）

传统开发流程往往耗时数月，而在当前 AI 编程助手（如 Cursor、Windsurf、Claude Code）、AI 设计工具及自动化运维成熟的背景下，现代团队普遍采用**“AI 驱动的端到端敏捷工作流”**。个人或小团队甚至可以在几天内走完完整闭环。

## 第 1 阶段：商业与市场探索（替代传统繁重的 BRD/MRD）

- **AI 竞品与市场调研**：利用具备深度研究（Deep Research）能力的 AI 工具，自动抓取竞品评论、行业报告与用户痛点，快速生成结构化的市场机会分析报告。
- **MVP 范围界定**：将商业构想输入大模型，要求其扮演资深产品总监，利用“MoSCoW 法则”（必须有、应该有、可以有、暂不做）对功能进行剪裁，锁定最小可行性产品（MVP）的核心功能闭环。

## 第 2 阶段：AI 辅助产品设计与结构化 PRD 生成

- **生成高保真交互原型（UI/UX）**：跳过繁琐的线框图绘制。直接使用 [v0](https://www.google.com/url?sa=i&source=web&rct=j&url=https://v00.ai/&ved=2ahUKEwjT6calk46YAxWTcPUHHbg5Fr0Qy_kOegYIAAgXEAA&opi=89978449&cd&psig=AOvVaw3aH-_H4ppLs4_8S0Z4MaM9&ust=1794975591944000)、[Bolt.new](https://www.google.com/url?sa=i&source=web&rct=j&url=http://Bolt.new&ved=2ahUKEwjT6calk46YAxWTcPUHHbg5Fr0Qy_kOegYIAAgYEAA&opi=89978449&cd&psig=AOvVaw3aH-_H4ppLs4_8S0Z4MaM9&ust=1794975591944000)、[Lovable](https://www.google.com/url?sa=i&source=web&rct=j&url=https://docs.lovable.dev/features/ai&ved=2ahUKEwjT6calk46YAxWTcPUHHbg5Fr0Qy_kOegYIAAgWEAA&opi=89978449&cd&psig=AOvVaw3aH-_H4ppLs4_8S0Z4MaM9&ust=1794975591944000) 或 Figma AI 插件，通过自然语言描述界面需求，一键生成具备响应式布局的前端交互原型与视觉设计稿。
- **撰写“AI 友好型”PRD**：现代 PRD 不再是给人类看的千字长文，而是兼顾研发与 AI 编程工具的**结构化提示词文档（通常为 Markdown 格式）**。产品经理利用 AI 生成包含数据模型（Schema）、接口契约（API Spec）、状态流转和边界条件的技术规格说明书。

## 第 3 阶段：技术架构设计与环境搭建

- **系统架构选型**：与 AI 架构师对话，根据业务并发量和开发速度要求确定技术栈（例如全栈 Next.js + Supabase + Tailwind CSS），并让 AI 直接输出项目目录结构图和数据库建表 SQL 语句。
- **编写项目规则文件（Rules）**：在代码仓库根目录配置 `.cursorrules` 或 [CLAUDE.md](https://www.google.com/url?sa=i&source=web&rct=j&url=http://CLAUDE.md&ved=2ahUKEwjT6calk46YAxWTcPUHHbg5Fr0Qy_kOegYIAAgcEAA&opi=89978449&cd&psig=AOvVaw3aH-_H4ppLs4_8S0Z4MaM9&ust=1794975591944000) 等上下文规范文件，明确代码风格、命名规范、安全红线和组件库限制，确保后续 AI 生成的代码高度一致。

## 第 4 阶段：AI 结对编程与功能实现（核心开发期）

- **上下文驱动开发（Context-Driven Development）**：开发者不再逐行敲代码，而是作为“代码审查员与架构指挥官”。在 [Cursor](https://www.google.com/url?sa=i&source=web&rct=j&url=https://cursor.com/&ved=2ahUKEwjT6calk46YAxWTcPUHHbg5Fr0Qy_kOegYIAAggEAA&opi=89978449&cd&psig=AOvVaw3aH-_H4ppLs4_8S0Z4MaM9&ust=1794975591944000) 或 Claude Code 等工具中，引入第 2 步生成的 Markdown 版 PRD 和数据库 Schema 作为上下文。
- **模块化渐进生成**：按照“数据库层 -> 后端 API 接口 -> 前端 UI 绑定 -> 业务逻辑联调”的顺序，指令 AI 分模块生成代码。每完成一个微小模块，立即在本地运行验证。

## 第 5 阶段：自动化测试与 AI 代码审查（QA 与安全）

- **自动生成测试用例**：要求 AI 针对核心业务逻辑（尤其是支付、权限、边界异常）自动编写单元测试（Unit Test）和端到端测试脚本（如 Playwright）。
- **AI 静态代码审查与排错**：在提交代码前，利用 AI PR Review 工具（如 CodeRabbit）自动扫描潜在的内存泄漏、SQL 注入风险、逻辑漏洞及性能瓶颈，并直接采纳 AI 给出的修复补丁（Diff）。

## 第 6 阶段：CI/CD 自动化部署与云端上线

- **基础设施即代码（IaC）**：让 AI 编写 `Dockerfile`、Docker Compose 或 GitHub Actions 工作流配置文件，实现代码推送到主分支后自动触发构建与测试。
- **无服务器（Serverless）一键托管**：利用 Vercel、Cloudflare Pages、Railway 或现代云平台进行部署。环境变量配置、HTTPS 证书签发、CDN 全球加速及数据库迁移均通过自动化流水线完成。

## 第 7 阶段：上线监控与 AI 驱动的迭代闭环

- **智能日志分析与告警**：接入监控工具（如 Sentry），当线上出现报错时，AI 自动聚合错误堆栈日志，定位导致 Bug 的具体代码行，甚至直接生成修复 Pull Request 等待人工确认合并。
- **用户反馈闭环**：利用 AI 自动分类整理上线后收集到的用户反馈与埋点数据，提炼出下一阶段的高优先级需求，重新进入第 2 阶段开启新一轮版本迭代。


# 全流程各阶段核心输出产物清单

|开发阶段|核心输出产物（Deliverables）|常见文件格式|对后端/全栈开发的实际价值|
|---|---|---|---|
|**1. 商业与市场探索**  <br>_(BRD / MRD)_|**1. 商业立项与可行性报告（BRD）**  <br>**2. 市场调研与竞品分析报告（MRD）**  <br>**3. MVP 功能范围剪裁清单（MoSCoW 表）**|`.md` / `.pdf` / 飞书文档|明确“**不做什么**”，防止在开发过程中无限加需求导致项目烂尾，锁定第一版最小闭环。|
|**2. 产品设计**  <br>_(UI / 原型 / PRD)_|**1. 高保真交互原型图（UI 设计稿）**  <br>**2. 前端切图资源与样式代码片段**  <br>**3. AI 友好型产品需求文档（PRD）**  <br>**4. 业务状态流转图（Swimlane / 状态机）**|即时设计链接 / `.png` / `.md` / Mermaid 图表|**设计稿直接转代码**，省去自己调 CSS/WXSS 样式的时间；状态机图表让后端写状态流转逻辑时绝不漏掉边界条件。|
|**3. 架构与环境**  <br>_(数据库 / 规范)_|**1. 系统技术架构图与技术栈选型说明**  <br>**2. 数据库 ER 图与建表 DDL 脚本**  <br>**3. API 接口契约规范（OpenAPI / Swagger）**  <br>**4. Trae 专属上下文规范文件（Project Rules）**|`.sql` / `.yaml` / `.json` / `.trae/rules`|**核心基石**：数据库表结构和 `.trae/rules` 一旦定死，后续让 Trae 生成的所有增删改查和大数据聚合代码都会高度规范、零幻觉。|
|**4. 编码与联调**  <br>_(前后端开发)_|**1. 后端微服务/API 源码与大数据处理脚本**  <br>**2. 微信小程序前端页面与组件源码**  <br>**3. Apifox 在线接口文档与 Mock 数据集**  <br>**4. 本地环境配置文件（环境变量模板）**|源码仓库（Git） / `.env.example` / Apifox 项目|形成可在本机和微信开发者工具中完整跑通的 **MVP 源码包**，同时沉淀下标准化的接口调试集合。|
|**5. 测试与代码审查**  <br>_(QA / 压测 / 安全)_|**1. 后端核心接口单元测试脚本**  <br>**2. Apifox 自动化接口测试用例集与测试报告**  <br>**3. 接口并发压测报告（QPS / 响应耗时）**  <br>**4. AI 静态代码安全与漏洞扫描报告**|`_test.go` / `.py` / `.html` 测试报告|确保大数据查询接口不会在并发稍高时拖垮数据库，修复 SQL 注入、越权访问等安全隐患。|
|**6. 线上部署与运维**  <br>_(云端上线)_|**1. 容器化打包配置文件（Dockerfile / Compose）**  <br>**2. CI/CD 自动化部署流水线脚本**  <br>**3. 线上生产环境配置（域名、SSL 证书、Nginx 配置）**  <br>**4. 微信小程序提审包与合规隐私协议文档**|`Dockerfile` / `docker-compose.yml` / `.conf`|实现“**一键打包上线**”，彻底脱离本机环境依赖；拿到合法 HTTPS 域名，顺利通过微信官方审核发布。|
|**7. 监控与迭代**  <br>_(日志 / 数据分析)_|**1. 线上运行监控大盘与异常告警规则**  <br>**2. 线上 Bug 堆栈分析与热修复补丁（Hotfix）**  <br>**3. 核心业务数据指标看板（留存、转化、报错率）**  <br>**4. V1.1 下一版本迭代需求池（Backlog）**|监控面板配置 / SQL 看板 / `.md` 需求池|利用你的大数据优势，用真实线上数据驱动下一轮开发，而不是靠拍脑袋决定新功能。|

---

## 给独立开发者的“极简必留产物”建议

如果你目前是**单人或极小团队**推进这个项目，不需要像大厂那样写满所有文档，建议重点沉淀以下 **5 份核心数字资产**（全部放进你的 Git 仓库里即可）：

1. **`docs/`**PRD.md（需求与业务状态机说明书）
2. **`.trae/rules`**（让 Trae 懂你技术栈和代码规范的“紧箍咒”）
3. **`sql/schema.sql`**（完整的数据库与数仓建表语句）
4. **`apifox-export.json`**（随时可导入重现的前后端联调接口与测试用例）
5. **`docker-compose.yml`**（包含后端、数据库、Redis、Nginx 的一键云端部署编排文件）

