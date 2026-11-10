# 启动服务和配置

## 开启服务

### 开启后端

```bash
source .venv/bin/activate
export PYTHONPATH=$(pwd)
bash docker/launch_backend_service.sh
```

### 开期网页服务

```bash
cd web
npm run dev
```

### 访问网页

- Local:
  http://localhost:9222/

## 配置模型

### llm api

####  deepseek provider

| 配置   | 配置选项|
| -- | -- |
| 模型 | deepseek-v4-flash |

### embedding model

#### ollama provider

| 配置   | 配置选项|
| -- | -- |
| 基础 URL | http://localhost:11434 |
| API Key | 随机占位 |

ollama

### rerank model

<!-- TODO 未来急需要部署 -->
