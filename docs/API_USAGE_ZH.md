# API 调用说明

这些 workflow 是 ComfyUI API 格式，可以提交到 `/prompt`。

## 最小调用思路

1. 启动 ComfyUI。
2. 确认 API 地址，例如 `http://127.0.0.1:8188`。
3. 读取某个 `workflows_api/*.json`。
4. 在提交前替换输入素材、提示词、seed、输出前缀等字段。
5. POST 到 `/prompt`。
6. 通过 `/history/{prompt_id}` 查询结果。

## Python 示例

```python
import json
import urllib.request

server = "http://127.0.0.1:8188"
workflow_path = "workflows_api/kontext_全能溶图打光.json"

with open(workflow_path, "r", encoding="utf-8") as f:
    prompt = json.load(f)

payload = json.dumps({"prompt": prompt}).encode("utf-8")
req = urllib.request.Request(
    f"{server}/prompt",
    data=payload,
    headers={"Content-Type": "application/json"},
)

with urllib.request.urlopen(req) as resp:
    print(resp.read().decode("utf-8"))
```

## 实战提示

- 大多数 workflow 都需要你在提交前替换 `LoadImage` 或 `LoadVideo` 的输入文件。
- 如果模型文件名和你本机不同，直接改 JSON 里的模型名即可。
- 如果缺的是 UI 对比、预览或分组节点，可以复制一份 workflow 后做精简。
- 如果要批量生成，建议在脚本里动态改 seed、prompt、输入图和输出前缀。
