# ComfyUI Workflows 分享库

这里整理了一批适合学习、改造和二次创作的 ComfyUI API workflows，覆盖 FLUX / Kontext / Qwen / Wan / 放大修复 / 产品图 / 人像 / 视频等常见玩法。

这个仓库是公开分享版：只包含 workflow JSON 和说明文档，不包含模型权重、示例素材、API Key、账号信息、私人路径或服务器信息。默认输入图片和输出目录已经替换成通用占位符，使用时请换成你自己的素材。

## 目录结构

- `workflows_api/`：API 格式的 ComfyUI workflow JSON。
- `docs/`：中文使用指南、依赖说明和 API 调用说明。
- `metadata/`：公开版 workflow 清单，方便脚本或网页读取。

## 怎么使用

1. 下载或 clone 这个仓库。
2. 在 `workflows_api/` 里挑一个 workflow。
3. 根据 workflow 里 `LoadImage` / `LoadVideo` 节点的占位符，替换成你自己的图片或视频。
4. 用 ComfyUI Manager 安装缺失自定义节点，并按 workflow 需要准备模型。
5. 通过 ComfyUI API `/prompt` 调用，或在支持 API workflow 的工具里加载运行。

> 提醒：这些文件是 API workflow，不一定保留原始画布排版。更适合脚本调用、批量生成和二次改造。

## 推荐先试

- 产品图/电商：`FLUX-产品生成背景.json`、`Flux电商产品精修.json`、`kontext电商产品打光_渲染.json`
- 图片融合/重打光：`kontext_全能溶图打光.json`、`人物背景完美融合.json`、`PS高阶-光影优化V2.json`
- 放大修复：`Flux kontext 高清放大.json`、`高清放大合集-4合1-写实人像-产品图-素材图-修复放大工作流.json`
- 人像动作/换装：`Kontext人物换姿势【解决一致性】.json`、`模特一键换衣-电商.json`
- 视频：`Wan2.2极速文生视频KJ版本（已确保跑通）.json`、`wan2.1 vace首尾帧视频.json`

## Workflow 简介

| # | Workflow | 简介 |
| --- | --- | --- |
| 1 | [`FLUX 文生图 + ControlNet + 支持中文输入.json`](workflows_api/FLUX%20%E6%96%87%E7%94%9F%E5%9B%BE%20%2B%20ControlNet%20%2B%20%E6%94%AF%E6%8C%81%E4%B8%AD%E6%96%87%E8%BE%93%E5%85%A5.json) | FLUX 文生图，带 ControlNet 结构控制，并支持中文提示词。 |
| 2 | [`FLUX-FILL-扩图-质感扩图.json`](workflows_api/FLUX-FILL-%E6%89%A9%E5%9B%BE-%E8%B4%A8%E6%84%9F%E6%89%A9%E5%9B%BE.json) | FLUX Fill 扩图，适合保留材质和质感的画布外扩。 |
| 3 | [`FLUX-产品生成背景.json`](workflows_api/FLUX-%E4%BA%A7%E5%93%81%E7%94%9F%E6%88%90%E8%83%8C%E6%99%AF.json) | 产品抠图/分割后生成 AI 广告背景。 |
| 4 | [`FLUX反推控图与生图.json`](workflows_api/FLUX%E5%8F%8D%E6%8E%A8%E6%8E%A7%E5%9B%BE%E4%B8%8E%E7%94%9F%E5%9B%BE.json) | 图片反推提示词，再用 FLUX 做受控再生成。 |
| 5 | [`FLUX最优高质量洗图增加质感细节修复质感提升产品人物细节稳定工作流细节修复质感提升产品人物细节稳定.json`](workflows_api/FLUX%E6%9C%80%E4%BC%98%E9%AB%98%E8%B4%A8%E9%87%8F%E6%B4%97%E5%9B%BE%E5%A2%9E%E5%8A%A0%E8%B4%A8%E6%84%9F%E7%BB%86%E8%8A%82%E4%BF%AE%E5%A4%8D%E8%B4%A8%E6%84%9F%E6%8F%90%E5%8D%87%E4%BA%A7%E5%93%81%E4%BA%BA%E7%89%A9%E7%BB%86%E8%8A%82%E7%A8%B3%E5%AE%9A%E5%B7%A5%E4%BD%9C%E6%B5%81%E7%BB%86%E8%8A%82%E4%BF%AE%E5%A4%8D%E8%B4%A8%E6%84%9F%E6%8F%90%E5%8D%87%E4%BA%A7%E5%93%81%E4%BA%BA%E7%89%A9%E7%BB%86%E8%8A%82%E7%A8%B3%E5%AE%9A.json) | 源图清理、质感增强、细节修复，适合产品和人物低重绘精修。 |
| 6 | [`FOX-XL-Illustrious-ControlNet辅助文生图.json`](workflows_api/FOX-XL-Illustrious-ControlNet%E8%BE%85%E5%8A%A9%E6%96%87%E7%94%9F%E5%9B%BE.json) | SDXL/Illustrious 动漫文生图，带 ControlNet、脸部细化和放大辅助。 |
| 7 | [`Fill One reward局部重绘工作流.json`](workflows_api/Fill%20One%20reward%E5%B1%80%E9%83%A8%E9%87%8D%E7%BB%98%E5%B7%A5%E4%BD%9C%E6%B5%81.json) | OneReward FLUX Fill 局部重绘，适合蒙版区域替换或修复。 |
| 8 | [`Fill-flux-dev 重绘 OneReward fp8 工作流 .json`](workflows_api/Fill-flux-dev%20%E9%87%8D%E7%BB%98%20OneReward%20fp8%20%E5%B7%A5%E4%BD%9C%E6%B5%81%20.json) | fp8 OneReward FLUX Fill 局部重绘，适合较低显存设置。 |
| 9 | [`Flux Krea 图生图+自动提示词+润色+ControlNet.json`](workflows_api/Flux%20Krea%20%E5%9B%BE%E7%94%9F%E5%9B%BE%2B%E8%87%AA%E5%8A%A8%E6%8F%90%E7%A4%BA%E8%AF%8D%2B%E6%B6%A6%E8%89%B2%2BControlNet.json) | 参考图图生图，自动反推/润色提示词并使用 ControlNet 保结构。 |
| 10 | [`Flux kontext 高清放大.json`](workflows_api/Flux%20kontext%20%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7.json) | Flux Kontext 高清分块放大和细节优化。 |
| 11 | [`Flux-TTP-tile高清放大修复高清无损放大.json`](workflows_api/Flux-TTP-tile%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7%E4%BF%AE%E5%A4%8D%E9%AB%98%E6%B8%85%E6%97%A0%E6%8D%9F%E6%94%BE%E5%A4%A7.json) | TTP 分块 FLUX 放大与修复，适合高清无损感修复。 |
| 12 | [`Flux.1-Dev-SRPO工作流｜3倍于Flux美感.json`](workflows_api/Flux.1-Dev-SRPO%E5%B7%A5%E4%BD%9C%E6%B5%81%EF%BD%9C3%E5%80%8D%E4%BA%8EFlux%E7%BE%8E%E6%84%9F.json) | 高审美 FLUX SRPO 文生图工作流。 |
| 13 | [`Flux电商产品换背景、.json`](workflows_api/Flux%E7%94%B5%E5%95%86%E4%BA%A7%E5%93%81%E6%8D%A2%E8%83%8C%E6%99%AF%E3%80%81.json) | 电商产品换背景，尽量保持产品主体不变。 |
| 14 | [`Flux电商产品精修.json`](workflows_api/Flux%E7%94%B5%E5%95%86%E4%BA%A7%E5%93%81%E7%B2%BE%E4%BF%AE.json) | 电商产品精修、白底清洁、商业品质提升。 |
| 15 | [`HYPIR图像2K4K8K超高清放大降噪修复强化.json`](workflows_api/HYPIR%E5%9B%BE%E5%83%8F2K4K8K%E8%B6%85%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7%E9%99%8D%E5%99%AA%E4%BF%AE%E5%A4%8D%E5%BC%BA%E5%8C%96.json) | HYPIR 超分、降噪和图像修复，适合 2K/4K/8K 增强。 |
| 16 | [`Kontext 电商角度自适应自动纠正透视场景产品融图.json`](workflows_api/Kontext%20%E7%94%B5%E5%95%86%E8%A7%92%E5%BA%A6%E8%87%AA%E9%80%82%E5%BA%94%E8%87%AA%E5%8A%A8%E7%BA%A0%E6%AD%A3%E9%80%8F%E8%A7%86%E5%9C%BA%E6%99%AF%E4%BA%A7%E5%93%81%E8%9E%8D%E5%9B%BE.json) | 产品场景融合，自动适配角度和透视。 |
| 17 | [`Kontext 绝对无损放大.json`](workflows_api/Kontext%20%E7%BB%9D%E5%AF%B9%E6%97%A0%E6%8D%9F%E6%94%BE%E5%A4%A7.json) | Flux Kontext 分块低损高清放大。 |
| 18 | [`Kontext-人物重打光V2.json`](workflows_api/Kontext-%E4%BA%BA%E7%89%A9%E9%87%8D%E6%89%93%E5%85%89V2.json) | 人物/人像重打光，可控制光源方向。 |
| 19 | [`Kontext-保持角色一致-改变动作 .json`](workflows_api/Kontext-%E4%BF%9D%E6%8C%81%E8%A7%92%E8%89%B2%E4%B8%80%E8%87%B4-%E6%94%B9%E5%8F%98%E5%8A%A8%E4%BD%9C%20.json) | 保持角色一致，生成动作或姿势变化组。 |
| 20 | [`Kontext人物换姿势【解决一致性】.json`](workflows_api/Kontext%E4%BA%BA%E7%89%A9%E6%8D%A2%E5%A7%BF%E5%8A%BF%E3%80%90%E8%A7%A3%E5%86%B3%E4%B8%80%E8%87%B4%E6%80%A7%E3%80%91.json) | 人物换姿势，同时尽量保持身份和服装一致。 |
| 21 | [`PS高阶-光影优化V2.json`](workflows_api/PS%E9%AB%98%E9%98%B6-%E5%85%89%E5%BD%B1%E4%BC%98%E5%8C%96V2.json) | 类似 PS 的高阶光影优化，适合人像或产品光影清理。 |
| 22 | [`Qwen Edit衣服提取工作流.json`](workflows_api/Qwen%20Edit%E8%A1%A3%E6%9C%8D%E6%8F%90%E5%8F%96%E5%B7%A5%E4%BD%9C%E6%B5%81.json) | Qwen Image Edit 衣服提取，用于准备服装素材。 |
| 23 | [`Wan2.2 动态壁纸生成器 🚀.json`](workflows_api/Wan2.2%20%E5%8A%A8%E6%80%81%E5%A3%81%E7%BA%B8%E7%94%9F%E6%88%90%E5%99%A8%20%F0%9F%9A%80.json) | Wan 2.2 图生视频动态壁纸。 |
| 24 | [`Wan2.2极速文生视频KJ版本（已确保跑通）.json`](workflows_api/Wan2.2%E6%9E%81%E9%80%9F%E6%96%87%E7%94%9F%E8%A7%86%E9%A2%91KJ%E7%89%88%E6%9C%AC%EF%BC%88%E5%B7%B2%E7%A1%AE%E4%BF%9D%E8%B7%91%E9%80%9A%EF%BC%89.json) | Wan 2.2 极速文生视频 KJ 版本，原文件标注已确保跑通。 |
| 25 | [`flux reward修手工作流.json`](workflows_api/flux%20reward%E4%BF%AE%E6%89%8B%E5%B7%A5%E4%BD%9C%E6%B5%81.json) | FLUX Fill 修手，适合修复手指和手部结构。 |
| 26 | [`instant id 换脸 _ 一键在线运行.json`](workflows_api/instant%20id%20%E6%8D%A2%E8%84%B8%20_%20%E4%B8%80%E9%94%AE%E5%9C%A8%E7%BA%BF%E8%BF%90%E8%A1%8C.json) | InstantID 换脸/身份迁移。 |
| 27 | [`kontext_全能溶图打光.json`](workflows_api/kontext_%E5%85%A8%E8%83%BD%E6%BA%B6%E5%9B%BE%E6%89%93%E5%85%89.json) | 通用溶图和重打光，适合融合感和光影统一。 |
| 28 | [`kontext工作流 （人像光影）.json`](workflows_api/kontext%E5%B7%A5%E4%BD%9C%E6%B5%81%20%EF%BC%88%E4%BA%BA%E5%83%8F%E5%85%89%E5%BD%B1%EF%BC%89.json) | 人像光影调整，保持人物可识别同时改善光照。 |
| 29 | [`kontext电商产品打光_渲染.json`](workflows_api/kontext%E7%94%B5%E5%95%86%E4%BA%A7%E5%93%81%E6%89%93%E5%85%89_%E6%B8%B2%E6%9F%93.json) | 电商产品打光和渲染精修。 |
| 30 | [`kontext筋膜枪_手机等各类手持_融图.json`](workflows_api/kontext%E7%AD%8B%E8%86%9C%E6%9E%AA_%E6%89%8B%E6%9C%BA%E7%AD%89%E5%90%84%E7%B1%BB%E6%89%8B%E6%8C%81_%E8%9E%8D%E5%9B%BE.json) | 手机、筋膜枪等手持产品融图。 |
| 31 | [`miluo丨版画艺术生成器.json`](workflows_api/miluo%E4%B8%A8%E7%89%88%E7%94%BB%E8%89%BA%E6%9C%AF%E7%94%9F%E6%88%90%E5%99%A8.json) | 版画/雕刻风格艺术生成。 |
| 32 | [`model_product_showcase_LOCAL_FLUX_KONTEXT_DEV.json`](workflows_api/model_product_showcase_LOCAL_FLUX_KONTEXT_DEV.json) | 本地 FLUX.1 Kontext Dev 模特展示产品 workflow 的 ASCII 文件名别名，方便自动化调用。 |
| 33 | [`qwen—image万物迁移合集.json`](workflows_api/qwen%E2%80%94image%E4%B8%87%E7%89%A9%E8%BF%81%E7%A7%BB%E5%90%88%E9%9B%86.json) | Qwen Image Edit 万物迁移合集，适合对象/风格迁移。 |
| 34 | [`wan2.1 vace首尾帧视频.json`](workflows_api/wan2.1%20vace%E9%A6%96%E5%B0%BE%E5%B8%A7%E8%A7%86%E9%A2%91.json) | Wan 2.1 VACE 首尾帧视频生成。 |
| 35 | [`wan2.1 万相 Q版卡通动漫角色跳舞视频动画.json`](workflows_api/wan2.1%20%E4%B8%87%E7%9B%B8%20Q%E7%89%88%E5%8D%A1%E9%80%9A%E5%8A%A8%E6%BC%AB%E8%A7%92%E8%89%B2%E8%B7%B3%E8%88%9E%E8%A7%86%E9%A2%91%E5%8A%A8%E7%94%BB.json) | Q 版/卡通角色跳舞视频动画。 |
| 36 | [`wan2.2(动作迁移开高清）.json`](workflows_api/wan2.2%28%E5%8A%A8%E4%BD%9C%E8%BF%81%E7%A7%BB%E5%BC%80%E9%AB%98%E6%B8%85%EF%BC%89.json) | Wan 2.2 动作迁移，带高清辅助路径。 |
| 37 | [`wan2.2文生视频(14B)GGUF适合16G以下显存.json`](workflows_api/wan2.2%E6%96%87%E7%94%9F%E8%A7%86%E9%A2%91%2814B%29GGUF%E9%80%82%E5%90%8816G%E4%BB%A5%E4%B8%8B%E6%98%BE%E5%AD%98.json) | Wan 2.2 14B GGUF 文生视频，适合较低显存实验。 |
| 38 | [`一键换头，可根据需要是否添加蒙版.json`](workflows_api/%E4%B8%80%E9%94%AE%E6%8D%A2%E5%A4%B4%EF%BC%8C%E5%8F%AF%E6%A0%B9%E6%8D%AE%E9%9C%80%E8%A6%81%E6%98%AF%E5%90%A6%E6%B7%BB%E5%8A%A0%E8%92%99%E7%89%88.json) | 一键换头，可选蒙版或局部重绘。 |
| 39 | [`一键模特展示产品.json`](workflows_api/%E4%B8%80%E9%94%AE%E6%A8%A1%E7%89%B9%E5%B1%95%E7%A4%BA%E4%BA%A7%E5%93%81.json) | 云端 Flux Kontext Pro 版本的模特展示产品 workflow，需要 Comfy 登录/授权。 |
| 40 | [`一键模特展示产品_LOCAL_FLUX_KONTEXT_DEV.json`](workflows_api/%E4%B8%80%E9%94%AE%E6%A8%A1%E7%89%B9%E5%B1%95%E7%A4%BA%E4%BA%A7%E5%93%81_LOCAL_FLUX_KONTEXT_DEV.json) | 本地 FLUX.1 Kontext Dev 版本的模特展示产品 workflow，无需云端 Pro 节点。 |
| 41 | [`一键生成红蓝白底证件照comfyui.json`](workflows_api/%E4%B8%80%E9%94%AE%E7%94%9F%E6%88%90%E7%BA%A2%E8%93%9D%E7%99%BD%E5%BA%95%E8%AF%81%E4%BB%B6%E7%85%A7comfyui.json) | 证件照抠图、换红/蓝/白底和排版。 |
| 42 | [`一键用插画生成COSER老婆.json`](workflows_api/%E4%B8%80%E9%94%AE%E7%94%A8%E6%8F%92%E7%94%BB%E7%94%9F%E6%88%90COSER%E8%80%81%E5%A9%86.json) | 通过 Gemini 将插画参考转成写实 coser 风照片。 |
| 43 | [`万相2.2文生图-图生图-fp8量化版-Magic-Wan-Image.json`](workflows_api/%E4%B8%87%E7%9B%B82.2%E6%96%87%E7%94%9F%E5%9B%BE-%E5%9B%BE%E7%94%9F%E5%9B%BE-fp8%E9%87%8F%E5%8C%96%E7%89%88-Magic-Wan-Image.json) | Wan 2.2 fp8 文生图/图生图静态图生成。 |
| 44 | [`万相MotionLoRA - 镜头推进.json`](workflows_api/%E4%B8%87%E7%9B%B8MotionLoRA%20-%20%E9%95%9C%E5%A4%B4%E6%8E%A8%E8%BF%9B.json) | Wan MotionLoRA 镜头推进动画。 |
| 45 | [`产品修图-布料去褶皱.json`](workflows_api/%E4%BA%A7%E5%93%81%E4%BF%AE%E5%9B%BE-%E5%B8%83%E6%96%99%E5%8E%BB%E8%A4%B6%E7%9A%B1.json) | 产品或服装布料去褶皱。 |
| 46 | [`人像溶图打光 _ 人物海报合成_人像打光_人物背景融合.json`](workflows_api/%E4%BA%BA%E5%83%8F%E6%BA%B6%E5%9B%BE%E6%89%93%E5%85%89%20_%20%E4%BA%BA%E7%89%A9%E6%B5%B7%E6%8A%A5%E5%90%88%E6%88%90_%E4%BA%BA%E5%83%8F%E6%89%93%E5%85%89_%E4%BA%BA%E7%89%A9%E8%83%8C%E6%99%AF%E8%9E%8D%E5%90%88.json) | 人像海报合成、背景融合和人物打光。 |
| 47 | [`人物一键生成多姿势图.json`](workflows_api/%E4%BA%BA%E7%89%A9%E4%B8%80%E9%94%AE%E7%94%9F%E6%88%90%E5%A4%9A%E5%A7%BF%E5%8A%BF%E5%9B%BE.json) | 为人物一键生成多姿势图。 |
| 48 | [`人物背景完美融合.json`](workflows_api/%E4%BA%BA%E7%89%A9%E8%83%8C%E6%99%AF%E5%AE%8C%E7%BE%8E%E8%9E%8D%E5%90%88.json) | ICLight 人物与背景光照融合。 |
| 49 | [`商业级高清放大工作流.json`](workflows_api/%E5%95%86%E4%B8%9A%E7%BA%A7%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7%E5%B7%A5%E4%BD%9C%E6%B5%81.json) | 商业级高清放大，带自动描述和分块处理。 |
| 50 | [`固定人像换指定动作【万物迁移】.json`](workflows_api/%E5%9B%BA%E5%AE%9A%E4%BA%BA%E5%83%8F%E6%8D%A2%E6%8C%87%E5%AE%9A%E5%8A%A8%E4%BD%9C%E3%80%90%E4%B8%87%E7%89%A9%E8%BF%81%E7%A7%BB%E3%80%91.json) | 固定人像按参考动作换指定姿势。 |
| 51 | [`图像细节增加 模糊图片拯救 高清修复放大 .json`](workflows_api/%E5%9B%BE%E5%83%8F%E7%BB%86%E8%8A%82%E5%A2%9E%E5%8A%A0%20%E6%A8%A1%E7%B3%8A%E5%9B%BE%E7%89%87%E6%8B%AF%E6%95%91%20%E9%AB%98%E6%B8%85%E4%BF%AE%E5%A4%8D%E6%94%BE%E5%A4%A7%20.json) | 模糊图拯救、细节增加、高清修复放大。 |
| 52 | [`多图融合-1.json`](workflows_api/%E5%A4%9A%E5%9B%BE%E8%9E%8D%E5%90%88-1.json) | Qwen 双图融合。 |
| 53 | [`工业产品精修：机械零件设备-图片修复-高清放大-材质优化-工作流.json`](workflows_api/%E5%B7%A5%E4%B8%9A%E4%BA%A7%E5%93%81%E7%B2%BE%E4%BF%AE%EF%BC%9A%E6%9C%BA%E6%A2%B0%E9%9B%B6%E4%BB%B6%E8%AE%BE%E5%A4%87-%E5%9B%BE%E7%89%87%E4%BF%AE%E5%A4%8D-%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7-%E6%9D%90%E8%B4%A8%E4%BC%98%E5%8C%96-%E5%B7%A5%E4%BD%9C%E6%B5%81.json) | 工业产品/机械零件/设备图修复、放大和材质优化。 |
| 54 | [`最强高清放大还原.json`](workflows_api/%E6%9C%80%E5%BC%BA%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7%E8%BF%98%E5%8E%9F.json) | SeedVR2 加 FLUX/Ultimate SD Upscale 的强力高清还原。 |
| 55 | [`最新！！图像一键放大.json`](workflows_api/%E6%9C%80%E6%96%B0%EF%BC%81%EF%BC%81%E5%9B%BE%E5%83%8F%E4%B8%80%E9%94%AE%E6%94%BE%E5%A4%A7.json) | 一键通用图像放大，带像素和降噪说明。 |
| 56 | [`模特一键换衣-电商.json`](workflows_api/%E6%A8%A1%E7%89%B9%E4%B8%80%E9%94%AE%E6%8D%A2%E8%A1%A3-%E7%94%B5%E5%95%86.json) | 电商模特按服装参考一键换衣。 |
| 57 | [`模特姿势随机变化超强一致性.json`](workflows_api/%E6%A8%A1%E7%89%B9%E5%A7%BF%E5%8A%BF%E9%9A%8F%E6%9C%BA%E5%8F%98%E5%8C%96%E8%B6%85%E5%BC%BA%E4%B8%80%E8%87%B4%E6%80%A7.json) | 模特随机姿势变化，强调一致性。 |
| 58 | [`浑厚的书法字模版.json`](workflows_api/%E6%B5%91%E5%8E%9A%E7%9A%84%E4%B9%A6%E6%B3%95%E5%AD%97%E6%A8%A1%E7%89%88.json) | Qwen Image 厚重中文书法字模板。 |
| 59 | [`溶图迁移-穿搭.json`](workflows_api/%E6%BA%B6%E5%9B%BE%E8%BF%81%E7%A7%BB-%E7%A9%BF%E6%90%AD.json) | 穿搭迁移/服装融合。 |
| 60 | [`精准表情控制.json`](workflows_api/%E7%B2%BE%E5%87%86%E8%A1%A8%E6%83%85%E6%8E%A7%E5%88%B6.json) | 精准控制人物表情。 |
| 61 | [`线稿制作.json`](workflows_api/%E7%BA%BF%E7%A8%BF%E5%88%B6%E4%BD%9C.json) | 产品或图片转干净线稿。 |
| 62 | [`自适应纠正透视溶图.json`](workflows_api/%E8%87%AA%E9%80%82%E5%BA%94%E7%BA%A0%E6%AD%A3%E9%80%8F%E8%A7%86%E6%BA%B6%E5%9B%BE.json) | 自适应透视纠正和图像融合。 |
| 63 | [`视频动作迁移WAN2.1-VACE-14B.json`](workflows_api/%E8%A7%86%E9%A2%91%E5%8A%A8%E4%BD%9C%E8%BF%81%E7%A7%BBWAN2.1-VACE-14B.json) | Wan 2.1 VACE 视频动作/运动迁移。 |
| 64 | [`视频重绘【换衣+换人】.json`](workflows_api/%E8%A7%86%E9%A2%91%E9%87%8D%E7%BB%98%E3%80%90%E6%8D%A2%E8%A1%A3%2B%E6%8D%A2%E4%BA%BA%E3%80%91.json) | 高级视频局部重绘，可用于换衣和换人。 |
| 65 | [`高清放大_SeedVR2+TTP分块_.json`](workflows_api/%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7_SeedVR2%2BTTP%E5%88%86%E5%9D%97_.json) | SeedVR2 加 TTP 分块高清放大。 |
| 66 | [`高清放大合集-4合1-写实人像-产品图-素材图-修复放大工作流.json`](workflows_api/%E9%AB%98%E6%B8%85%E6%94%BE%E5%A4%A7%E5%90%88%E9%9B%86-4%E5%90%881-%E5%86%99%E5%AE%9E%E4%BA%BA%E5%83%8F-%E4%BA%A7%E5%93%81%E5%9B%BE-%E7%B4%A0%E6%9D%90%E5%9B%BE-%E4%BF%AE%E5%A4%8D%E6%94%BE%E5%A4%A7%E5%B7%A5%E4%BD%9C%E6%B5%81.json) | 四合一高清放大工具，覆盖写实人像、产品图、素材图和修复放大。 |
| 67 | [`高级渲染一键精修图片.json`](workflows_api/%E9%AB%98%E7%BA%A7%E6%B8%B2%E6%9F%93%E4%B8%80%E9%94%AE%E7%B2%BE%E4%BF%AE%E5%9B%BE%E7%89%87.json) | 一键高级渲染和商业精修。 |

## 重要说明

- 本仓库不提供模型下载，也不重新分发任何模型权重。
- 部分 workflow 依赖第三方自定义节点、云端节点或需要你自己的 API Key，请按自己的环境配置。
- 文件里的示例输入名如 `example_image_01.png`、`example_video_01.mp4` 都是占位符，不是仓库自带素材。
- 如果某个 workflow 报缺节点，优先用 ComfyUI Manager 的安装缺失节点功能，再根据报错补模型。
- 公开分享版已经去掉私人路径、内网地址、测试输出文件名和内部运行记录。

更多说明见：

- [快速开始](docs/QUICK_START_ZH.md)
- [依赖与模型说明](docs/DEPENDENCIES_ZH.md)
- [API 调用说明](docs/API_USAGE_ZH.md)
