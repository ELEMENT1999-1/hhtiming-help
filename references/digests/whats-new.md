# What's New（版本更新时间线）

## 概述

What's New 是 HH Timing 的版本发布公告区（博客形式），每个版本一篇发布说明，描述新功能与重大变更；站点还提供 RSS 订阅。本页按时间线整理全部已发布版本的要点（来源：根页与 Archive 页列出的 4 篇发布说明）。

- 入口 URL：https://help.hhtiming.com/whats-new
- RSS：https://help.hhtiming.com/whats-new/atom.xml
- 归档页：https://help.hhtiming.com/whats-new/archive
- 官方约定：帮助文档（help.hhtiming.com）会随开发同步更新；每个版本在 What's New 发帖介绍所有新功能与重大变更。问题/故障联系 support@hh-dev.com。

## 版本时间线（按发布时间）

| 发布日期 | 版本 | URL |
| --- | --- | --- |
| 2023-10-25 | 2023 November Release | https://help.hhtiming.com/whats-new/2023-november |
| 2024-02-12 | 2024 February Release | https://help.hhtiming.com/whats-new/2024-february |
| 2025-04-21 | 2025 April Release | https://help.hhtiming.com/whats-new/2025-april |
| 2025-06-10 | 2025 June Release | https://help.hhtiming.com/whats-new/2025-june |

（站点根页 https://help.hhtiming.com/whats-new 当前展示的最新一篇为 2025 June Release。）

## 各版本要点

### 2023 November Release（2023-10-25 发布，约 4 分钟阅读）

- **新帮助文件**：help.hhtiming.com 换新，地址不变，随开发更频繁更新；每版本在 whats-new 发帖。
- **HH Timing 回放数据库（重大功能）**：软件内置回放数据库，可直接访问并运行历史回放（仅部分系列赛/赛事提供，范围会逐步扩大）。完整文档：timing-data-management/remote-replays-database。
- **Car Scoreboard 赛事计算**：可在车辆记分板直接显示基于比赛计算参数的未来圈（future laps），辅助实时决策并校验参数录入。
- **Alkamel**：
  - GPS 速度图表重构，默认设置面向耐力赛与 Alkamel 协议，帮助文档同步重写；
  - 退赛（retired）状态显示在主记分板 Status 列。
- **Focus on reference car**：赛道图新增缩放到参考车选项，地图随选中车辆环绕赛道移动（配合 GPS 实时定位最有用）。
- **Track limit（赛道界限）**：新增 Track Limit warning 显示控件；主记分板与车手记分板增加 track limit 计数；无效圈被记录并更新记分板与排名。
- **Live crossing order**：为幽灵车增加与前车/后车的预计时间差（gap）。
- **Lap analysis scoreboard**：可显示参考车在每圈/每个扇区的**名次**（相对全部车辆或仅显示车辆），便于按厂商/组别比较排名。
- **主记分板 past sectors**：Backstage 新增选项——完成一圈后重置所有扇区，简化多扇区系列赛的记分板视图。
- **Car off track 改进**：GPS 模式下速度检测阈值可调（默认 40 kph）；全赛道图可关闭 spotter 模式（不显示被检测车辆的箭头）。
- **IMSA/WEC 锦标赛记分板**：championship point scoreboard 可显示制造商锦标赛积分。
- **Misc**：Windows 小组件名改为「Workbook Name - Project Name」；新增「对所有控件应用过滤器」选项；加载回放时校验锦标赛配置与回放文件是否兼容。

### 2024 February Release（2024-02-12 发布，约 2 分钟阅读）

- **⚠️ 插件破坏性变更**：本版本引入插件破坏性变更，官方随版本发布了新版插件，**所有插件都需要更新**。
- **Gap graph 整合**：停用普通 gap graph，集中改进 projected gap graph（2024 年整合既有工具的目标之一）。
- **Track loops 导出**：Alkamel v2、IMSA Enhanced RMon Timing、TimeService TeamStream 等协议可获取额外 loops 列表——DATA/Sessions → 选会话 → "Copy Track Loops" 复制到剪贴板，用于创建额外扇区。
- **Stint analysis**：stint 分析显示控件加入图例（所有选中车辆的颜色编码）。
- **新协议**：新增 Perugia timing 协议。
- **Car off track**：帮助文档重写，解释全部选项。
- **Live crossing order**：新增车手组别（driver categorisation）显示选项，记分板增加 Bronze/Silver/Gold/Platinum 列。
- **Misc**：未知组别颜色由黑改为灰（避免黑底控件上看不清；仅适用于未定义车辆组别的系列赛）。

### 2025 April Release（2025-04-21 发布，约 4 分钟阅读）

- **⚠️ 布局破坏性变更**：0.8 版本打开/保存的布局无法在 0.7 版本中加载。
- **Advancing replay（回放跳转）**：回放条（右下角）新增按钮，可跳到会话中指定时间点（前后均可），无需从头回放；弹窗设置目标 elapsed time 后处理并从该时间开始播放。
- **Graphs（图表）**：散点图/移动平均图可在 ribbon bar 直接切换 X/Y 轴而无需新建图表；可从 ribbon bar 直接更改车/车手系列；可按车手组别过滤显示系列。
- **Strategy overview**：可显示 stint 时间（pit out→pit in；首/末段用比赛开始/结束时间）。
- **Virtual finish ghost car（虚拟完赛幽灵车）**：全赛道图可显示一辆按指定平均圈速行驶、恰好在会话时间归零时完赛的幽灵车，用于判断当前位置能否再多跑一圈；ribbon bar 可设置。**限制：GPS 赛道图暂不支持，待后续版本**。
- **Alkamel V2 enhanced read history**：锦标赛配置 Read History 新增强化选项，启用后处理 Alkamel 圈/扇区成绩更正消息（因赛道界限或其他处罚被删除的圈），记分板与图表相应更新。
- **IMSA IWSC GTP telemetry**：可记录并显示 IMSA GTP 遥测网站（https://www.imsa.com/gtp-telemetry/ ）的数据。在 IMSA Enhanced RMon Timing 或 Al Kamel V2 North America 协议的锦标赛配置中启用 Enable Telemetry Reading。主记分板新增列：Energy Rem、Energy Refill Time；可在 Displays → Other Graphs 的遥测图选择 Live Telem Plot Mode 绘制实时数据。**注意：IMSA 数据为非官方、1 Hz 过滤与取整，可能与真实情况不符**。
- **Indycar telemetry**：RIS 协议启用遥测记录后，同样可在遥测图 Live Telem Plot Mode 显示实时数据。

### 2025 June Release（2025-06-10 发布，约 3 分钟阅读）

- **Full Track Map 缩放**：可对一辆或多辆车（如同队车辆、勒芒安全车）在全赛道图上缩放查看；滑块手动调节缩放级别；需启用 ribbon bar 上的 Zoom On Car 选项，启用后地图自动围绕参考车动态居中。
- **Advanced Car Stopwatch（高级车辆秒表）增强**：
  - 新增 Pit Entry / Pit Exit 灯状态两列（专用复选框开启），实时反映灯号变化（如 FCY 准备/进行中红灯、FCY 结束绿灯）；
  - 所有安全车在秒表中以黄色背景高亮。
- **Quick Access to Car Scoreboard**：在主记分板任意车辆行上**双击鼠标滚轮**即可打开该车的 Car Scoreboard，无需走项目树或 ribbon bar。
- **Use Micro sectors as main sectors（WEC，实验性）**：计时数据源提供时可用微扇区（microsectors）替代标准扇区做更细粒度分析。
  - 定义格式：成对 `entry,exit`（自动命名 MS1、MS2…）或三元组 `name,entry,exit`（自定义名）；每条定义用分号 `;` 分隔。
  - 勒曼 Slow Zones 示例：`SZ1,FL,Z4;SZ2,Z4,IP1;...;SZ9,POROUT,FL`
  - 需使用专用 Track Map 才能完整支持（含幽灵车等功能）。
  - ⚠️ 注意事项：必须启用 "Use Micro Sectors As Main Sectors" 选项；服务器需更新；**实验性功能**；建议移除此前在 additional options 中输入的 SZ。

## 常见问答

- **Q：版本发布公告在哪里订阅？** A：https://help.hhtiming.com/whats-new 及其 RSS https://help.hhtiming.com/whats-new/atom.xml ；归档见 /whats-new/archive。
- **Q：升级后插件全部失效？** A：2024 February 版本含插件破坏性变更，所有插件需随版本更新；0.9 的具体迁移清单见 Notes/v0-9-plugin-updates。
- **Q：0.8 保存的布局打不开？** A：2025 April 起布局存在跨版本兼容限制（0.8 布局不被 0.7 加载）。
- **Q：回放能否跳到指定时刻？** A：2025 April 起支持 Advancing replay 跳转。
- **Q：微扇区功能要求？** A：2025 June 实验功能：启用开关 + 服务器更新 + 专用赛道图 + 数据源支持。
