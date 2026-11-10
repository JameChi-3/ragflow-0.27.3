# RagFlow API Doc

`api/` 中与网页交互的接口，主要集中在 [api/apps/restful_apis](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis)。这些路由统一注册到 `/api/v1`；前端的接口地址集中写在 [web/src/utils/api.ts](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/web/src/utils/api.ts:18)，再由 `services` 和 `hooks` 供页面调用。

| 网页功能 | 主要接口示例 | Python 路由文件 |
|---|---|---|
| 登录、注册、个人设置 | `POST /auth/login`、`GET/PATCH /users/me` | [user_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/user_api.py:62) |
| 团队管理 | `GET /tenants`、`GET/POST/DELETE /tenants/{id}/users` | [tenant_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/tenant_api.py:41) |
| 模型设置 | `GET /models`、`GET /providers`、模型实例的增删改查 | [provider_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/provider_api.py:31) |
| 知识库 | `GET/POST/DELETE /datasets`、`GET/PUT /datasets/{id}` | [dataset_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/dataset_api.py:82) |
| 文档上传与解析 | `/datasets/{id}/documents`、`POST /documents/ingest`、`POST /datasets/{id}/documents/parse` | [document_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/document_api.py:442) |
| 分块与检索测试 | `/datasets/{id}/documents/{doc_id}/chunks`、`POST /datasets/search` | [chunk_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/chunk_api.py:391) |
| 聊天与会话 | `/chats`、`/chats/{id}/sessions`、`POST /chat/completions` | [chat_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/chat_api.py:417) |
| Agent 工作流 | `/agents`、`/agents/{id}/versions`、`POST /agents/chat/completions` | [agent_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/agent_api.py:719) |
| 文件管理、数据源 | `/files`、`/connectors` | [file_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/file_api.py:45)、[connector_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/connector_api.py:49) |
| 搜索、记忆、MCP | `/searches`、`/memories`、`/mcp/servers` | [search_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/search_api.py:43)、[memory_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/memory_api.py:30)、[mcp_api.py](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/api/apps/restful_apis/mcp_api.py:72) |

一次典型调用是：**页面 → `web/src/hooks` → `web/src/services` → `/api/v1/...` → `api/apps/restful_apis`**。例如聊天页通过 [use-chat-request.ts](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/web/src/hooks/use-chat-request.ts:108) 调用 [next-chat-service.ts](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/web/src/services/next-chat-service.ts:39)；生成回复时，前端向 `POST /api/v1/chat/completions` 发请求并读取流式结果，见 [chat-completion-stream.ts](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/web/src/services/chat-completion-stream.ts:62)。

**范围提醒：**网页同时支持 Python 和 Go 后端，开发代理也可选 `python`、`hybrid`、`go`，见 [vite.config.ts](/home/cjw/source/ragflow.v0.27.3/ragflow-0.27.3/web/vite.config.ts:58)。因此 `web/src/utils/api.ts` 中的地址不一定全部由 Python `api/` 实现；它还包含少量 `/v1/...` 路径。
