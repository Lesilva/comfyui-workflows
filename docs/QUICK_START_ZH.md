# 快速开始

这个仓库里的是 ComfyUI API workflow，适合脚本调用、批量任务和二次改造。它们不是完整的模型包，也不包含示例图片。

## 使用步骤

1. 打开 `workflows_api/`，选择一个你想跑的 JSON。
2. 把 workflow 里的 `example_image_01.png`、`example_video_01.mp4` 等占位符替换成你自己的素材文件名。
3. 把素材上传到 ComfyUI 的 `input/` 目录，或通过 `/upload/image` 等 API 上传。
4. 启动 ComfyUI，并确认 API 可访问，默认通常是 `http://127.0.0.1:8188`。
5. 如果报缺节点，用 ComfyUI Manager 安装缺失节点。
6. 如果报缺模型，把对应模型放到 ComfyUI 的 `models/` 目录，并让 workflow 中的模型文件名和你的本地文件名一致。

## 新手建议

先从产品图、重打光和放大类 workflow 开始。这类 workflow 通常比视频、换脸、多控制条件 workflow 更容易跑通。

建议优先试：

- `FLUX-产品生成背景.json`
- `Flux电商产品精修.json`
- `kontext_全能溶图打光.json`
- `Flux kontext 高清放大.json`
- `高清放大合集-4合1-写实人像-产品图-素材图-修复放大工作流.json`

## 占位符说明

公开分享版已经把原始素材名改成通用占位符：

- `example_image_01.png`：需要你替换的输入图片。
- `example_image_02.png`：第二张参考图或目标图。
- `example_video_01.mp4`：需要你替换的输入视频。
- `replace_with_uploaded_file_01`：云端或插件节点需要你自己上传/选择的文件标识。

这些文件不会随仓库提供，因为每个人的素材和授权情况不同。
