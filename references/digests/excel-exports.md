# Excel 导出（Excel exports）

来源：https://help.hhtiming.com/excel-exports/（2 个页面）
HH Timing 提供**两种**实时 Excel 导出：Live excel export（参数级实时导出）与 Scoreboard live excel export（计分板整表快照导出）。

---

## 1. Live excel export（实时 Excel 导出）

**用途**：连接计时/记分 feed 期间把计时数据**实时**写入 Excel——适合自定义 run sheet、自定义燃油/策略计算。可导出 feed 原始数据与 HH Timing 后处理数据。

**配置步骤**：
1. 新建一个 Excel export profile 或导入已有 profile；
2. profile 加入项目后自动打开；
3. **Excel Workbook** 参数填写目标 Excel 工作簿路径。

（教程视频：YouTube VVidK-dUZzA）

**注意**：
- **不要把 run sheet 放在 OneDrive 或类似同步服务上**；
- 德语、西班牙语、意大利语等区域设置下 Excel 存在冲突，会导致圈速/分段值错误——建议把 Windows 区域设为 English，或在附加区域设置中去掉千分位点号（dot as thousand separator）。

### 导出频率与参数

**每圈结束导出**：
Lap number、Elapsed time、Lap time、Driver、Position、Position in Class、Track status、Driving time (current driver)、Stint lap number、Moving Average、Leader Lap Time、Class Leader Lap Time、Estimated Total # of Laps In Race、Stint Number、Number Of Cars Passed、Number Of Cars Passed By、Track Limits

**每分段结束或过测速点导出**：
Lap Number、Sector times、Non Track Sector times、Speed traps、Gap to Car Ahead、Gap to Car Behind

**圈结束时（如适用）**：
Pit stop time [Lap]、Time of pit in [Lap]、Time of pit out [Lap]

**进站完成后导出**：
Pit stop time、Time of pit in、Time of pit out、In driver、Out driver、Pit stop lap number、Fuel Only/Fuel & Tyres、Pit Bit

**stint 结束（pit-in）时导出**：
Stint length (# of laps)

### Additional sectors（附加分段）
若在 Championship Configuration 中添加了分段，或 feed 中携带 Non-Track Sectors（如勒芒的 Porsche、Ford、T6、T7 分段），可用 **NTSx** 参数导出；需先在 Backstage Options 中填写 Non Track Sector 数量。

### Macro（VBA 宏调用）
Excel 导出可在以下时机调用 VBA 宏：
- 新建工作表时（启用 Auto Worksheet 模式）；
- 每次向 Excel 写入新值时。

示例：每次导出值时让 Sheet1!A1 写入 `" Written"`——在 HH Timing 中按约定方式引用该 VBA 函数名即可被调用（见文档配图）。

### Run sheet 示例与上手
HH Development 提供简易 Excel run sheet 及对应 HH Timing 模板：
1. 下载 HH Timing 模板；
2. 在 HH Timing 中 **Import** 该 profile；
3. 在项目树中双击打开模板；
4. 把 Excel 路径改为你下载的 run sheet 路径。

**FAQ**
- **Q：圈速数字乱了/小数错位？** 多为区域设置冲突——切 English culture 或去掉千分位点。
- **Q：为什么不要用 OneDrive？** 同步锁文件会导致导出失败或数据错乱。
- **Q：数据多久写一次？** 按事件触发：每圈、每分段/测速点、进站后、stint 结束。
- **Q：能导非赛道分段吗？** 可以，NTSx 参数 + 在 Backstage 填分段数量。

---

## 2. Scoreboard live excel export（计分板实时 Excel 导出）

**用途**：把 **Main Scoreboard** 或 **Driver Scoreboard** 的内容作为副本写入指定 Excel 工作表——与 Live excel export 相互独立、可并行。

**行为**：每 **10 秒**向指定 Excel 区域写入一次计分板副本。

**配置入口**：相应 scoreboard 的 ribbon 控件 → **Configuration** → 填写：
- Excel workbook 路径
- 工作表名（worksheet name）
- 行/列起始位置（row/column positions）

然后点 **Start Export** 开始导出。

**典型用法**：
- **Main Scoreboard**：先用 Column Config 自定义要显示的列，可把大量数据传到外部 Excel；
- **Driver Scoreboard**：通常用于对全场做驾驶时间计算，自动识别违规车手。

**默认配置示例**：Main Scoreboard 用默认行列设置导出后，Excel 中即呈现默认计分板布局（见文档配图）。

**并行**：可同时运行**多个** Excel 导出。

**FAQ**
- **Q：两种 Excel 导出怎么选？** 需要参数级、按圈/分段触发的数据（run sheet、策略计算）用 Live excel export；需要整张计分板定期快照用 Scoreboard live export。
- **Q：导出频率？** Scoreboard 版固定每 10 秒；Live 版按圈/分段/进站等事件。
- **Q：能同时导两个 scoreboard 吗？** 可以，多个导出可同时运行。

---

## 两种导出对比

| | Live excel export | Scoreboard live excel export |
|---|---|---|
| 配置位置 | 项目中的 Excel export profile | 各 scoreboard 的 ribbon Configuration |
| 触发方式 | 按事件（每圈、分段、进站、stint 结束） | 每 10 秒整表快照 |
| 数据粒度 | 单项参数（可含原始 feed 与后处理值） | 整个计分板当前显示内容 |
| 主要用途 | 自定义 run sheet、燃油/策略计算 | 全场驾驶时间监控、通用表格 |
| 可同时运行多个 | 是 | 是 |
| VBA 宏 | 支持 | 文档未提及 |

---

## 站点导航（本章源页面）

| 页面 | URL |
|---|---|
| Live excel export | /excel-exports/live-excel-export/ |
| Scoreboard live excel export | /excel-exports/scoreboard-live-excel-export/ |
