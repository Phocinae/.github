<p align="center">
  <img src="https://huggingface.co/Phocinae/Phocinae-Largha-150M-v1/resolve/main/figures/logo_phocinae.png" width="140" alt="Phocinae logo"/>
</p>

<h1 align="center">小海豹，大决断。<br/><sub>Tiny model. Big decisions.</sub></h1>

<p align="center">
  <b>Phocinae</b>（海豹亚科）是一族本地 typed decision 模型与工具：BERT 系 System 1 引擎，
  以结构化输出（choice / score / noul）替代 LLM 自由文本做决策——0 token、不联网、数据不出本机，
  毫秒级延迟（RTX 5090 fp16 实测 21.0ms/决策），同参数级公开 typed-decisions 最高分（en 0.906 / zh 0.848，zh 为机译用例）。
</p>

## 模型 Models

| 仓库 | 说明 |
|---|---|
| [Phocinae-Largha-150M-v1](https://github.com/Phocinae/Phocinae-Largha-150M-v1) | 斑海豹：144.3M 中英双语 typed decision 模型（Apache-2.0），GitHub / Hugging Face / ModelScope 同步分发 |

## 工具 Tools

**推理服务与审批内核**

| 仓库 | 说明 | 安装 |
|---|---|---|
| [phocinae-server](https://github.com/Phocinae/phocinae-server) | 本地推理服务，TypeSafe System One 兼容协议 `/v1/systemone` | `pip install phocinae-server` |
| [phocinae-guard](https://github.com/Phocinae/phocinae-guard) | 命令审批门：L0 离线确定性表先定夺、灰区才问模型，**fail-closed** | `pip install phocinae-guard` |
| [phocinae-mcp](https://github.com/Phocinae/phocinae-mcp) | MCP server：`gate` / `classify` / `route` / `score`，双代协议（2026-07-28 + 2024-11-05） | `pip install phocinae-mcp` |

**客户端与 SDK**

| 仓库 | 说明 | 安装 |
|---|---|---|
| [phocinae-cli](https://github.com/Phocinae/phocinae-cli) | 一行命令本地决策：`decide` / `classify` / `route` / `score` / `gate` / `ping`；退出码即判定（allow=0 / deny=2 / ask=3） | `pip install phocinae-cli` |
| [phocinae-js](https://github.com/Phocinae/phocinae-js) | TypeScript 客户端，零运行时依赖，内置与 guard 同源的 L0 离线放行门 | `npm install @phocinae/js` |

**Harness / IDE 插件**

| 仓库 | 说明 | 装法 |
|---|---|---|
| [dsh-phocinae](https://github.com/Phocinae/dsh-phocinae) | DeepSeek Harness 插件：`phocinae_ask` / `phocinae_gate` 工具 + PreToolUse 审批门 | `npm install dsh-phocinae` |
| [codebuddy-phocinae](https://github.com/Phocinae/codebuddy-phocinae) | 腾讯 CodeBuddy 插件：PreToolUse 硬闸门 + 决策技能 | `/plugin install codebuddy-phocinae@phocinae-codebuddy-marketplace` |
| [codebuddy-marketplace](https://github.com/Phocinae/codebuddy-marketplace) | CodeBuddy 自建市场清单（先 add 本仓，再装上面的插件） | `/plugin marketplace add Phocinae/codebuddy-marketplace` |
| [workbuddy-phocinae](https://github.com/Phocinae/workbuddy-phocinae) | 腾讯 WorkBuddy 连接器 + 技能包：文档分类 / 审批预判 / 任务路由 / 质量 gate | 见仓库 README |

## 链接 Links

- Model card: [huggingface.co/Phocinae/Phocinae-Largha-150M-v1](https://huggingface.co/Phocinae/Phocinae-Largha-150M-v1)
- ModelScope: [modelscope.cn/models/PerryLink/Phocinae-Largha-150M-v1](https://modelscope.cn/models/PerryLink/Phocinae-Largha-150M-v1)
- PyPI: [phocinae-server](https://pypi.org/project/phocinae-server/) · [phocinae-guard](https://pypi.org/project/phocinae-guard/) · [phocinae-mcp](https://pypi.org/project/phocinae-mcp/) · [phocinae-cli](https://pypi.org/project/phocinae-cli/)
- npm: [dsh-phocinae](https://www.npmjs.com/package/dsh-phocinae) · [@phocinae/js](https://www.npmjs.com/package/@phocinae/js)
- MCP Registry: [`io.github.Phocinae/phocinae-mcp`](https://registry.modelcontextprotocol.io/v0/servers?search=phocinae)

## 安全取舍 Security posture

- **审批门默认 fail-closed**：服务不可达、应答异常、解释器缺失 —— 一律阻断，绝不静默放行。
- **确定性优先**：常见危险命令由离线表毫秒级拦下；150M 权重未做命令审批域校准，因此模型只用于灰区。
- **全程本机**：服务默认只监听 `127.0.0.1`；判定状态含工具输出原文，故不鼓励暴露到网络。
