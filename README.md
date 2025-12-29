> 创建虚拟环境：
```bash
uv venv --python 3.11 .venv
```

> 激活虚拟环境：
```bash
source .venv/bin/activate
```
> 或者Windows下：
```bash
.\.venv\Scripts\activate
```

> 退出虚拟环境：
```bash
deactivate
```

### Step 3: 构造 React Agent
React Agent 是整个系统的协调者，负责管理 LLM 调用、工具执行和状态维护。

React Agent 的设计采用了经典的分层架构模式：

- 接口层：对外暴露简单的 run() 方法
- 协调层：管理思考-行动-观察的循环
- 解析层：从模型输出中提取结构化信息
- 执行层：调用具体工具完成任务

这种设计让代码结构清晰，易于维护和扩展。