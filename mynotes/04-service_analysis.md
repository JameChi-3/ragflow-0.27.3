# 开启的服务分析

## 开启后端服务

[后端启动脚本](../docker/launch_backend_service.sh)

我们在运行后端启动脚本命令
```shell
bash docker/launch_backend_service.sh
```
做了这些事情

运行了的shell函数

| shell函数 | 函数功能说明 | 实际命令 |
| - | - | - |
| ensure_db_init | 确保数据库已经插入了表格和字段 | |
| run_migrations |   | |
| task_exe | 运行[task_executor.py](../rag/svr/task_executor.py) | `python3 rag/svr/task_executor.py` |
| run_server | 运行[ragflow_server.py](../api/ragflow_server.py) | `python3 api/ragflow_server.py` |


## Task Executor 解析

任务处理调度程序调用到具体的任务处理函数的架构说明[task_executor_refactoring_plan.md](../rag/svr/task_executor_refactor/task_executor_refactoring_plan.md)

<!-- TODO 通过上述的文档，找出真实的调用处理逻辑，进行单独的评测 -->
