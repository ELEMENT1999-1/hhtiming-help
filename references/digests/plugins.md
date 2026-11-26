# Plugins（插件）

## 概述

Plugins 章节介绍 HH Timing 的插件框架与官方插件。本章节**没有独立根页**，共 2 个子页：官方免费的 Drive Time Plugin（驾驶时间插件）详解，以及「如何自研插件」开发指南。插件框架是 FAQ 中「保密/专属工具」的实现途径：框架开放，客户可自行开发而不必付费委托官方。

## 子页 1：Drive time plugin（驾驶时间插件）

- URL：https://help.hhtiming.com/plugins/drive-time-plugin/

### 完整要点

**定位**：HH Timing 的免费附加插件，帮助车队在**固定 stint 时间 + 赛事特定驾驶时间规则**的比赛中做更好的策略决策；适用于任何采用固定 stint 长度的赛事（如 GTWC/Blancpain 耐力赛）。

**下载与安装**
- 下载：官网 hh-dev.com 的 HH Timing plugins 区，或直接 https://hh-dev.com/latest/HHT-DT
- 安装：把插件文件夹（**不要解压**）放到：

  ```
  Documents\HH Timing\Plugins\
  ```

- 启动 HH Timing → Backstage → Plugins 选项卡，确认 Drive Time 插件已启用 → **重启软件** → ribbon bar 出现 **Drive Time** 选项卡，插件组件可像其他组件一样创建和操作。
- 源码在官方 GitHub 仓库。

**插件组件**
- Stint Summary（stint 摘要）
- Continuous Driving Time（连续驾驶时间，**实验性**）
- Cumulative Driving Time（累计驾驶时间，**实验性**）
- Pit Stop Window（进站窗口）
- Pit Stopwatch（进站秒表）

通用规则：所有驾驶时间计算中**维修区内的时间不计入驾驶时间**（与 HH Timing 其他驾驶时间数据一致）。
- Continuous Driving Time 显示车手在车内已用时间（**含进站**）及距最大连续驾驶时间还剩几圈；因含进站时间，**不要在 GTWC 使用**。
- Cumulative Driving Time 显示距最短/最长驾驶时间的剩余时间与剩余圈数（也含进站时间）。二者均为实验性显示。

**Assumed Pace（假设配速）**
- 插件大量前向预测的基础：假设圈速 = **最近 5 圈中最快 3 圈的平均值**。
- 选取最近 5 圈时忽略 in/out lap 以及安全车、全场黄旗等 "yellow" 圈。
- 该假设在 FCY/SC 前后配速剧变时可能不准（见 Limitations）。

**Stint Summary（stint 摘要）**
- 定位：以驾驶时间（而非传统燃油）为主要因素的策略工具；背景色 = Car Options 中定义的车辆颜色，便于识别对应车辆。可同时使用多个（跟踪本队及竞争对手）。
- **输入**（ribbon bar）：Car Number；Estimated In Lap Time（过终点线到 Pit-In 计时线的用时，决定 stint 最后一圈时长，末段除外）；Merge with previous stint（与上一 stint 合并，用于 drive-through 后统计自上次以来的 stint 时间）；Driving Time Rules（在 Track Definition 中设置）；EDS（仅当前 stint 启用 Extended Driving Stint +5 分钟，下次进站自动关闭）。
- **输出**：
  - Stint Merged：勾选合并后显示；
  - Current Stint Time：当前 stint 驾驶时间（实时递增）；
  - Session Time if Max Stint：若把当前 stint 拉满，stint 结束时的会话/比赛时间；
  - Stint Time if Box This Lap：本圈末进站时的预测 stint 时长；
  - Next Lap：完成本圈再多跑一圈后的预测 stint 时长；
  - Remaining Max Stint Time：拉满至单 stint 最大允许驾驶时间还剩多久；
  - Max Laps Remaining：拉满后还能完成的完整圈数（小数表示——如 10.2 表示再多跑 11 圈时会在赛道 20% 处超时；也反映预测裕度）；
  - Rem. Continuous Driving Time：遵守**连续**驾驶时间规则的剩余驾驶时间；
  - Remaining Total Driving Time：遵守全场**总**驾驶时间规则的剩余时间。
- **Minimum Stint Time (No Extra Stops)**：当前 stint 不至于短到被迫多停一次即可完赛的最短时长——可理解为进站窗口开启时刻。当 Current Stint Time 达到该值时替换为 "Pit Window Open" 消息（窗口会随配速演化提前/推后）。
- **Box This Lap 警告**：过线后若预测无法再完成一圈，底部红黑闪烁提示，三种触发场景：超过最大 stint 时间 / 超过最大连续驾驶时间 / 超过最大总驾驶时间。
- **Max Stint Time 与 EDS**：最大 stint 时间在 Track Definition（Driving Time Rules）中定义，是所有 stint 计算的上界；某些 SRO 赛事允许每车一名车手使用 EDS（+5 分钟，仅当前 stint，下次进站失效，按规则每车每场仅一次），激活时 Stint Summary 显示 EDS 指示。
- **注**：2017 Blancpain 规则中执行 drive-through 时维修区内时间**计入**驾驶时间，软件目前无法自动处理，需车队手动把该时间加进连续/总驾驶时间。

**Pit Stop Window（进站窗口）**
- 场景：如 DTM 要求在规定窗口（如比赛 20–40 分钟之间）进站。
- 输入：Car Number、Estimated In Lap Time、进站窗口开始（分钟）、结束（分钟）；平均圈速默认仍为最近 5 圈最快 3 圈平均（除非在 Track Item 的 Average Lap Time For a Stint 中填写）。
- 输出：Min/Max Remaining Time（距窗口开启/关闭）、Session Time if Pit after opening of PW、Session Time if Pit before end of PW、Min/Max Remaining Laps、以及随会话时间变化的倒计时状态（Pit Window open in / closed in 倒计时 → Pit Window Closed）。

**Pit Stopwatch（进站秒表）**
- 双模式：
  - **On Track**：若现在进站，预计到静止在维修位的用时；Last Stop 显示上次进站用时（更详细进站数据见 Car Scoreboard 与 Pit Stop Scoreboard）。
  - **In Pit**：顶部显示自过 Pit-In 线起的计时；底部按放行窗口状态变化——进站且最长短停放行窗口开启（绿）→ 关闭前 15 秒倒计时（橙闪）→ 窗口关闭（红）→ 最长停/最短长停放行窗口开启前 15 秒倒计时（橙闪）→ 窗口开启（绿）→ 过 Pit-Out 线回到 On Track 模式。
- **Manual Mode**：计时数据流有延迟、不信任自动触发时勾选；车进站时需用户手动点击 Pit Stopwatch 显示来触发倒计时。
- 注意：Blancpain 等计时系统可能有数据延迟导致放行窗口不精确；车队通常有自己的（如车载 GPS）计时系统，本秒表更多是备份手段。
- 输入：Car Number、Estimated In Lap Time、From Pit-In（Pit-In 到静止）、To Pit-Out（静止到 Pit-Out）、Maximum Short（短停阈值，不用可设 0）、Minimum Long（长停阈值）。

**Plugin Settings Checklist（赛前检查清单）**
- Backstage options：GTWC 中 Predicted Strategy Type 应设为 Fixed Stint Lengths。
- Stint Summary：Car Number、Estimated In Lap Time、Driving Time Rules（Track Definition）。
- Pit Stopwatch：Car Number、Estimated In Lap Time、From Pit-In、To Pit-Out、Maximum Short、Minimum Long、Manual Mode。

**Testing / Suggested Settings**
- 用历史赛事回放测试插件——从插件视角看，回放等价于连接实时计时数据流。
- Fixed Stint Lengths 建议填完整 65 分钟（而非按 2:00 圈速算出的 63 分钟），把「余量判断」留给工程师，避免每段 stint 预设 1 圈余量。

**Limitations（局限）**
1. **Race Finish Estimation**：SRO 对比赛结束时驾驶时间的定义特殊（车手驾驶时间在比赛时限到达时结束）；HH Timing 按各车相对总领跑者冲线时刻预测比赛结束，可能把末段 stint 预测得比规则实际更长。2018 起 Minimum Stint Time/PIT WINDOW OPEN 消息已按规则更新，计算更准但更激进。
2. **Assumed Pace**：FCY/SC 转换等配速剧变阶段，所有前向计算可能失准。
3. **Technical Stop**：必须在指定窗口完成的技术停不参与未来 stint 前向规划；但每车完成技术停后，其对驾驶时间的影响会计入，之后的计算准确。

## 子页 2：Making your own plugin（自研插件）

- URL：https://help.hhtiming.com/plugins/making-your-own-plugin/

### 完整要点

**框架能力**：HH Timing 基于 .NET Framework 与 WinForms 构建，插件可用任意 .NET 语言（C#、VB.NET 等）开发，UI 也必须用 WinForms。当前框架允许：
- 在 ribbon bar 创建自定义选项卡访问插件；
- 创建显示控件，以「消息」形式接收软件的计时数据；
- 在项目中创建并保存条目；
- 创建「data importers」导入 CSV、PDF 等静态文件；
- 创建「message parsers」从网络连接、HTML 网页或 FTP 服务器读取计时数据流；
- 通过 Entity Framework 访问项目数据库（需额外引用相关 EF 库）。

**创建插件的环境要求**
- .NET 9 SDK（VS 工作负载选择器或微软官网安装）；
- 最新版 HH Timing；
- 最新版 Visual Studio 2022；
- 新建 VS 项目时确保目标框架为 **`net9.0-windows`**（不一定是默认值，编码前务必核对）。

**需要引用的 HH Timing DLL**（位于默认安装目录 `C:\Program Files\HH Development\HH Timing` ，且 **CopyLocal 必须设为 false**）：
- HHTiming.Core.Definitions.dll
- HHTiming.Desktop.Definitions.dll
- HHTiming.DAL.dll
- HHDev.ProjectFramework.Definitions.dll
- （可选）HHTiming.WinFormsControls.dll——用于扩展基础控件；需要控件支持时可向官方索要资料或安排网络会议。

**关键接口**
- `IHHTimingPlugin`（命名空间 HHTiming.Desktop.Definitions.PlugInFramework）：插件入口，插件必须有一个实现该接口的类才能被加载。
- `IWorksheetControl`：workbook 中每个显示控件都是一个 "worksheet"，UserControl 需实现该接口才能显示。
- `IUIUpdateControl`：实时数据通过消息系统分发；每条消息实现 `IUIUpdateMessage`，广播给已注册的 IUIUpdateControl；控件也可请求数据库初始化消息（如某车全部圈/扇区时间）。IUIUpdateMessage 的实现都在 HHTiming.Core.Definitions.dll。
- `IProjectObject`：保存到项目的每个对象都要实现，关键是暴露 Save/Load 方法。

**调试**
- 插件只能在 HH Timing 内运行：VS 项目属性 → Debug → 启动操作设为启动 HH Timing（默认路径 `C:\Program Files\HH Development\HH Timing\HHTiming.Desktop.exe`），然后用 Start 按钮调试。

**Build Events（构建事件）**
- 插件必须位于 `Documents\HH Timing\Plugins`。
- 项目属性 → Build Events → Post-build Event Command Line 中配置（把 MyPlugin 换成自己的插件名）：Debug 配置下自动在用户文档的 `HH Timing\Plugins\MyPlugin` 创建目录并 `copy /y` 输出文件。

**使用插件**
- 若未配置构建事件，手动把压缩的插件文件夹（无需解压）放入 `Documents\HH Timing\Plugins`；启动软件后插件会出现在 ribbon bar 的独立选项卡中。

**官方可用插件**
- Drive Time Plugin：面向 GT World Challenge Endurance 车队，管理驾驶时间、stint 时长与进站时长规则（详见本文件子页 1）。
- 示例插件源码见官方 GitHub 账号。

**关联文档**：0.8.x → 0.9.x 插件升级清单见 https://help.hhtiming.com/notes/v0-9-plugin-updates/ （含 PluginInfo.json、TargetFramework、NLog v5 等破坏性变更）。

## 常见问答

- **Q：插件放哪里？** A：`Documents\HH Timing\Plugins\`（文件夹不解压），Backstage → Plugins 启用后重启软件。
- **Q：Drive Time 插件是免费的吗？** A：是，免费附加插件；下载 https://hh-dev.com/latest/HHT-DT 。
- **Q：连续/累计驾驶时间显示能在 GTWC 用吗？** A：不能直接用——它们包含进站时间；Continuous 明确标注勿在 GTWC 使用。
- **Q：假设配速怎么算？** A：最近 5 圈中最快 3 圈的平均（剔除 in/out lap 与黄旗圈）。
- **Q：自己写插件要什么？** A：.NET 9 SDK + VS 2022 + 最新 HH Timing；目标框架 net9.0-windows；引用 4 个官方 DLL（CopyLocal=false）；实现 IHHTimingPlugin；UI 用 WinForms。
- **Q：插件升级到 0.9 后不加载？** A：检查根目录 PluginInfo.json 的 TargetVersionNumber 是否为 "0.9"，并按 Notes 页完成全部破坏性变更迁移。
