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

### 前置条件

确保已安装 [Copier](https://copier.readthedocs.io/):

```bash
# 使用 pipx (推荐)
pipx install copier

# 或者使用 pip
pip install copier

# 或者使用 uv
uv tool install copier
```

### 生成项目

运行以下命令生成新项目：

```bash
copier copy https://github.com/your-username/your-template-repo.git path/to/destination
```

如果是本地模板：

```bash
copier copy path/to/template path/to/destination
```

### 配置选项

在生成过程中，你需要回答以下问题：

- `project_name`: 项目名称 (默认: My Awesome Project)
- `project_slug`: 项目 Python 包名/目录名 (snake_case, 默认: mysite)
- `project_description`: 项目描述
- `author_name`: 作者姓名
- `author_email`: 作者邮箱
- `python_version`: Python 版本 (默认: 3.12)

### 生成后操作

项目生成后，进入项目目录并按照 `README.md` 中的说明进行操作：

1. 初始化环境: `uv sync`
2. 配置环境变量: `cp .env.example .env`
3. 启动开发环境: `docker compose -f docker/docker-compose.dev.yaml up -d`

## 贡献

欢迎提交 Issue 和 PR。
