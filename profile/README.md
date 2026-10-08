<p align="center">
  <img src="https://huggingface.co/Phocinae/Phocinae-Largha-150M-v1/resolve/main/figures/logo_phocinae.png" width="140" alt="Phocinae logo"/>
</p>

<h1 align="center">小海豹，大决断。<br/><sub>Tiny model. Big decisions.</sub></h1>

<p align="center">
  <b>Phocinae</b>（海豹亚科）是一族本地 typed decision 模型与工具：BERT 系 System 1 引擎，
  以结构化输出（choice / score / noul）替代 LLM 自由文本做决策——0 token、不联网、数据不出本机，
  毫秒级延迟（RTX 5090 fp16 实测 18.6ms/决策），同参数级公开 typed-decisions 最高分（en 0.797 / zh 0.789）。
</p>

## 模型 Models

| 仓库 | 说明 |
|---|---|
| [Phocinae-Largha-150M-v1](https://github.com/Phocinae/Phocinae-Largha-150M-v1) | 斑海豹：144.3M 中英双语 typed decision 模型（Apache-2.0），GitHub / Hugging Face / ModelScope 同步分发 |

## 工具 Tools

| 仓库 | 说明 |
|---|---|
| [phocinae-server](https://github.com/Phocinae/phocinae-server) | 本地推理服务，TypeSafe System One 兼容协议 `/v1/systemone` |
| [phocinae-guard](https://github.com/Phocinae/phocinae-guard) | 命令/工具调用审批门（fail-closed，deny 默认） |
| [phocinae-mcp](https://github.com/Phocinae/phocinae-mcp) | MCP server：gate / classify / route / score |
| [dsh-phocinae](https://github.com/Phocinae/dsh-phocinae) | DeepSeek Harness（dsh）本地审批门插件 |
| [codebuddy-phocinae](https://github.com/Phocinae/codebuddy-phocinae) | CodeBuddy 决策插件 |
| [workbuddy-phocinae](https://github.com/Phocinae/workbuddy-phocinae) | WorkBuddy 决策插件 |

## 链接 Links

- Model card: [huggingface.co/Phocinae/Phocinae-Largha-150M-v1](https://huggingface.co/Phocinae/Phocinae-Largha-150M-v1)
- ModelScope: [modelscope.cn/models/PerryLink/Phocinae-Largha-150M-v1](https://modelscope.cn/models/PerryLink/Phocinae-Largha-150M-v1)
- PyPI: [phocinae-server](https://pypi.org/project/phocinae-server/) · [phocinae-guard](https://pypi.org/project/phocinae-guard/) · [phocinae-mcp](https://pypi.org/project/phocinae-mcp/)
- npm: [dsh-phocinae](https://www.npmjs.com/package/dsh-phocinae)

*一斑见全豹，一点定全局。*
