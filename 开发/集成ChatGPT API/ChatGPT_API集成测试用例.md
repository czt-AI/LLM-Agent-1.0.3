# ChatGPT API 集成测试用例

## 1. 测试目的

确保LLM-Agent成功集成ChatGPT API，并能正确处理请求和响应。

## 2. 测试环境

- 操作系统：Windows/Linux/MacOS
- Python版本：Python 3.x
- 依赖库：requests、unittest等

## 3. 测试用例

### 3.1 测试用例1：成功请求

- **输入**：有效的prompt和API密钥。
- **预期输出**：返回有效的响应内容。
- **测试步骤**：
  1. 调用ChatGPT API。
  2. 检查响应状态码为200 OK。
  3. 验证返回的JSON数据格式正确。

### 3.2 测试用例2：无效的API密钥

- **输入**：无效的API密钥。
- **预期输出**：返回错误响应，如401 Unauthorized。
- **测试步骤**：
  1. 调用ChatGPT API，使用无效的API密钥。
  2. 检查响应状态码为401 Unauthorized。
  3. 验证返回的JSON数据包含错误信息。

### 3.3 测试用例3：过长的prompt

- **输入**：过长的prompt。
- **预期输出**：返回错误响应，如413 Payload Too Large。
- **测试步骤**：
  1. 调用ChatGPT API，使用过长的prompt。
  2. 检查响应状态码为413 Payload Too Large。
  3. 验证返回的JSON数据包含错误信息。

### 3.4 测试用例4：无效的请求参数

- **输入**：无效的请求参数。
- **预期输出**：返回错误响应，如400 Bad Request。
- **测试步骤**：
  1. 调用ChatGPT API，使用无效的请求参数。
  2. 检查响应状态码为400 Bad Request。
  3. 验证返回的JSON数据包含错误信息。

### 3.5 测试用例5：API限制

- **输入**：达到API请求限制。
- **预期输出**：返回错误响应，如429 Too Many Requests。
- **测试步骤**：
  1. 调用ChatGPT API，达到请求限制。
  2. 检查响应状态码为429 Too Many Requests。
  3. 验证返回的JSON数据包含错误信息。

---

以上测试用例应覆盖ChatGPT API集成的主要方面，确保功能的正确性和稳定性。