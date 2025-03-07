# MCP Text Tools Demo

这是一个简单的 MCP (Model Context Protocol) 服务器示例，提供了文本反转功能。

## 安装

1. 创建并激活 conda 环境：
```bash
conda create -n mcp-server-demo python=3.10
conda activate mcp-server-demo
```

2. 安装依赖：
```bash
pip install -r requirements.txt
```

## 运行服务器

### 使用 stdio 模式（默认）
```bash
python server.py
```

### 使用 SSE 模式
```bash
python server.py --transport sse --port 8000
```

## 在 Cursor 中配置

1. 打开 Cursor 设置
2. 导航到 `Features` > `MCP`
3. 点击 `+ Add New MCP Server`
4. 配置服务器：
   - 对于 stdio 模式：
     - Type: stdio
     - Name: Text Tools
     - Command: conda run -n mcp-server-demo python /path/to/server.py
   
   - 对于 SSE 模式：
     - Type: sse
     - Name: Text Tools
     - URL: http://localhost:8000/sse

## 可用工具

- `reverse_text`: 接收一个文本输入并返回其反转版本
  - 参数：
    - text: 要反转的文本字符串

## 注意事项

- 确保在运行服务器之前已经激活了 conda 环境：`conda activate mcp-server-demo`
- 在 Cursor 中配置命令时需要使用 `conda run -n mcp-server-demo` 前缀
- 请将命令中的 `/path/to/server.py` 替换为实际的服务器脚本路径 