# 本地安装说明

- 安装快速说明：
  https://github.com/infiniflow/ragflow/tree/v0.27.3

[本地安装参考](../README.md#-launch-service-from-source-for-development)

## 本地安装

**具体步骤**:

> [!IMPORTANT]
> After cloning the repository for the first time, run `git config --local --unset core.hooksPath`, `uv tool install lefthook` and `lefthook install` once from the repo root to enable local Git hooks.

1. Clone the source code and install Python dependencies:

   ```bash
   git clone https://github.com/infiniflow/ragflow.git
   cd ragflow/
   uv sync --python 3.13 # install RAGFlow dependent python modules
   uv run python3 ragflow_deps/download_deps.py
   git config --local --unset core.hooksPath
   uv tool install lefthook
   lefthook install
   ```
2. Launch the dependent services (MinIO, Elasticsearch, Redis, and MySQL) using Docker Compose:

   ```bash
   docker compose -f docker/docker-compose-base.yml up -d
   ```

3. If your operating system does not have jemalloc, please install it as follows:

   ```bash
   # Ubuntu
   sudo apt-get install libjemalloc-dev
   # CentOS
   sudo yum install jemalloc
   # OpenSUSE
   sudo zypper install jemalloc
   # macOS
   brew install jemalloc
   ```
4. Launch backend service:

   ```bash
   source .venv/bin/activate
   export PYTHONPATH=$(pwd)
   bash docker/launch_backend_service.sh
   ```
6. Install frontend dependencies:

   ```bash
   cd web
   npm install
   ```
7. Launch frontend service:

   ```bash
   npm run dev
   ```

   _The following output confirms a successful launch of the system:_

   ![RAGFlow web interface](https://github.com/user-attachments/assets/0daf462c-a24d-4496-a66f-92533534e187)
8. Stop RAGFlow front-end and back-end service after development is complete:

   ```bash
   pkill -f "ragflow_server.py|task_executor.py"
   ```

9. 安装`nltk`的相关依赖

   ```shell
   mkdir -p ~/nltk_data/{corpora,tokenizers}

   # WordNet
   wget -O /tmp/wordnet.zip \
     https://raw.githubusercontent.com/nltk/nltk_data/gh-pages/packages/corpora/wordnet.zip

   # Punkt
   wget -O /tmp/punkt.zip \
     https://raw.githubusercontent.com/nltk/nltk_data/gh-pages/packages/tokenizers/punkt.zip

   # Punkt Tab
   wget -O /tmp/punkt_tab.zip \
     https://raw.githubusercontent.com/nltk/nltk_data/gh-pages/packages/tokenizers/punkt_tab.zip

   # 解压
   unzip -oq /tmp/wordnet.zip -d ~/nltk_data/corpora/
   unzip -oq /tmp/punkt.zip -d ~/nltk_data/tokenizers/
   unzip -oq /tmp/punkt_tab.zip -d ~/nltk_data/tokenizers/
   ```

