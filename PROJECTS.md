# Phocinae project map and README policy

Last reviewed: 2026-10-20.

Discovery: `dsh-phocinae` is on dshfind; `dsh-batch-triage`, `dsh-context-verdict` and `dsh-evidence` received the `dsh-plugin`, `deepseek-harness`, `dsh` and `cordis-plugin` topics on 2026-10-20, so the next dshfind (02:17 UTC) and dsh.market (06:00 local) syncs can pick them up. `dsh-phocinae-screen` stays out of the listings because it is explicitly not for release.

## Status

| Project | Kind | README | Status / action |
|---|---|---|---|
| `Phocinae-Largha-150M-v1` | model | model card | Keep as source of weights; link from every tool. |
| `phocinae-server` | inference server | install + API | Active. |
| `phocinae-guard` | approval gate | install + usage | Active. |
| `phocinae-rulepack` | deterministic rules | install + API | Active. |
| `phocinae-publish-gate` | pre-publication checks | install added | Active. |
| `phocinae-mcp` | MCP server | local-build install added | Active; explicit that this is the local enhanced build. |
| `phocinae-cli` | CLI | install + usage | Active. |
| `phocinae-js` | TypeScript client | install + API | Active. |
| `phocinae-formulate` | measurement harness | install + method | Active; research tool. |
| `dsh-phocinae` | DSH plugin | **rewritten** | Flagship. Quick start, examples, config, security, rc.2 range. |
| `dsh-batch-triage` | DSH plugin | quick start added | Active. |
| `dsh-context-verdict` | DSH plugin | quick start added | Active. |
| `dsh-evidence` (package `dsh-preclaim`) | DSH plugin | quick start added | Active; clarify the repo/package naming at the top. |
| `dsh-phocinae-screen` | measurement harness | status banner | **NOT FOR RELEASE**; keep unpublished. |
| `codebuddy-phocinae` | CodeBuddy plugin | install + hooks | Active. |
| `codebuddy-marketplace` | CodeBuddy market | install | Active. |
| `workbuddy-phocinae` | WorkBuddy connector | install + skills | Active. |
| `models.dev` | upstream fork | upstream README | Do not rewrite; track upstream. |
| `every_eval_ever` | upstream/research | upstream README | Do not rewrite; track upstream. |
| `.github` | org profile | updated | Project map + correct DSH install commands. |

## README standard

Every active project should answer, in this order:

1. **What is it?** One sentence, no acronyms on first use.
2. **Quick start.** The shortest command that produces a result, at the top.
3. **What you get.** Three to five concrete surfaces, not marketing.
4. **Examples.** One detailed input/output; then short cases if useful.
5. **How it works.** Only the parts a user must trust.
6. **Configuration.** Keys with defaults.
7. **Security / limits.** What it does not do, and what is local.
8. **Compatibility.** Node/Python/DSH ranges.
9. **Troubleshooting.** The three failures users actually hit.
10. **License.**

Rules:

- No synthetic demo as the hero. Label any illustrative output as “shape”.
- Pin DSH plugin versions in install commands; a bare add can hit pnpm's
  `minimumReleaseAge` and resolve an older build.
- Keep the family install syntax consistent:
  `dsh plugin --profile web add <package>@<version>`.
- Do not advertise `npm install <dsh-plugin>` as installation; it does not mount
  the plugin in a DSH profile.

## Priority

1. `dsh-phocinae` — flagship, rewritten; keep examples current.
2. `dsh-batch-triage`, `dsh-context-verdict`, `dsh-evidence` — next visible
   DSH plugins; quick starts added; add one real example each next.
3. Tool stack (`server`/`guard`/`mcp`/`cli`/`js`) — keep install and exit-code
   contracts aligned.
4. `dsh-phocinae-screen` — do not publish; link the negative result.
5. `models.dev`, `every_eval_ever` — upstream; do not fork READMEs.
