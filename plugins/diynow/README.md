# DIYNow

DIYNow helps Chinese-speaking applicants with master's applications for 2027 entry. This plugin adds a read-only MCP connector and one skill.

- **Connector `diynow`**: https://diynow.life/mcp (Streamable HTTP, no sign-in). Six read-only tools search DIYNow's published programme data: coverage, programme search, one programme's facts, hard-requirement checks, deadlines and school profiles. Every fact comes with its official source link and whether the official page states it for 2027 entry.
- **Skill `diynow-apply`**: guides the application step by step: the applicant's background, a shortlist, requirement checks, a timeline, document checklists, essays, help with online forms, and follow-up. The applicant signs, pays and submits.

## What the plugin sends and keeps

- Tool calls send only search words, region, school and programme ids and, for requirement checks, the IELTS score and budget the user gives. There is no account; no name, email, identity document or application file is sent.
- DIYNow does not log or keep tool calls. The site and the MCP server run on Cloudflare, which processes the client's IP address to deliver requests, block attacks and rate-limit.
- The skill keeps the applicant's notes in an `applications/` folder in the user's own workspace and does not send them to DIYNow. It uploads a file only to an official university application portal, and only when the user asks.
- The plugin runs no local commands, hooks or scripts.

Privacy: https://diynow.life/agent/#privacy · Install guide: https://diynow.life/agent/ · Contact: contact@diynow.life · License: MIT

## 中文说明

DIYNow 帮中文申请者准备 2027 年入学的硕士申请。插件包含只读 MCP 连接器 `diynow`（https://diynow.life/mcp，不需要登录）和申请全流程 skill `diynow-apply`。工具调用只发送搜索词、地区、学校和项目编号，以及核对条件时你给出的语言成绩和预算；DIYNow 不记录调用内容。skill 把申请记录写在你自己的工作目录 `applications/`；签字、付款和提交由你本人完成。
