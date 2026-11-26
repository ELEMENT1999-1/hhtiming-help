# Getting Started（入门）

## 章节概述

Getting Started 章节覆盖 HH Timing 的安装运行、HH Development 官网账户、软件主界面三大区域（Ribbon Bar / Project Tree / Displays Area）以及 Projects 项目体系。用户从下载安装、license 激活开始，再通过 Backstage 的 Project Management 创建/加载项目，随后在 Workspace 中配置 displays、components 与 data。本章是后续 Workbooks & layouts、Displays、Timing data management、Settings 等章节的基础入口。

---

## Installing and running HH Timing

原文URL：https://help.hhtiming.com/getting-started/installation/

### 安装软件（Installing the Software）
- 下载 HH Timing 安装包后会得到一个可执行安装程序（installer，exe 形式）。
- 运行该可执行文件即可安装；安装程序会自动确保所有 prerequisites（前置依赖/运行库）正确安装。
- 安装过程成功完成后会给出成功通知。

### 首次启动（Starting HH Timing for the First Time）
- 安装完成后可通过桌面快捷方式（desktop shortcut）或开始菜单（start menu）启动。
- **首次启动**会弹出 license 对话框（license dialog）。
- **没有 license key**：可进入 **demo mode**，功能完整（fully functional），为期 **30 天**。
- **有 license key**：在对话框中输入 code，点 **OK** 继续。
- 提示（tip）：license key 可直接复制粘贴到文本框；在 HH Development 网站上**左键点击** license key 即可将其复制到剪贴板（clipboard）。

### 相关链接
- License key 说明见 Versions & license：https://help.hhtiming.com/getting-started/website/versions-license/#license-keys

---

## Workspace

原文URL：https://help.hhtiming.com/getting-started/workspace/

HH Timing 主界面（Workspace）分为三大区域：

### Ribbon Bar
- 位于界面**顶部**的标签页区域（tabs），集中了软件的主要控件/操作入口（main software controls）。
- 具体标签页包括：File、Data、Displays、Components、Reports、Layout 等，详见 Ribbon bar 章节。

### Project Tree
- 位于界面**左侧**的树状面板。
- 用于访问并配置 **displays**、**components**、**data** 三大类项目内容。
- 对应子页面：Project Tree 总览及其 Displays / Components / Data 子页。

### Displays Area
- 主工作区，用于**排布（arrange）**各类显示组件以可视化数据。
- 典型 displays 包括：
  - **scoreboards**（记分牌/排行榜）
  - **track maps**（赛道图）
  - **clocks**（时钟）
  - 以及其他可视化 displays

---

## Projects

原文URL：https://help.hhtiming.com/getting-started/projects/

### 项目是什么
- Project 用于存储**配置（configuration）**以及**计时与评分数据（timing and scoring data）**。
- 创建新项目时需指定计算机上的保存位置；HH Timing 会据此创建一整套**目录结构（directory structure）**存放全部数据。
- 在软件中，项目通过 **Project Tree** 表示。

### 重要限制（Info）
- 目前 HH Timing 项目**不设计用于承载多个锦标赛（multiple championships）**。
- 一个项目的预期范围是**一个 championship**。
- 每个不同的 championship 都需要创建**单独的项目**。

### 项目管理入口
- **Project Management** tab 位于 **backstage**（File 选项卡后的后台界面）。
- 可在此：创建新项目、加载已有项目、创建模板项目（template projects）。

### 项目生命周期（Project lifetime）
- 设计目标：每次使用软件时维持一套**自定义环境**。
  - 例如：赛车颜色（colours of the cars）保存在项目中，每次启动软件车辆颜色保持一致。
- 引入 project 概念的原因：用户会在多个 championship 中使用软件，需要为不同 championship 保留不同配置。
- 项目除配置外，还包含所有**已导入或已录制**的计时数据，以 **session** 形式存储。

### 使用建议（Suggestion）
- 建议**一个 project 对应一个赛季（season）+ 一个 championship**。
- 原因：软件中**赛车编号（car numbers）**是车辆之间的主要标识（primary identifier）；若把不同 championship/赛季的数据混在同一项目中，会导致**车手与赛车错误关联**的问题。

---

## Creating a new project

原文URL：https://help.hhtiming.com/getting-started/projects/creating-new-project/

### 创建步骤
1. 打开 **File** 选项卡 → **backstage** 中的 **Project Management** tab。
2. 点击 **Create New Project** 按钮。
3. 弹出 **New Project** 窗口。

### New Project 窗口中可配置项
| 配置项 | 说明 |
|--------|------|
| **Name** | 新项目的名称 |
| **Location** | 新项目在计算机上的保存位置 |
| **Template Project** | 可选：基于哪个**模板项目**创建（新项目将继承其配置） |

---

## Access（官网访问）

原文URL：https://help.hhtiming.com/getting-started/website/access/

### 网站地址
- **HH Development portal** 面向所有拥有 HH Development 用户账户的人开放。
- 网站地址：**hh-dev.com**
- 入口：屏幕**右上角**的 **Log In** 链接。

### 登录（Website Login）
- 进入登录页（sign-in page）。
- 每个用户在账户创建后会收到一封**介绍邮件（introduction email）**，内含如何设置密码的说明。

### 忘记密码
1. 在 hh-dev.com 登录页点击 **Forgot Password**，按屏幕指示操作。
2. 输入 **Username（即邮箱）**，点击 **Submit**。
3. 系统会向该账户邮箱发送一封含**密码重置链接**的邮件。

### 登出（Logout）
- 点击网站**右上角**的用户**首字母头像（initial）**。
- 再点击 **Logout**。

---

## Versions & license

原文URL：https://help.hhtiming.com/getting-started/website/versions-license/

### 官网导航
- 左侧**树形导航（tree）**完成站点导航。
- 树中可见选项**取决于用户权限级别（user permission level）**。

### 获取 HH Timing 发布版本
1. 打开 **Releases** Tab。
2. 默认展示**最新可用版本**，可直接下载。

**固定链接（tip）**：始终可通过以下链接获取最新发布版：
```
hh-dev.com/Latest/HHT
```

### 下载旧版本
- 在每个下载项的 **Version** 选择器中切换，即可找到**旧版本（Older versions）**。

### Release type（发布类型）
| 类型 | 含义与处理建议 |
|------|----------------|
| **Required** | 包含重大变更（如为新功能引入新 database schema）。旧版本很可能**无法工作或处于不稳定状态**——必须更新。 |
| **Recommended** | 修复了重要部分或重大 bug。不更新软件仍可运行，但建议**下次关闭软件时更新**。 |
| **Optional** | 软件的小改进或功能新增。 |

### License Keys
- 账户的 license keys 通过 **License Keys** Tab 查看。
- 这些 key 可用于安装时的 license 对话框激活（见 Installation 页）。

---

## Users（官网用户管理）

原文URL：https://help.hhtiming.com/getting-started/website/users/

> **权限说明**：本节仅 **Account Admin** 用户可访问。

### 导航
- 位于官网的 **Admin** 子栏目下。

### 两种用户类型（User type）
| 类型 | 权限 |
|------|------|
| **Account Admin** | 添加/移除用户（Add/remove users）；发布插件（release plugins） |
| **User** | 访问账户下所有软件的最新版本；访问 license key |

### 添加新用户（Add new user）
1. 在用户列表页，点右上角 **Add New User**。
2. 在新窗口填写：
   - **Email Address**：必须是**可用邮箱**——设置密码的初始邮件将发到此地址。
   - **Display Name**：网站上用于指代该用户的显示名称。
   - **Permission Level**：选择 **Account Admin** 或 **User**。

### 编辑 / 移除用户
- **Edit User**：在用户列表中点击对应按钮编辑。
- **Remove User**：在用户列表中点击对应按钮移除。

### 注意事项
- **务必始终保留至少一个 Account Admin 用户**，否则将无法再登录官网管理后台。

### 邮件列表偏好（Mailing List Preferences）
- 任何用户都可管理自己订阅的 mailing lists。
- 步骤：左侧面板点 **Options** → 勾选目标 mailing lists → 点 **Save Mailing Preferences** 保存。

---

## Ribbon bar

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/

- **Ribbon Bar** 是用户界面**顶部**的区域，集中了大量用户控件（user controls）。
- 本章下辖六个标签页子页面：
  1. **File** — 项目管理、选项、服务、插件、帮助、关于
  2. **Data** — 实时数据连接/回放/排名模式/导入
  3. **Displays** — 创建各类可视化 displays
  4. **Components** — 配置 Car / Category / Tyre / Track / Championship
  5. **Reports** — 创建 report profiles
  6. **Layout** — 组织与自定义 displays 布局

---

## Ribbon bar — File

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/file/

### Project Management
| 操作 | 说明 |
|------|------|
| **Create new project** | 创建新项目 |
| **Open existing project** | 打开已有项目 |
| **Create project template from current project** | 将当前项目保存为**模板项目** |

### Options
- 大多数软件设置与选项（settings and options）集中于此。

### Service
#### Submit statistics data to HH Timing
- **手动**提交统计数据并更新部分软件元素。
- 只要计算机有**互联网连接**，这些操作通常在**每次启动软件时自动完成**。
- 注意：要让统计数据发送与更新**自动**进行，必须在 **Options** 中将对应项设为 **True**。

#### Update all track maps and report definitions
- 向服务器发起检查，确保所有 **track maps** 与 **report definitions** 为最新。
- 主要用途：赛事期间发布了新赛道图时，**无需重启软件**即可更新 track map。
- 注意：该功能会检查云端服务器，**需要互联网连接**。

### Plugins
- 查看软件当前可用的插件（plugins），并控制哪些插件处于**激活（active）**状态。

### Help
- 访问各类帮助资源（help resources）的入口。

### About
可查看：
- **Software version**（软件版本）
- **Computer and operating system details**（计算机与操作系统信息）
- **Computer IP address**（本机 IP）
- **License information**（许可证信息）

---

## Ribbon bar — Data

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/data/

### 连接与会话控制
| 按钮/功能 | 说明 |
|-----------|------|
| **Connect** | 连接到**实时数据源（live data feed）** |
| **Disconnect** | 断开实时数据源 |
| **Load Replay** | 加载此前 session 的 **replay**（回放） |
| **Select Active** | 激活当前项目中已包含的某个 **session** |
| **Replay** | 回放当前项目中的某个 session |
| **Recover** | 见下方说明 |

### Recover（恢复）
- 用途：将之前的数据**重新载入 scoreboard**。
- 场景：计算机或软件故障导致需要在 session 中途重连，且 scoreboard 已被清空。
- 重连后，**旧数据会追加（appended）到实时数据之后**，整体作为**同一个 session** 处理。

### 排名模式
#### Race/Timed Switch
- 显示 **RACE** 或 **TIMED**，决定 session 中车辆如何排名：
  - **Race 模式**：按**行驶距离（distance traveled）**排名。
  - **Timed 模式**：按**最佳圈速（best lap time）**排名。

#### Auto Race Mode Checkbox
- 勾选后，软件根据当前数据**自动切换**到正确的排名模式。
- 多数系列赛表现良好；但部分系列赛（如 **VLN**）的 **session type 不包含在数据中**，软件无法自动识别。
- 此时需**取消勾选 Auto Race Mode**，再手动点击 **Race/Timed Switch**（取消勾选后该开关变为可用/active）覆盖 session 类型。

#### WEC Qualifying Sort Checkbox
- **WEC** 排位赛使用**两位车手最佳单圈的平均值**排名。
- 勾选 **WEC Qualifying Sort** 后，软件按此标准排名。
- **必须在 WEC 排位 session 中手动开启/关闭**（不会自动生效）。

### 数据导入与 Excel 导出
| 功能 | 说明 |
|------|------|
| **Import T&S Data** | 导入官方发布的 **Timing and Scoring data** |
| **New Excel Export Profile** | 创建新的 **Excel export profile** |
| **Import Excel Export Profile** | 从其他 HH Timing 项目导入已有的 Excel export profile |

---

## Ribbon bar — Displays

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/displays/

- 所有用于**数据可视化（visualising data）**的 displays 都在 **Displays Ribbon Bar** 中创建。
- 典型 displays：scoreboards（记分牌）、graphs（图表，如 scatter）、track maps、clocks 等。
- 各 display 的详细用法与操作，参见文档站点的 **Displays** 章节（https://help.hhtiming.com/displays/）。
- 创建出的 displays 会出现在 **Displays Area**，并可在 **Project Tree → Displays** 中管理为模板。

---

## Ribbon bar — Components

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/components/

### Car（赛车）
| 操作 | 说明 |
|------|------|
| **Add New** | 向项目添加新赛车 |
| **Filter Tree** | 配置过滤方法 |
| **Add Filter** | 定义新过滤器（filter） |
| **Car Options** | 自定义赛车**颜色（colours）**、**线型（line styles）**等；这些设置**在软件内全局生效（apply globally）** |

### Category（类别）
- **Add New**：定义新的 **Car Category**。
- 用途：当需要按与 timing data 中不同的方式对车辆分组时使用。

### Tyre Manufacturer（轮胎制造商）
- 定义自定义轮胎制造商，可分配给各辆赛车。
- 默认已内置 **Dunlop** 与 **Michelin**（见 Project Tree — Components）。

### Track（赛道）
| 操作 | 说明 |
|------|------|
| **Add New** | 定义新 **Track Item**，赛道特定设置保存在对应 Track Item 中 |
| **Import** | 从其他项目导入 Track Item |
| **Select Contour** | 为当前激活的 Track Item 选择 **track contour（赛道轮廓/赛道图）** |

### Championship（锦标赛）
| 操作 | 说明 |
|------|------|
| **Add New** | 创建新 **Championship Item**；用于定义实时连接的 **timing protocol**、**network configuration** 及其他锦标赛特定设置 |
| **Import** | 从其他项目导入 Championship Item |
| **Select Active** | 打开当前激活的 Championship Item |

---

## Ribbon bar — Reports

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/reports/

- **Report profiles** 在此创建与管理。
- 生成和使用 reports 的详细信息，参见 **Reporting** 章节：
  - https://help.hhtiming.com/reporting/making-reports
- 创建后的 report profiles 会出现在 **Project Tree → Data → Report Profiles**，可双击编辑。

---

## Ribbon bar — Layout

原文URL：https://help.hhtiming.com/getting-started/ribbon-bar/layout/

- **Layouts** 用于**组织（organise）**并**自定义（customize）**项目中的 displays。
- 详细用法参见 **Workbooks & layouts** 章节：
  - https://help.hhtiming.com/workbooks-layouts
- 保存后的 layout 会出现在 **Project Tree → Displays → Layouts**，可右键 **Load** 加载。

---

## Project Tree

原文URL：https://help.hhtiming.com/getting-started/project-tree/

### 位置与作用
- 位于软件**左侧**。
- 包含部分**项目配置信息**与 **session 数据**。

### 三大分区
1. **Displays** — 记分牌模板、图表模板、屏幕布局
2. **Components** — 赛车、类别、轮胎、过滤器、赛道、锦标赛配置
3. **Data** — Sessions、Report Profiles、Excel Export Profiles

### 折叠/展开技巧（tip）
- 将鼠标悬停在**分隔树与其余区域的竖条**上，**左键点击**即可**折叠**树。
- 再次点击该竖条可**重新显示**树视图。

---

## Project Tree — Data

原文URL：https://help.hhtiming.com/getting-started/project-tree/data/

**Data** 标题下展示项目中的计时数据、Report Profiles 与 Excel Export Profiles。

### Sessions
- 项目中使用过的 **Session Data** 列在 **Sessions** 下。
- **加粗（bold）**的 session 为**当前激活（active）**的 session。
- **右键 → Activate** 可将其他 session 设为激活。
- 该列表同时包含 **Static**（静态）与 **Replay**（回放）数据。

### Report Profiles
- 项目中的 report profiles 列在 **Report Profiles** 下。
- **双击**某个 Report Profile 即可**打开编辑**。

### Excel Export Profiles
- 项目中的 Excel export profiles 列在 **Excel Export Profiles** 下。
- **双击**某个 Export Profile 即可**打开编辑**。

---

## Project Tree — Displays

原文URL：https://help.hhtiming.com/getting-started/project-tree/displays/

**Displays** 分区展示项目内自定义的 scoreboards、graphs 与 screen layouts。

### Scoreboard Templates
- 自定义的 **scoreboard** 可保存为**模板（template）**复用。
- 操作：在树项上**右键 → Open**，即可将该 scoreboard 加入**当前 layout**。

### Graph Templates
- 自定义的 **graph** 可保存为模板复用。
- 操作：在树项上**右键 → Open**，加入当前 layout。

### Layouts
- 已保存的 **screen layouts** 存储在此。
- 操作：**右键 → Load** 加载该 layout。

---

## Project Tree — Components

原文URL：https://help.hhtiming.com/getting-started/project-tree/components/

### Car Configuration
- 项目加载过数据后，数据中的**赛车编号（car numbers）**会列在 Car Configuration 下。
- **双击**某辆车是打开该车 **car scoreboard** 的方式之一。

### Category Configuration
- 列出项目中所有 car numbers 的类别（categories，由 timing data 定义）。
- **双击**某个 category 打开其 options，可定义**新的 category colour**，该颜色将在**整个软件中使用**。

### Tyre Manufacturer
- 软件默认定义了 **Dunlop** 与 **Michelin** 轮胎。
- 各车的轮胎制造商**通常不在 timing feed 中**，如需使用可在 **Car Options** 中**手动分配**。
- 这些值可用于在 **track maps** 中对车辆着色。

### Car Filters
- 已创建的 **Car Filters** 列在此处。

### Tracks
- 新项目始终包含一个 **Default Track**。
- 其他生成的 **track items** 也会出现在赛道列表中。
- **加粗**的赛道为**当前激活**赛道；**右键 → Activate** 可切换激活。

### Championship Configuration
- 用于定义锦标赛特定信息，包括 **timing protocol** 与 **connection details**。
- 默认会列出若干 championship configurations；**加粗**的为当前激活项。
- **右键 → Activate** 可切换激活的 championship configuration。

---

## 常见问答要点

**Q1：没有 license key 能用 HH Timing 吗？**
A：可以。首次启动时若不输入 license key，可进入 **demo mode**，功能完整，期限 **30 天**。

**Q2：license key 从哪里获取？如何输入？**
A：在 hh-dev.com 登录后进入 **License Keys** Tab 复制。安装后首次启动的 license 对话框中可直接粘贴；在网站上**左键点击** key 即可复制到剪贴板，点 **OK** 激活。

**Q3：一个项目可以放多个锦标赛/多个赛季的数据吗？**
A：不建议，也不在设计范围内。一个 project 的预期范围是**一个 championship**；且建议**一个 project 对应一个赛季**，否则因 car numbers 是主要标识，容易造成车手与赛车关联错误。每个 championship 应创建独立项目。

**Q4：如何创建新项目？可以基于模板吗？**
A：File（backstage）→ **Project Management** → **Create New Project**，在 New Project 窗口填写 Name、Location，并可选择 **Template Project** 作为基础。

**Q5：RACE 和 TIMED 排名模式有什么区别？什么时候要手动切换？**
A：**RACE** 按行驶距离排名，**TIMED** 按最佳圈速排名。勾选 **Auto Race Mode** 时软件自动选择；若 series 的数据不含 session type（如 VLN），需**取消 Auto Race Mode** 后手动点 **Race/Timed Switch**。WEC 排位还需另外手动开启 **WEC Qualifying Sort**（按两车手最佳单圈平均值排名）。

**Q6：电脑故障导致 scoreboard 清空，如何恢复？**
A：重新连接后使用 Data 区的 **Recover**：将之前的数据重新载入 scoreboard，并**追加**到实时数据之后，整体仍作为同一 session 处理。

**Q7：赛事期间发布了新赛道图，必须重启软件吗？**
A：不必。使用 File → Service → **Update all track maps and report definitions** 检查云端服务器即可更新（需联网），无需重启。

**Q8：官网忘记密码怎么办？谁可以管理用户？**
A：在 hh-dev.com 登录页点 **Forgot Password**，输入 Username（邮箱）提交，按邮件链接重置。用户管理仅 **Account Admin** 可用；**务必至少保留一个 Account Admin**，否则无法再进管理后台。

**Q9：轮胎品牌默认有哪些？数据里没有轮胎信息怎么填？**
A：默认内置 **Dunlop** 与 **Michelin**。timing feed 通常不含轮胎制造商，需在 **Car Options** 中手动分配；可用于 track map 上的车辆着色。

**Q10：如何在 Project Tree 中切换激活的 session、赛道或锦标赛？**
A：统一操作——在树中**右键 → Activate**。激活项在树中以**加粗**显示（Sessions / Tracks / Championship Configuration 均如此）。
