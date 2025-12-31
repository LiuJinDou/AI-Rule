# Claude Code 安装指南 (Linux)

本文档介绍如何在 Linux 系统上安装和配置 Claude Code，包括 Node.js、npm 的安装，以及环境变量的设置。

## 1. 安装 Node.js 和 npm

Claude Code 需要 Node.js 和 npm 才能运行。请根据你的 Linux 发行版选择相应的安装命令。

### Ubuntu/Debian
```bash
sudo apt update
sudo apt install nodejs npm
```

### CentOS/RHEL/Fedora
```bash
sudo dnf install nodejs npm
```

### Linux 注意事项
- 某些发行版可能需要安装额外的依赖项。
- 如果遇到权限问题，请使用 `sudo`。
- 确保你的用户对 npm 的全局目录有写权限。

### 验证安装
安装完成后，打开终端并运行以下命令来验证：

```bash
node --version
npm --version
```

如果显示版本号，则说明安装成功！

## 2. 安装 Claude Code

现在安装 Claude Code CLI 工具。

### 全局安装
运行以下命令全局安装 Claude Code：

```bash
npm install -g @anthropic-ai/claude-code
```

如果遇到权限问题，可以使用 `sudo`：

```bash
sudo npm install -g @anthropic-ai/claude-code
```

### 验证安装
安装完成后，检查是否安装成功：

```bash
claude --version
```

如果显示版本号，恭喜你！Claude Code 已经成功安装。

## 3. 设置环境变量

为了让 Claude Code 连接到你的中转服务，需要设置两个环境变量：`ANTHROPIC_BASE_URL` 和 `ANTHROPIC_AUTH_TOKEN`。

### 方法一：临时设置（当前会话）
在终端中运行以下命令（仅在当前会话有效）：

```bash
export ANTHROPIC_BASE_URL="https://ai.tokencloud.ai/api"
export ANTHROPIC_AUTH_TOKEN="你的API密钥"
```

💡 **提示**：记得将 `"你的API密钥"` 替换为实际的 API 密钥（可在 "API Keys" 标签页中创建）。

### 方法二：永久设置
编辑你的 shell 配置文件以永久设置环境变量。

#### 对于 Bash（默认 shell）
```bash
echo 'export ANTHROPIC_BASE_URL="https://ai.tokencloud.ai/api"' >> ~/.bashrc
echo 'export ANTHROPIC_AUTH_TOKEN="你的API密钥"' >> ~/.bashrc
source ~/.bashrc
```

#### 对于 Zsh
```bash
echo 'export ANTHROPIC_BASE_URL="https://ai.tokencloud.ai/api"' >> ~/.zshrc
echo 'export ANTHROPIC_AUTH_TOKEN="你的API密钥"' >> ~/.zshrc
source ~/.zshrc
```

设置完成后，重启终端或运行 `source` 命令使更改生效。

## 故障排除

- 如果安装过程中遇到问题，请确保你的系统已更新到最新版本。
- 对于权限问题，考虑使用 Node Version Manager (nvm) 来管理 Node.js 版本。
- 如果 API 密钥无效，请检查密钥是否正确复制。

## 更多信息

有关 Claude Code 的更多详细信息，请参考官方文档。