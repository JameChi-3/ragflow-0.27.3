# 文档预览目录

本页是仓库 `docs/` 的中文导览。原有 **118 篇** Markdown/MDX 正文（不含本预览页）；`_category_.json` 用于文档站侧边栏分类，不是正文。下方链接指向仓库内的原文，原文主要是英文。

## 这套文档写了什么

| 范围 | 内容 |
| --- | --- |
| 起步与概念 | Docker 快速启动、RAG 原理、Agent Context Engine、FAQ 和版本记录。 |
| 用户操作 | 模型、知识库与文档解析、检索、Chat、Search、Agent、流水线、知识编纂、记忆、数据源、聊天渠道和团队权限。 |
| 运维管理 | 服务配置、SSL、沙箱、管理员界面与 CLI、备份迁移、升级、追踪。 |
| 开发集成 | 源码启动、镜像构建、MCP、HTTP/Python API 和术语表。 |

## 建议如何看

1. **首次使用**：先读[快速开始](quickstart.mdx)，按“启动服务 → 配置模型 → 创建知识库 → 检查解析 → 建立 Chat”做一遍；概念不清楚时补看 [RAG 基础](basics/rag.md)。
2. **做知识库问答**：接着读[知识库概览](guides/dataset/dataset_overview.md)和[召回测试](guides/dataset/retrieval_testing.md)，再按用途选择 [Chat](guides/chat/feature_overview_and_creation.md)、[Search](guides/search/create_search.md) 或 [Agent](guides/agent/agent_overview.md)。
3. **接外部内容或加工结构化知识**：分别从[数据源概览](guides/data_source/overview_and_page_management.md)、[数据摄取流水线](guides/agent/ingestion_pipeline/create_ingestion_pipeline.md)和[知识编纂概览](guides/knowledge_compilation/overview.md)进入。
4. **部署与排障**：看[配置](administrator/configurations/configurations.md)、[升级](administrator/upgrade_ragflow.mdx)、[备份迁移](administrator/migration/backup_and_migration.md)及 [FAQ](faq.mdx)。
5. **开发集成**：从[源码启动](develop/launch_ragflow_from_source.md)、[获取 API Key](develop/acquire_ragflow_api_key.md)开始，再查 [HTTP API](references/http_api_reference.md)、[Python API](references/python_api_reference.md)或 [MCP 概览](develop/mcp/overview.md)。

可在仓库浏览器或支持 Markdown 的编辑器中打开本页并点击链接。`.mdx` 文件含文档站专用组件；需要完整的标签页等效果时，在对应文档站页面查看。截图多引用外部图片地址，本地预览需能访问这些地址。下面列出全部正文文件，按主题分组。

## 全量目录

### 起步（3 篇）

快速安装、常见问题和版本变化。

- [Quickstart](quickstart.mdx)
- [FAQs](faq.mdx)
- [Releases](release_notes.md)

### 基础概念（2 篇）

RAG 的处理链路，以及 Agent Context Engine 的定位。

- [What Is Retrieval-Augmented Generation (RAG)?](basics/rag.md)
- [What Is Agent Context Engine?](basics/agent_context_engine.md)

### 用户指南 · 知识库（10 篇）

创建知识库、配置解析、管理文档与切片、元数据、召回测试、日志。

- [Dataset Overview](guides/dataset/dataset_overview.md)
- [Dataset List and Creation](guides/dataset/dataset_list_and_creation.md)
- [Configuration](guides/dataset/configuration.md)
- [Files: Dataset Document Management](guides/dataset/files_dataset_document_management.md)
- [Chunk: Parsing Results and Knowledge Fragment Management](guides/dataset/chunk_parsing_results_and_knowledge_fragment_management.md)
- [Metadata: Metadata Management](guides/dataset/metadata_management.md)
- [Retrieval Testing: Retrieval Test](guides/dataset/retrieval_testing.md)
- [Artifacts: Knowledge Artifact Generation and Management](guides/dataset/artifacts_knowledge_artifact_generation_and_management.md)
- [Logs: Logs](guides/dataset/logs.md)
- [Notes and FAQs](guides/dataset/notes_and_faqs.md)

### 用户指南 · 知识库实践（1 篇）

加快文档索引的实践建议。

- [Accelerate Indexing](guides/dataset/best_practices/accelerate_doc_indexing.mdx)

### 用户指南 · 模型（3 篇）

模型供应商、API Key 与本地模型部署。

- [Configure Model API Key](guides/models/llm_api_key_setup.md)
- [Deploy Local Models](guides/models/deploy_local_llm.mdx)
- [Model Providers](guides/models/supported_models.mdx)

### 用户指南 · Chat（4 篇）

创建和配置聊天助手，使用会话及多模型比较。

- [Feature Overview and Creation](guides/chat/feature_overview_and_creation.md)
- [Using Chat conversations](guides/chat/using_chat_sessions.md)
- [Chat Configuration](guides/chat/chat_configuration.md)
- [Multimodel Comparison & FAQ](guides/chat/Mutimodel_comparison_and_FAQ.md)

### 用户指南 · Search（3 篇）

创建搜索应用、调整检索设置和排查常见问题。

- [Create a Search](guides/search/create_search.md)
- [Search Settings](guides/search/search_settings.md)
- [FAQ](guides/search/faq.md)

### 用户指南 · Agent（5 篇）

Agent 的用途、创建、画布使用、导入导出及网页嵌入。

- [Agent Overview](guides/agent/agent_overview.md)
- [Creation and Management](guides/agent/creation_and_management.md)
- [Import and Export Agents](guides/agent/import_and_export_agents.md)
- [Embed into Web Pages](guides/agent/embed_into_web_pages.md)
- [Understand the Canvas](guides/agent/understand_the_canvas.md)

### 用户指南 · Agent 工作流组件（5 篇）

基础、对话、流程、数据处理与工具组件。

- [Basic Component](guides/agent/agent_workflow/basic_component.md)
- [Dialogue Component](guides/agent/agent_workflow/dialogue_component.md)
- [Flow Components](guides/agent/agent_workflow/flow_components.md)
- [Data Manipulation Components](guides/agent/agent_workflow/data_manipulation_components.md)
- [Tool Components](guides/agent/agent_workflow/tool_components.md)

### 用户指南 · 数据摄取流水线（8 篇）

创建和试运行流水线，配置 Parser、Chunker、Transformer、Indexer，并绑定知识库。

- [Understand the Core Ingestion Pipeline Components](guides/agent/ingestion_pipeline/understand_core_ingestion_pipeline_components.md)
- [Create an Ingestion Pipeline](guides/agent/ingestion_pipeline/create_ingestion_pipeline.md)
- [Configure the Parser Component](guides/agent/ingestion_pipeline/configure_parser_component.md)
- [Configure the Chunker Component](guides/agent/ingestion_pipeline/configure_chunker_component.md)
- [Configure the Transformer Component](guides/agent/ingestion_pipeline/configure_transformer_component.md)
- [Configure the Indexer Component](guides/agent/ingestion_pipeline/configure_indexer_component.md)
- [Test Run](guides/agent/ingestion_pipeline/test_run.md)
- [Connect the Pipeline to a Knowledge Base](guides/agent/ingestion_pipeline/connect_the_pipeline_to_a_knowledge_base.md)

### 用户指南 · 知识编纂（6 篇）

用模板和流水线生成图谱、知识树、页面索引、思维导图、时间线与 Wiki 等知识产物。

- [Overview](guides/knowledge_compilation/overview.md)
- [Basic Information Configuration](guides/knowledge_compilation/basic_information_configuration.md)
- [Built-In Templates and Dedicated Configuration](guides/knowledge_compilation/built_in_templates_and_dedicated_configuration.md)
- [Apply a Knowledge Compilation Template](guides/knowledge_compilation/apply_knowledge_compilation_template.md)
- [FAQ](guides/knowledge_compilation/faq.md)
- [Knowledge Compilation Runtime Configuration](guides/knowledge_compilation/runtime_configuration.md)

### 用户指南 · 记忆（4 篇）

创建和配置记忆，查看消息，并连接 Agent。

- [Create Memory](guides/memory/create_memory.md)
- [Message Page](guides/memory/message_page.md)
- [Configure Memory](guides/memory/configure_memory.md)
- [Connect to an Agent](guides/memory/connect_to_an_agent.md)

### 用户指南 · 文件管理（4 篇）

文件夹、上传、移动删除及关联知识库。

- [Files and Folders](guides/file/file.md)
- [File Operations](guides/file/file_operations.md)
- [Link Knowledge Base](guides/file/link_dataset.md)
- [Batch Move and Delete](guides/file/batch_move_and_delete.md)

### 用户指南 · 数据源（4 篇）

连接外部系统、配置同步，并将数据加入知识库。

- [Data Source Overview and Page Management](guides/data_source/overview_and_page_management.md)
- [Add a Data Source to a Knowledge Base and Synchronization and Updates](guides/data_source/add_to_knowledge_base_and_sync.md)
- [Data Source Categories and Selection](guides/data_source/data_source_categories_and_selection.md)
- [Data Source Configuration](guides/data_source/data_source_configuration.md)

### 用户指南 · 聊天渠道（4 篇）

渠道接入、配置和故障排查。

- [Chat Channels Overview](guides/chatchannel/chat_channels_overview.md)
- [Channel Access and Configuration](guides/chatchannel/channel_access_and_configuration.md)
- [Connect Chat](guides/chatchannel/connect_chat.md)
- [FAQ](guides/chatchannel/faq.md)

### 用户指南 · 团队权限（6 篇）

成员身份、共享范围和资源操作权限的规则。

- [Overview](guides/team/permission_system_overview/index.md)
- [Team Member Management](guides/team/permission_system_overview/team_member_management.md)
- [Team and Resource Permissions](guides/team/permission_system_overview/team_and_resource_permissions.md)
- [Resource Sharing Scope](guides/team/permission_system_overview/resource_sharing_scope.md)
- [Resource Operation Permissions](guides/team/permission_system_overview/resource_operation_permissions.md)
- [Permission Effective Rules](guides/team/permission_system_overview/permission_effective_rules.md)

### 用户指南 · 团队管理（10 篇）

邀请、加入、离开团队，查看和移除成员。

- [Enter the Team Page](guides/team/team_management/enter_the_team_page.md)
- [Overview](guides/team/team_management/index.md)
- [View Current Workspace Members](guides/team/team_management/view_current_workspace_members.md)
- [Invite Members](guides/team/team_management/invite_members.md)
- [Remove Members](guides/team/team_management/remove_members.md)
- [View Joined Teams](guides/team/team_management/view_joined_teams.md)
- [Accept or Decline an Invitation](guides/team/team_management/accept_or_decline_an_invitation.md)
- [Leave a Joined Team](guides/team/team_management/leave_a_joined_team.md)
- [Resource Sharing from the Team Perspective](guides/team/team_management/resource_sharing_from_the_team_perspective.md)
- [FAQ](guides/team/team_management/faq.md)

### 用户指南 · 共享范围（5 篇）

配置知识库、Agent、记忆等资源的共享范围。

- [Open-Source Edition Sharing Scope Configuration](guides/team/sharing_scope_configuration/open_source_edition_sharing_scope_configuration.md)
- [Overview](guides/team/sharing_scope_configuration/index.md)
- [Share Knowledge Bases](guides/team/sharing_scope_configuration/share_knowledge_bases.md)
- [Share Agents](guides/team/sharing_scope_configuration/share_agents.md)
- [Share Memories](guides/team/sharing_scope_configuration/share_memories.md)

### 管理员 · 配置（3 篇）

Docker 服务参数、SSL 证书和代码执行沙箱。

- [Configuration](administrator/configurations/configurations.md)
- [Configure SSL Certificates](administrator/configurations/config_ssl_cert.md)
- [Sandbox Quickstart](administrator/configurations/sandbox_quickstart.md)

### 管理员 · 管理界面（4 篇）

管理员账户、系统状态、用户账户和沙箱配置。

- [Before You Begin](administrator/admin/admin_ui/before_you_begin.md)
- [Check System Status](administrator/admin/admin_ui/check_system_status.md)
- [Manage User Accounts](administrator/admin/admin_ui/manage_user_accounts.md)
- [Configure Code Execution Sandbox](administrator/admin/admin_ui/configure_code_execution_sandbox.md)

### 管理员 · 服务与 CLI（2 篇）

启动 Admin Service，并使用 RAGFlow CLI 执行管理操作。

- [Admin Service](administrator/admin/admin_service.md)
- [RAGFlow CLI](administrator/admin/ragflow_cli.md)

### 管理员 · 迁移（3 篇）

备份、数据库结构迁移和版本变更记录。

- [Database Schema and Migration](administrator/migration/database_schema_and_migration.md)
- [Backup & Migration](administrator/migration/backup_and_migration.md)
- [Database Change Log](administrator/migration/database_change_log.md)

### 管理员 · 其他（2 篇）

升级 RAGFlow 和配置链路追踪。

- [Upgrading](administrator/upgrade_ragflow.mdx)
- [Tracing](administrator/tracing.mdx)

### 开发者指南（6 篇）

源码启动、构建镜像、文档引擎切换、贡献流程与 API Key。

- [Explore RAGFlow on DeepWiki](develop/deepwiki.md)
- [Launch Service from Source](develop/launch_ragflow_from_source.md)
- [Switch Document Engine](develop/switch_doc_engine.md)
- [Acquire RAGFlow API Key](develop/acquire_ragflow_api_key.md)
- [Build RAGFlow Docker Image](develop/build_docker_image.mdx)
- [Contribution Guidelines](develop/contributing.md)

### 开发者指南 · MCP（8 篇）

RAGFlow 作为 MCP Server，以及连接外部 MCP Server 的配置、工具和客户端示例。

- [MCP Overview](develop/mcp/overview.md)
- [Use RAGFlow as an MCP Server](develop/mcp/use_ragflow_as_mcp_server.md)
- [Connect an External MCP Server to RAGFlow](develop/mcp/connect_an_external_mcp_to_ragflow.md)
- [Connect external MCP tools](develop/mcp/connect_external_mcp_servers.md)
- [Native Go MCP Runtime](develop/mcp/native_go_mcp.md)
- [Launch RAGFlow MCP Server](develop/mcp/launch_mcp_server.md)
- [RAGFlow MCP Tools](develop/mcp/mcp_tools.md)
- [RAGFlow MCP Client Examples](develop/mcp/mcp_client_example.md)

### 参考资料（3 篇）

HTTP/Python API 的接口说明和术语表。

- [Glossary](references/glossary.mdx)
- [HTTP API](references/http_api_reference.md)
- [Python API](references/python_api_reference.md)
