# Copier Django Forge

这是一个基于 Copier 的 Django 项目模板，旨在快速构建现代化的 Django 应用。

## 功能特性

- **Django 6.0+**: 使用最新的 Django 版本。
- **Docker 支持**: 包含完整的 Docker 开发和生产环境配置。
- **PostgreSQL & Redis**: 预配置数据库和缓存。
- **Celery**: 异步任务支持。
- **Django Ninja**: 快速构建 API。
- **Nginx**: 反向代理配置。

## 使用方法

### 1. 安装工具

本项目推荐使用 [uv](https://github.com/astral-sh/uv) 进行包管理。

确保已安装 `copier`：

```bash
# 使用 uv 安装 (推荐)
uv tool install copier

# 或者使用 pipx
pipx install copier
```

### 2. 生成项目

#### 从远程仓库生成

```bash
copier copy https://github.com/your-username/copier-django-forge.git path/to/destination
```

#### 使用本地模板（开发调试）

如果你克隆了本仓库并在本地进行修改，可以使用以下命令测试：

```bash
# 进入你希望存放新项目的目录
cd /path/to/workplace

# 运行 copier，指向模板的本地路径
copier copy /path/to/copier-django-forge my-new-project
```

### 3. 配置选项

在生成过程中，你会被要求回答以下问题：

- `project_name`: 项目名称 (默认: My Awesome Project)
- `project_slug`: 项目 Python 包名/目录名 (snake_case, 默认: mysite)
- `project_description`: 项目描述
- `author_name`: 作者姓名
- `author_email`: 作者邮箱
- `python_version`: Python 版本 (默认: 3.12)

### 4. 初始化项目

项目生成后，请按照生成的 `README.md` 进行操作。主要步骤如下：

1.  **进入项目目录**：
    ```bash
    cd my-new-project
    ```

2.  **安装依赖**：
    ```bash
    uv sync
    ```

3.  **配置环境变量**：
    ```bash
    cp .env.example .env
    ```

4.  **启动开发环境**：
    ```bash
    # 启动 Docker 服务 (PostgreSQL, Redis 等)
    docker compose -f docker/docker-compose.dev.yaml up -d

    # 运行数据库迁移
    uv run manage.py migrate

    # 启动 Django 开发服务器
    uv run manage.py runserver
    ```

## 贡献

欢迎提交 Issue 和 PR。
