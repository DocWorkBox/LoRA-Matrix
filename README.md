# LoRA Matrix

**图片与视频 LoRA 评测台。好不好，放在一起看。**

训练后的 LoRA 有没有起作用，强度多少合适？LoRA Matrix 可以固定提示词、种子和参考条件，批量测试不同 LoRA 与强度，把图片和视频排成矩阵，方便比较、复查和导出。

连接你自己的 ComfyUI 或 RunningHub，在 Windows 和 macOS 上使用。

[访问官网](https://matrix.doxora.work/) · [GitHub 下载](https://github.com/DocWorkBox/LoRA-Matrix/releases) · [夸克网盘下载](https://pan.quark.cn/s/7ce9f891c838)

![LoRA Matrix 0.2.0 石墨青柠夜间界面：完整四步配置与 Qwen-Image 强度矩阵](https://matrix.doxora.work/workbench-dark.jpg)

*当前版本的真实工作台，图中为 Qwen-Image 的三档 LoRA 强度历史结果。*

<details>
<summary>查看日间界面 · 云白钴蓝</summary>

![LoRA Matrix 0.2.0 云白钴蓝日间界面](https://matrix.doxora.work/workbench-light.jpg)

</details>

## 下载与安装

当前正式版本：[v0.2.0](https://github.com/DocWorkBox/LoRA-Matrix/releases/tag/v0.2.0)。

| 平台 | 下载文件 | 使用方式 |
| --- | --- | --- |
| Windows 10 / 11 x64 | `LoRA-Matrix-0.2.0-Windows.zip` | 完整解压后，运行其中的 `LoRA Matrix 0.2.0.exe` |
| macOS Apple Silicon（M1 及更新芯片） | `LoRA-Matrix-0.2.0.dmg` | 打开 DMG，将应用拖入“应用程序” |

- **GitHub Releases**：[查看版本说明与安装包](https://github.com/DocWorkBox/LoRA-Matrix/releases)。`SHA256SUMS.txt` 提供安装包的完整性校验值。
- **夸克网盘**：[打开分享页下载](https://pan.quark.cn/s/7ce9f891c838)。网盘中的版本以实际文件为准。

macOS 安装包尚未使用 Apple Developer ID 签名或公证。如系统阻止打开，请先确认下载来源和文件完整性，再按系统提示在“系统设置 → 隐私与安全性”中允许该应用打开；无需关闭系统的全局安全保护。

> 软件不附带 ComfyUI、模型、自定义节点或算力。你需要准备可用的本地／远程 ComfyUI，或自己的 RunningHub 账号、API Key 与额度。

## 能做什么

### 图片和视频，都能并排比较

- 一次设置 **1–9 个对比项**，可以选择 LoRA 或原模型基准，再按起始、结束和步进值生成强度矩阵。
- 固定提示词、种子、尺寸和采样参数，减少比较时的干扰变量。
- 调整结果预览大小，自动适应画布，或收起配置面板，把空间留给结果。
- 视频可以单条播放、从头同步播放、全部暂停；打开详情后听声音、看细节。

[查看视频评测介绍与实测片段](https://matrix.doxora.work/#capabilities)

### 不只试强度，也能试采样和参考素材

- 采样器与调度器可以固定使用，也可以配成组合测试；支持搜索、增删和排序，组合按行执行。
- 保留加速 LoRA、模型架构检查与对应模型的默认采样参数。
- 按模型能力使用参考图编辑、视频首帧或首尾帧。
- **MiniMax H3 多参考模式**支持图片、视频、音频单独使用或混合使用，参考视频是否引用原声可以单独设置。
- **Wan 2.2 A14B** 支持高低噪声 LoRA 配对，也能只测试其中一个阶段。
- **Krea 2 Edit** 提供 KV Cache 开关；仅在 LoRA 训练时启用了该选项才开启，普通 Edit LoRA 保持关闭。

### 接上生成服务，留下每一轮结果

- 连接本地／远程 ComfyUI，或 RunningHub 国内站／国际站。RunningHub 提供 24G、48G Plus 与 Ultra 84G 选项。
- 扫描节点和模型，自动匹配主模型、VAE 与文本编码器；匹配不到时可以手动选择，缺少的资源会提示出来。
- 不同连接分别保存输入和并发设置；支持任务取消、完成通知与历史单条删除。
- 运行历史保存在本机，图片提供本地缓存；可以重新打开已有任务继续比较。
- 图片和视频都能下载原文件或打包 ZIP；图片矩阵还可以导出**自适应比例的 PNG 对比画布**。
- 石墨青柠夜间模式与云白钴蓝日间模式记住上次选择，切换时不清空输入或历史，也不改变图片、视频的颜色。

## 四步开始

先连接 ComfyUI 或 RunningHub，确认节点与模型扫描完成，再沿着工作台的四个步骤设置：

| 步骤 | 做什么 |
| --- | --- |
| 01 模型 | 选择与 LoRA 匹配的模型，检查主模型、VAE、编码器等文件 |
| 02 提示词 | 写好提示词，按需要加入参考图片、视频或音频 |
| 03 LoRA | 选择要测试的 LoRA，设置强度范围，按需加入原模型对照或加速 LoRA |
| 04 采样 | 确认种子、步数、输出规格及采样方式，开始测试 |

先用一个 LoRA、几个强度跑一轮。确认设置与结果后，再扩大测试范围。

## 模型与模式

v0.2.0 内置 **38 个模型与模式配置**，包括同一系列的不同版本与运行模式。

| 类别 | 数量 | 范围 |
| --- | --- | --- |
| 图像生成 | 17 | FLUX.1 / FLUX.2、SD 1.5、SDXL、Chroma、Qwen-Image 系列、Anima、Z-Image / Turbo、FLUX.2 Klein Base / Turbo、Boogu Image、Krea 2 Raw / Turbo |
| 图像编辑 | 6 | FLUX.1 Kontext、Qwen-Image-Edit / 2509 / 2511、FireRed-Image-Edit-1.1、Boogu Image Edit |
| 视频与音视频 | 12 | Wan 2.1 / 2.2、LTX-2 / 2.3 / 2.5、MiniMax H3 首尾帧与多参考模式 |
| 实验模式 | 3 | Ideogram4、Krea 2 Raw Edit、Krea 2 Turbo Edit |

[在官网搜索完整模型列表](https://matrix.doxora.work/#models)

这些是内置配置，不代表软件附带模型文件，也不代表每种环境和 LoRA 都能直接兼容。实际运行需要对应的模型与节点，实验模式的兼容性和效果以实际结果为准。

## 使用前了解

- **H3 多参考模式至少需要一份素材。** 最多 9 张图片、3 段视频、3 段独立音频，合计最多 12 个文件；本地 ComfyUI 使用视频参考时需要 VideoHelperSuite。
- **视频需要主动保存。** 视频目前通过流式代理播放，不是永久本地缓存；需要长期保留时，请下载原文件。
- **视频有没有声音取决于模型和生成结果。** 矩阵同步播放不保证逐帧锁定；PNG 对比画布仅用于图片结果。
- **RunningHub 连接与网页收藏登录是两件事。** API Key 连接成功，不代表网页收藏会话已经登录；国内站和国际站分别使用各自的账号与配置。
- **生成完成不等于效果合格。** 仍需检查 LoRA 是否匹配，以及画面、动作、声音和参考素材是否符合预期。

本仓库用于托管 LoRA Matrix 的正式安装包、版本说明与产品介绍，不作为源代码仓库使用。
