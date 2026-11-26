# Tips & Tricks（技巧与提示）

## 概述

Tips & tricks 章节汇总 HH Timing 的日常使用技巧：项目树管理、屏幕空间节省、项目备份、路由器网络配置、复制赛道 loops 列表，以及切换项目（模板迁移）的完整流程。共 1 个概览页 + 5 个子页。

## 子页 1：Tips & tricks（概览）

- URL：https://help.hhtiming.com/tips_tricks/

### 完整要点

- **用文件夹整理项目树**：右键项目树（https://help.hhtiming.com/getting-started/project-tree ）标题可创建文件夹，左键拖拽条目移入文件夹。
- **复制项目树条目**：按住 Ctrl 键并左键拖拽即可复制条目。
- **多选项目树条目**：按住 Shift 或 Ctrl 键并左键点击。
- **新显示控件背景色默认值**：可在 scoreboard background settings 中把新控件默认背景设为白或黑（https://help.hhtiming.com/settings-options/backstage-options/#scoreboard-settings ）。
- **快速复制记分板数据**：高亮记分板数据后 Ctrl+C 即可复制到外部计算使用——这与记分板 ribbon bar 中的 CSV Export 功能是相互独立的（https://help.hhtiming.com/displays/scoreboards ）。

## 子页 2：Switching project（切换项目 / 迁移到新项目）

- URL：https://help.hhtiming.com/tips_tricks/switching-project/

### 完整要点

场景：需要创建干净的新项目（新赛季、新赛事、旧项目出问题等），同时沿用旧项目的配置。步骤：

1. **创建模板项目（Template Project）**
   - 从旧项目生成一个不含会话数据、但保留车辆颜色与模板的模板项目：Backstage → Project Management → **Create Template From Current Project**。
   - 新建项目时选择刚创建的模板。
2. **导入布局（Layout）**：Layout → Import，在旧项目目录下的 `Layouts` 文件夹中选择要导入的布局。
3. **导入 Excel 导出配置**：Data → Import Profile，在旧项目目录中找到对应配置文件。
4. **导入赛道图（track maps）设置**：若策略计算使用赛道图，可从旧项目导入相关设置。
5. **导入报告配置（Report profile）**：同样从旧项目目录导入。
6. **导入锦标赛配置（Championship Configuration）**：若使用了非默认的锦标赛配置，也可一并迁移。

## 子页 3：Saving screen space（节省屏幕空间）

- URL：https://help.hhtiming.com/tips_tricks/saving-screen-space/

### 完整要点

- **双击 ribbon bar 标签**（Data、Displays、Components 等）可隐藏 ribbon bar 腾出屏幕空间；单击折叠后的标签可临时访问 ribbon bar；再次双击标签将其重新固定在顶部。
- **F12**：同时折叠每个显示控件的标题头与 ribbon bar，最大化可用空间。
- **隐藏项目树**：把鼠标悬停在项目树与主工作区之间的分隔条上，待光标变化后左键点击即可隐藏；使用软件时往往并不需要一直显示项目树。

## 子页 4：Backing up HH Timing projects（项目备份）

- URL：https://help.hhtiming.com/tips_tricks/backing-up-hh-timing-projects/

### 完整要点

- **备份很重要，但要在 HH Timing 关闭后再备份**：硬盘可能损坏；若 HH Timing 运行期间触发 OneDrive/Dropbox/Windows 备份，大项目+弱网容易出现同步问题，导致项目数据库文件被改名，HH Timing 从此找不到数据库。
- **最常见症状**：数据库文件被备份工具改名后，软件报错「Unable to load project」。
- **修复步骤**：
  1. 打开 `我的文档（My Documents）\HH Timing\`，进入对应项目文件夹，查看 `DatabaseData` 文件夹；
  2. 正常情况下该文件夹应只有一个 `HHDatabase.hhdb2` 文件；
  3. 若存在另一个名字相似的文件（通常是 OneDrive 备份失败时新建的）：若 `HHDatabase.hhdb2` 为空文件，删除它并把另一文件重命名为 `HHDatabase.hhdb2`；
  4. 若根本没有 `HHDatabase.hhdb2`，直接把另一文件重命名为 `HHDatabase.hhdb2`。

## 子页 5：Router configuration（路由器配置）

- URL：https://help.hhtiming.com/tips_tricks/router-configuration/

### 完整要点

场景：部分系列赛的计时数据通过维修区（pit lane）网络下发，需要在同一网络中同时访问互联网与计时数据流。官方推荐使用商用路由器（如 Ubiquiti EdgeRouter X）作为低调可靠的方案。

路由器设置分 4 部分（管理页通常为 https://192.168.1.1 ）：

1. **Interfaces（接口）**
   - Eth0 端口用于计时连接，使用固定 IP；计时接入接口参数需向计时提供商索取。
   - Eth1–Eth4 为用户连接，无需特殊配置。
2. **Routing（路由）**
   - 互联网路由走互联网接入接口（例：192.168.1.2）；
   - 计时路由走计时接口（例：10.10.105.1）。互联网接入参数向网络服务商索取。
3. **DHCP**
   - DNS 1 设为计时提供商的 DNS（例：10.10.105.1）；
   - DNS 2 设为 Google DNS（8.8.8.8）。
4. **DNS Forwarding（DNS 转发，Alkamel）**
   - 若计时商使用 DNS 服务器，需配置 DNS 转发：把 eth0 上的 DNS 请求经计时连接转发到 Alkamel DNS。

## 子页 6：Get loops list（复制赛道 loops 列表）

- URL：https://help.hhtiming.com/tips_tricks/copy-loops-list/

### 完整要点

- 对部分协议（**Alkamel v2、IMSA Enhanced RMon Timing、TimeService TeamStream**）可以获取赛道 loops 列表。
- 操作：点击 DATA/Sessions 下的会话名称，再点击 **"Copy Track Loops"**，loops 列表即复制到剪贴板，可用于创建额外的计时扇区（sectors）。
- （该功能也在 2024 February 版本更新中正式宣传，见 What's New。）

## 常见问答

- **Q：如何复制项目树里的某个显示？** A：Ctrl + 左键拖拽。
- **Q：如何在不丢配置的情况下开新赛季项目？** A：用「Create Template From Current Project」建模板，再按 Switching project 页逐项导入布局/Excel 配置/赛道图/报告/锦标赛配置。
- **Q：报 "Unable to load project" 怎么办？** A：多半是备份工具改名了数据库，见 Backing up 页的 DatabaseData 修复步骤；以后务必先退出软件再备份。
- **Q：维修区网络既要计时又要上网怎么办？** A：按 Router configuration 页配置 EdgeRouter X（接口/路由/DHCP/DNS 转发四步）。
- **Q：怎么拿到 loops 列表？** A：DATA/Sessions → 会话名 → Copy Track Loops（需协议支持）。
- **Q：屏幕太小怎么腾空间？** A：双击 ribbon 标签、按 F12、隐藏项目树（见 Saving screen space）。
