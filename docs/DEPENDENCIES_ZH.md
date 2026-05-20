# 依赖与模型说明

这个仓库只分享 workflow，不包含模型权重、自定义节点源码、API Key 或商业服务账号。

## 常见依赖类型

- FLUX / Kontext：常见于产品图、重打光、图生图、放大修复。
- Qwen Image / Qwen Edit：常见于图像编辑、融合、中文场景。
- Wan / VideoHelperSuite：常见于文生视频、首尾帧视频、动作迁移。
- ControlNet / OpenPose / Depth：常见于姿势、结构、深度控制。
- Florence2 / JoyCaption / WD14：常见于自动反推提示词或图片理解。
- rgthree / KJNodes / Easy Use / LayerStyle：常见于画布辅助、图像尺寸处理、视频处理和批量节点。

## 安装建议

1. 不要一次性按所有报错安装全部依赖。
2. 先选一个你真正要跑的 workflow。
3. 用 ComfyUI Manager 安装缺失节点。
4. 根据报错补模型，并检查模型文件名是否和 workflow 中一致。
5. 如果只是前端预览、对比、分组、清缓存类节点缺失，可以考虑在自己的版本里删除或绕过。

## 关于云端节点

有些 workflow 可能包含 Gemini、LibLib、Flux Kontext Pro 或类似云端节点。公开库不会提供任何账号、Token 或 API Key。

如果你没有对应服务，可以：

- 换成本地模型节点。
- 删除云端分支，只保留本地生成链路。
- 把这个 workflow 当作结构参考，重新搭建适合自己环境的版本。

## 关于模型授权

请自行确认模型、LoRA、素材和生成结果的授权范围。这个仓库不重新分发模型，也不替任何第三方模型提供许可说明。
