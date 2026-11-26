# Reporting（报告功能）

## 概述

Reporting 章节介绍 HH Timing 的报告工具：快速生成计时报告，并保存为**无需 HH Timing 即可查看**的格式（PDF 与 HTML），便于分享给车手和团队成员。共 3 页：概览、制作报告、查看报告。

## 子页 1：Reporting（概览）

- URL：https://help.hhtiming.com/reporting/

### 完整要点

- 报告功能的目的：快速生成计时报告，并保存为无需 HH Timing 即可查看/交互的格式。
- 两种输出格式：
  - **HTML 格式**：用浏览器打开；优势是**保留一定交互性**（见 Viewing reports），在参赛车辆很多的活动中更灵活实用。
  - **PDF 格式**：用任意 PDF 阅读器打开；与 HTML 不同，它是**静态的**，不可做任何操作。

## 子页 2：Making reports（制作报告）

- URL：https://help.hhtiming.com/reporting/making-reports/

### 完整要点

HH Timing 目前有 3 种报告类型：**Quick report（快速报告）、Auto report（自动报告）、Custom report（自定义报告）**。

#### Quick Report（快速报告）

- 作用：把项目中**当前打开的显示控件**复制成 HTML 报告，各控件的过滤器与配置都会被保留并复刻。
- 入口：Reports 选项卡中的 Quick Report 按钮。
- 点击后每个显示被复制进一个 HTML 文件，并用默认浏览器自动打开；如需分享可在浏览器中保存该文件。
- 仅与报告相关的显示会被打印——例如赛道图（track maps）不会加入报告。

#### Auto Report（自动报告）

- 作用：以最少输入快速产出**标准格式**的详细报告。
- 创建：Reports 选项卡 → **New Profile**，命名报告配置；新配置会出现在左侧项目树中。
- **Report Configuration（标题页）**：
  - 可填写标题页详细信息；"Car(s)" 字段中输入的车号会在报告开头生成车手与报告颜色的汇总表；
  - 必须勾选 "Include Title Page" 标题页才会包含在报告中；
  - "Report title" 决定保存的文件名。
- **定义内容**：进入 Auto Report 选项卡 → ribbon bar 的 **Add Chapter** 添加章节。一般每个会话一个章节（每场 Free Practice、Qualifying、Race 各一章）。
- 章节可配置项：
  - **Report Structure（结构模板）**：Endurance Race、Endurance Timed Session、Multi Session Summary（仅 Multi Session Summary 可选多个会话，其余只能选单个会话）。
  - **Chapter Name**：章节名（如 FP1）。
  - **Session Selection**：该章节报告哪个会话。
  - **Car Selection**：包含哪些组别，可展开细化到单车。
  - **Focus Cars**：需要更详细分析的车（通常是本队车辆），会附加额外图表并在表格中高亮。
  - **Copy Car Selection to all Chapters**：把本章车辆选择复制到所有章节，多章节时省时。
- 生成：ribbon bar 的 **Generate Auto Report**，按 Report Configuration 定义的格式（HTML、PDF 或两者）自动打开。
- 保存位置：

  ```
  C:\Users\USER NAME\Documents\HH Timing\Reporting
  ```

#### Custom Report（自定义报告）

- 与 Quick Report 类似，基于项目中当前活跃的显示与数据，区别在于：
  1. 可像 Auto Report 一样定义标题页；
  2. 生成后保存到与 Auto Report 相同的目录；
  3. 用户可控制每个显示的展示顺序；
  4. 可从报告中移除显示；
  5. **格式可保存并在以后对其他会话复用**。
- 操作：Custom Report 选项卡 → ** Populate Report** 复制当前活跃的全部显示 → 调整顺序/取舍 → **Generate Custom Report** 生成（同样按配置格式自动打开并保存到 Reporting 目录）。

## 子页 3：Viewing reports（查看报告）

- URL：https://help.hhtiming.com/reporting/viewing-reports/

### 完整要点

- HTML 报告创建后会在浏览器中自动打开。
- 报告的意义：与**没有 HH Timing 的人**共享计时信息。HTML 与 PDF 报告生成后都保存在：

  ```
  Documents\HH Timing\Reporting
  ```

- **HTML 报告的交互能力**（相对 PDF 的优势）：
  - 可在记分板中高亮车辆；
  - 点击列头可按任意列重新排序记分板；
  - 图表可缩放；
  - 可在图表中高亮/隐藏某些系列（series）。
- HTML 报告顶部有控制栏：右上角图标打开**目录页**，可直接跳到某个章节/小节而无需滚动；**"i" 图标**打开报告相关的基础帮助信息。

## 常见问答

- **Q：报告有哪几种？** A：Quick（当前显示直接转 HTML）、Auto（章节模板式标准报告，可保存 Profile）、Custom（基于当前显示但可调顺序/可保存复用）。
- **Q：生成的报告存在哪？** A：`Documents\HH Timing\Reporting`。
- **Q：HTML 和 PDF 怎么选？** A：要交互（排序、高亮、图表缩放、目录跳转）用 HTML；要静态分发用 PDF；Auto/Custom 可同时输出两种。
- **Q：报告里怎么高亮本队车辆？** A：Auto Report 用 Focus Cars；HTML 报告查看时直接点击高亮。
- **Q：赛道图会进报告吗？** A：Quick Report 只打印与报告相关的显示，赛道图不会加入。
- **Q：标题页没出现？** A：检查 Report Configuration 中 "Include Title Page" 是否勾选。
