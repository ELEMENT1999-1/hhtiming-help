# Videos & Notes（教学视频与附注）

## 概述

本文件汇总两个轻量章节：
- **Videos（Tutorial videos）**：官方 YouTube 教学视频，目前 2 个子页（入门、布局）。
- **Notes（附注）**：技术/运营附注，目前 2 个子页（v0.9 插件升级指南、IMSA 2026 回放文件索引）。

两章节均无独立根页（站点导航直接指向首个子页）。

## 第一部分：Videos（教学视频）

### 子页 1：Getting started（入门视频）

- URL：https://help.hhtiming.com/videos/getting-started/
- 页面标题原文拼写为 "Gettign started"（站点笔误，实为 Getting started）
- **YouTube 视频**：https://www.youtube.com/watch?v=Lndv2Ls1QDo
- 要点：HH Timing 入门教学视频，配合 Getting Started 文档章节使用。

### 子页 2：Working with layouts（布局操作视频）

- URL：https://help.hhtiming.com/videos/layouts/
- **YouTube 视频**：https://www.youtube.com/watch?v=Bzcne8Ojclc
- 要点：讲解 Workbooks 与 Layouts 基础用法；该视频同时内嵌在 Workbooks & layouts 章节首页（https://help.hhtiming.com/workbooks-layouts/ ）。

## 第二部分：Notes（附注）

### 子页 1：v0.9 plugin updates（v0.9 插件升级说明）

- URL：https://help.hhtiming.com/notes/v0-9-plugin-updates/

#### 完整要点

目的：说明将 HH Timing 插件从 **v0.8.x 升级到 v0.9.x** 所需的变更（并非所有插件都涉及全部变更）。

- **预览版本**：官方提供了 HH Timing 0.9 预览版（beta，网站 releases 页面下载），仅含少量破坏性变更，足以验证插件升级。
- **示例插件**：drive-time 插件的升级示例提交 — https://github.com/hh-development/hhtiming-drive-time-plugin/compare/master...release/2025-major

**破坏性变更（Breaking changes）清单：**

1. **TargetFramework**：把硬编码的 `net7.0-windows` 引用路径全部替换为 `$(TargetFramework)`，以便宿主迁移到 .NET 9 后插件能解析匹配的桌面二进制文件。
2. **Windows Forms**：在 csproj 的属性组中加入 `WFO1000`，避免新版 Windows Forms 分析器阻止构建。
3. **AssemblyInfo**：加入 `[assembly: SupportedOSPlatform("windows")]`——.NET 9 下 WinForms 项目需要显式 OS 目标。
4. **Logging（NLog v4 → v5）**：获取 logger 的方式已过时。
   - 旧写法（C#）：`private static ExtendedLogger _logger = (ExtendedLogger)LogManager.GetCurrentClassLogger(typeof(ExtendedLogger));`
   - 新写法（C#）：`private static ExtendedLogger logger = NLog.LogManager.LogFactory.GetCurrentClassLogger();`
   - VB.NET 同理改用 `NLog.LogManager.LogFactory.GetCurrentClassLogger(Of ExtendedLogger)()`。
5. **PluginInfo.json（新增必需文件）**：插件根目录必须放置描述插件信息的 JSON，HH Timing 加载插件时读取。示例：

   ```json
   { "EntryDll": "HHTiming.DriveTime.dll", "TargetVersionNumber": "0.9" }
   ```

   - `EntryDll`：包含 `IHHTimingPlugin` 实现的主程序集文件名；
   - `TargetVersionNumber`：插件所支持的 HH Timing 版本（当前为 `"0.9"`）。该列表随版本发布更新；出现破坏性变更时旧版本号会被移除，届时必须升级插件并更新该字段，否则插件不再被加载。

### 子页 2：IMSA 2026 replays（IMSA 2026 赛季回放文件）

- URL：https://help.hhtiming.com/notes/imsa-2026-replays/

#### 完整要点

2026 IMSA 赛季回放文件索引，按锦标赛与赛事分组（供软件内回放数据库使用；回放功能见 timing-data-management/replays 章节）。收录赛事：

**WeatherTech SportsCar Championship**
- Daytona Test（Session 1–7）
- Roar Before the 24（Session 1–7）
- Rolex 24 at Daytona（Practice 1–3、Qualifying、Race）
- Sebring 12 Hours（Practice 1–3、Qualifying、Race，其中多项含 with telemetry 遥测版本）
- Long Beach（Practice 1–2、Qualifying、Race，Race 含遥测版）
- Laguna Seca（Practice 1–2、Qualifying、Race，Race 含遥测版）
- Detroit（Practice 1–3、Qualifying、Race；部分标注 no telemetry）
- Watkins Glen（Practice 1–2、Qualifying、Race；Practice 2 与 Race 含遥测版）
- Canadian Tire Motorsport Park（Practice 1–2、Qualifying、Race，Race 含遥测版）
- Road America（Practice 1–2、Qualifying、Race，Race 含遥测版）
- VIR（Practice 1–2、Qualifying、Race）
- Indianapolis（Practice 1–2、Qualifying、Race，Race 标注 no telemetry）
- Petit Le Mans / Road Atlanta（Practice 1–3、Qualifying、Race）

**Michelin Pilot Challenge**
- Sebring 12 Hours、Laguna Seca、Mid-Ohio、Watkins Glen、Canadian Tire Motorsport Park、Road America、VIR、Indianapolis、Petit Le Mans（各站 Practice 1–2、Qualifying、Race）

**Porsche Carrera Cup North America**
- Sebring 12 Hours（Practice 2、Qualifying、Race 1–2）
- Long Beach、Watkins Glen、Indianapolis、Petit Le Mans（各站 Practice 1–2、Qualifying、Race 1–2）
- Road America（Practice 1–2、Qualifying、Race 1–2，另含 Miami Make-Up Race 2）

## 常见问答

- **Q：新手看哪个视频？** A：Getting started：https://www.youtube.com/watch?v=Lndv2Ls1QDo
- **Q：布局/工作簿怎么用，有视频吗？** A：Working with layouts：https://www.youtube.com/watch?v=Bzcne8Ojclc （也内嵌在 workbooks-layouts 首页）。
- **Q：升级到 0.9 后插件加载不了？** A：按 Notes/v0-9-plugin-updates 检查：TargetFramework、WFO1000、SupportedOSPlatform、NLog v5 写法、根目录 PluginInfo.json 的 TargetVersionNumber 是否为 "0.9"。
- **Q：哪里找 IMSA 2026 各站回放？** A：Notes/imsa-2026-replays 页面按锦标赛→赛事→会话列出全部回放文件。
