# Workbooks & Layouts（工作簿与布局）

## 概述

Workbooks & layouts 章节说明 HH Timing 的窗口组织方式：**每个窗口称为一个 workbook（工作簿）**；**Layout（布局）**由一个或多个 workbook 及其显示配置组成，可保存到项目中，每次启动软件无需重复设置即可恢复同一显示配置。共 3 页：章节概览（含视频）、Workbooks 详解、Layouts 详解。

## 子页 1：Workbooks & layouts（概览）

- URL：https://help.hhtiming.com/workbooks-layouts/

### 完整要点

- HH Timing 的每个窗口都叫 workbook；一个 Layout 可包含多个 workbook，各自配置不同显示控件。
- Layout 可保存进项目，之后每次运行软件都恢复相同显示配置，零设置成本。
- 章节首页内嵌基础教学视频（与 Videos 章节的「Working with layouts」同一视频）：
  https://www.youtube.com/watch?v=Bzcne8Ojclc

## 子页 2：Workbooks（工作簿）

- URL：https://help.hhtiming.com/workbooks-layouts/workbooks/

### 完整要点

- **多窗口用途**：可创建多个 workbook 以支持多显示器设置，或在单屏上循环切换不同窗口。
- **每个 workbook 由 5 大部分组成**：
  1. **Ribbon bar**（顶部功能区）
  2. **Project tree**（左侧项目树）
  3. **Status bar**（底部状态栏）
  4. **Main workspace**（主工作区）
  5. **Backstage**（后台/文件菜单区）
- **提示**：点击项目树与主工作区之间的竖直分隔条可隐藏项目树。
- **Ribbon bar 选项卡**：Data、Displays、Components、Reports、Layout。
- 此外，工作区中**每个有可用选项的显示控件都会生成自己的 ribbon bar 选项卡**，为各控件提供一致的选项界面（各控件选项详见对应显示控件文档）。
- **提示**：双击 ribbon bar 标签可隐藏功能区腾出屏幕；按 **F12** 折叠所有标题头，进一步扩大可用空间（同 Tips & tricks / Saving screen space）。

## 子页 3：Layouts（布局）

- URL：https://help.hhtiming.com/workbooks-layouts/layouts/

### 完整要点

- **定义**：Layout = 一个或多个 workbook 的组合，每个 workbook 有自己的显示组织方式；用于每次使用时恢复软件视觉设置。常见做法是按会话类型准备不同布局（如 RACE 与 PRACTICE 各一套）。布局通过 ribbon bar 的 **Layout** 选项卡管理。

### 排列显示控件（Arranging Displays）

- 同一 workbook 上可创建多个控件，初始以**选项卡（tabs）**形式叠放，点击各控件选项卡切换。
- 可用**停靠（docking）属性**重新组织：左键按住某个控件选项卡拖到页面中部，会出现停靠方向图标；在哪个方向图标上松开左键，显示区域就按该方向划分。
- 示例：把 Full Track Map 选项卡拖入显示区并在右侧停靠图标上松开，赛道图即停靠在主显示区右侧；用同样方法可构建更复杂的布局。

### 保存与加载（Saving and Loading）

- 布局定稿后：Layout 选项卡 → **Save As** → 在 "Add New Item" 窗口命名并选择项目内的保存位置；保存后会出现在项目树中。
- **加载**：双击项目树中对应节点，或右键选择 **Load Layout**；当前激活的布局在项目树中以**粗体**显示。
- **重新保存**：对激活布局做过修改后点 ribbon bar 的 **Save**；若关闭了原布局包含的某些 workbook，会被询问是否将它们包含进新版本布局。

### 导入布局（Importing）

- Layout 选项卡 → **Import** → 选择 `*.lay` 文件 → 加入项目树后即可打开；便于用户之间、项目之间共享布局。
- 默认存储目录：

  ```
  Documents\HH Timing\Projects\PROJECT_NAME\Layouts
  ```

### 重命名工作簿（Renaming a Workbook）

- Layout 选项卡上的 **Workbook Name** 设置可重命名 workbook。
- 名称显示在 workbook 顶部，并会出现在 Windows 任务栏；对软件功能无影响，仅用于多窗口时快速识别。

## 常见问答

- **Q：workbook 是什么？** A：HH Timing 中的每个窗口；支持多显示器或单屏多窗口切换。
- **Q：怎么把两个控件左右分屏？** A：按住控件选项卡拖到显示区中部，停靠图标出现后在目标方向松开。
- **Q：布局存哪？怎么分享？** A：项目内保存；文件在 `Documents\HH Timing\Projects\<项目名>\Layouts`，用 Layout → Import 导入 `.lay` 文件即可跨项目/跨用户共享。
- **Q：当前用的是哪个布局？** A：项目树中粗体显示的节点。
- **Q：屏幕空间不够？** A：双击 ribbon 标签隐藏、F12 折叠全部标题头、隐藏项目树（见 Tips & tricks / Saving screen space）。
- **Q：有教学视频吗？** A：有，https://www.youtube.com/watch?v=Bzcne8Ojclc （亦见 digests/videos-and-notes.md）。
- **Q：新项目如何继承旧布局？** A：走 Tips & tricks 的 Switching project 流程：Layout → Import 从旧项目 `Layouts` 目录导入。
