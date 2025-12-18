# 项目规则：机器学习专项课程 (Machine Learning Specialization)

本仓库包含 2022 年机器学习专项课程的资料，包括 Jupyter Notebooks、Python 脚本和相关资源。

## 1. 环境管理 (uv)
本项目严格遵循 PEP 621 标准，通过 `pyproject.toml` 使用 `uv` 进行包和环境管理。

### 核心命令
- **同步环境**：运行 `uv sync`，根据 `uv.lock` 和 `pyproject.toml` 创建或更新虚拟环境。
- **添加依赖**：使用 `uv add <package>` 添加新包（例如：`uv add pandas`）。
- **移除依赖**：使用 `uv remove <package>` 卸载包。
- **运行脚本**：始终使用 `uv run <script.py>` 以确保使用正确的环境。
- **Python 版本**：>=3.11（由 `uv` 在 `pyproject.toml` 中管理）。

### 最佳实践
- **切勿直接使用 `pip` 或 `conda`** 安装包，以避免环境漂移。
- **锁定文件**：始终将 `uv.lock` 提交到版本控制，以确保构建的确定性。
- **工具使用**：使用 `uv tool run` 运行临时工具（例如：`uv tool run ruff check .`）。

## 2. Python 代码规范
遵循 **PEP 8** 风格指南和现代 Python 最佳实践。

- **类型提示**：在 `.py` 文件中为函数参数和返回值使用类型提示 (PEP 484)。
- **文档字符串**：为所有公共模块、函数、类和方法包含文档字符串 (PEP 257)。
- **导入顺序**：组织导入：标准库 -> 第三方库 -> 本地应用。
- **路径处理**：使用 `pathlib` 代替 `os.path` 进行文件路径操作。

## 3. Jupyter Notebook 指南
- **内核使用**：确保 Notebooks 运行在项目的 `.venv` 内核上。
    - 如果缺少内核，请运行：`uv run python -m ipykernel install --user --name=ml-specialization`
- **可复现性**：Notebooks 应能从头到尾无错误运行。
    - 验证方法：`Restart Kernel` -> `Run All Cells`。
- **整洁性**：在分享前，尽可能移除 Notebooks 中不必要的输出或大型二进制数据。
- **模块化**：将复杂的逻辑或可重用的实用函数从 Notebooks 移动到单独的 `.py` 模块中（例如：`utils.py`）。

## 4. 目录结构
- **根目录**：`pyproject.toml`, `uv.lock`, `.trae/`。
- **课程内容**：层级结构：`课程名称` / `周次` / `主题` / `材料`。
- **资源**：`images/` 存放资源，`data/` 存放数据集。

## 5. Trae IDE 交互
- **终端**：使用集成终端执行所有 `uv` 命令。
- **代码执行**：当请求助手运行代码时，默认使用 `uv run`。
- **文件创建**：新建的 Python 文件应自动包含类型提示和文档字符串。
- **语言偏好**：始终使用中文与用户进行对话，而非英文。注意：在./Trae/documents 中生成计划文档时，也确保所有文档均采用中文。
