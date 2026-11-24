# DIYNow agent kit

DIYNow 的只读 MCP 服务和申请全流程 skill：按官网出处查 2027 年入学的硕士项目资料，核对硬性条件，排截止日期和材料清单，写文书，辅助填写网申。提交由你本人完成。

这个仓库由 DIYNow 主仓库的 `apps/agent/pack.mjs --plugin` 生成，不要直接修改。完整安装说明：<https://diynow.life/agent/>

## 安装

Claude Code（MCP 服务和 skill 一起装）：

```
/plugin marketplace add Ethereal49/diynow-agent
/plugin install diynow@diynow
```

Codex（装好后开新会话）：

```
codex plugin marketplace add Ethereal49/diynow-agent
codex plugin add diynow@diynow
```

Claude 网页版和桌面版：左侧栏 Plugins → Add → Add marketplace → Add from a repository，填 `Ethereal49/diynow-agent` 并 Sync；搜索 DIYNow 并 Add；在 Connectors 一栏选 Connect，认证选 No sign-in。

WorkBuddy：在插件市场选“添加市场”，填 `Ethereal49/diynow-agent`，再安装 DIYNow。

只装 skill（Claude Code、Codex、Cursor、Gemini CLI、Trae 等，命令会让你选）：

```
npx skills add https://diynow.life
```

只接 MCP 服务：在支持远程 MCP 的客户端里添加 `https://diynow.life/mcp`（Streamable HTTP，不需要账号或密钥）。ChatGPT、豆包工作、Cursor、VS Code、Grok 等各自的步骤见 <https://diynow.life/agent/>。

## 内容

- `plugins/diynow/`：插件。`skills/diynow-apply/SKILL.md` 是申请全流程 skill。`plugin.json` 和 `mcp.json` 给 Agent Plugins 1.0 客户端（含 Codex），`.claude-plugin/plugin.json` 和 `.mcp.json` 给 Claude Code 和 claude.ai，`.codex-plugin/plugin.json` 给旧版 Codex；它们都指向只读 MCP 服务 `https://diynow.life/mcp`。
- `.claude-plugin/marketplace.json`：Claude Code、Claude、WorkBuddy 读的插件市场；`.cursor-plugin/marketplace.json` 内容相同，给 Cursor。`.agents/plugins/marketplace.json`：Codex 插件市场。
- `server.json`：MCP 官方目录的登记信息；改动后由 `.github/workflows/publish-mcp.yml` 发布。

服务只读，不接收也不保存个人材料或身份信息。skill 把申请记录写在你自己电脑的 `applications/` 目录；签字、付款和提交由你本人完成。
