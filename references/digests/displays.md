# Displays 章节概述

> 原文URL：https://help.hhtiming.com/displays/

Displays（显示面板）用于可视化 HH Timing 处理后的计时数据。本章按子组划分：Scoreboards（计分板）、Track maps（赛道地图）、Graphing（图表）、Overviews（策略/圈速总览），以及若干独立 display（Filtering displays、Clocks、Car off track、Track Limits Warning、Race Control Messages、Pit Light Display、Track gap display、Connection Status）。每个 display 通常从 Displays ribbon tab 打开，通用配置（字体、颜色、过滤、参考车等）大多位于 ribbon bar 或 Backstage Options。

# Scoreboards 子组

## Scoreboards（共通功能）

> 原文URL：https://help.hhtiming.com/displays/scoreboards/

Scoreboards 是 HH Timing 最主要的 display 类型之一，所有计分板共享以下功能：

- **Car Ranking（车辆排名）**：计时赛默认按 best time 排名，正赛按 distance completed（已完成距离）排名。点击任意列头按该列升序重排，再点击一次降序。
- **Car Highlighting（车辆高亮）**：双击计分板中的某辆车，或使用 ribbon bar 的 **Highlight All Rows** 按钮，可按 Car Options 中定义的车辆颜色着色，便于快速定位目标车。
- **Font Control**：ribbon bar 提供字体控制，可按屏幕物理尺寸与分辨率调整计分板文字大小和字体。
- **Time Format**：默认时间格式为 `m:ss.0`，可手动改为纯秒数显示，便于计算或与其他数据源比对。
- **CSV Export**：ribbon bar 的 CSV Export 按钮可将任意计分板导出为 CSV；也可直接选中单元格 Ctrl+C 复制粘贴。
- **Filtering**：计分板支持按 class（组别）或 car number（车号）过滤，详见 Filtering displays。
- **Delta with Heat Map（差值热力图）**：大多数列可通过右键将该列变为相对参考值的 delta 显示。
  - 单击右键循环：delta 值 → delta 百分比（%）→ 取消 delta。
  - 双击右键循环：全表所有列 delta 值 → 全表 delta % → 全表取消 delta。

## Main scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/main-scoreboard/

默认配置的主计分板，除跟踪总排名外还有大量用途，是软件中可配置性最强的元素之一。

- **Column Config**：ribbon bar 的 Column Config 按钮打开列配置，可选择显示哪些值、调整列顺序（用左侧按钮或在 Column Order 列直接输入索引）；适用时可将列显示为相对指定车的 delta。
- **Tip**：参数极多，建议用配置窗口内的 Search 功能快速查找参数。
- **Last Sectors**：显示 last sector times（上一圈分段）列时，用 Backstage Options 的 *Reset last sectors every lap* 控制：禁用 Clear Sectors 时保留上一圈分段信息，启用时在越过 S1 后清空。
- **Scoreboard Export**：主计分板可自动导出到外部 Excel workbook（Scoreboard Live Excel Export），用于外部计算。
- 计时赛/正赛默认排名规则与共通的 Car Ranking 一致。

## Car scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/car-scoreboard/

单车详情计分板，打开方式：在项目树 COMPETITORS/Car Configuration 下双击某辆车；点击 Displays ribbon 的 Car Scoreboard 按钮；在 Strategy overview 上双击车号。ribbon bar 控件内可直接切换所选车辆。包含多个标签页（tabs）：

- **All Laps**：该车本节所有已完成圈的列表。
  - 圈色规则：IN laps 红色、OUT laps 蓝色、FCY/SC/VSC 圈黄色。
  - 默认最优高亮：PURPLE=全场最佳、ORANGE=组别（category）最佳、GREEN=该车最佳、CYAN=该车该驾驶员最佳；可在 Backstage Options（Scoreboard settings）自定义。
  - 默认列：Lap #、Elapsed、Lap time、Driver、Sectors、Top Speed。
  - 可通过 Column Config 追加的列：Stint Lap #、In Lap Time、Out Lap Time、Pit Stop Time、Comments、Stint Tyre Set（仅 feed 提供轮胎规格的系列，目前 Indycar 和 Supercars）、PowerMode（仅 Formula E）、Joker（部分系列）、TrackLimits（该圈是否因 track limits 无效，True/False；目前支持 Alkamel、Swiss Timing、Natsoft XML）、Lap Type（On Track / In Lap / Out Lap）、Flag Type（过 S/F 线时的赛道状态）、P（圈末总排名）、PIC（圈末组别排名）。
  - **Track limits highlight**：检测到 track limits 时该圈对应列红色高亮。
  - **Show future laps**：仅 Race mode 且启用 race calculation 时可用；按 HH Timing race calculation 显示预测的未来圈（灰色背景），用于校验比赛完赛计算相关设置。
- **Best Laps**：该车性能摘要——best lap time、做出该圈的圈次、best theoretical lap、各最佳分段与 trap speed。
- **Pit Stops**：该车所有进站摘要——进站圈、停站时长、进站发生时刻、进站前后驾驶员；最后一列基于用户输入阈值区分“仅加油”与“加油+换4胎”所需时间（仅耐力赛使用）。
- **Stints**：每个 stint 的性能摘要。
- **Drivers**：每位驾驶员总驾驶时间摘要。

## Driver scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/driver-scoreboard/

列出全部驾驶员，用于快速了解全场驾驶员的相对表现和驾驶时间。支持 Scoreboard Export 自动导出到外部 Excel workbook。

## Best sector scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/best-sector-scoreboard/

汇总最佳 Lap Time、Theoretical Lap（理论最佳圈）、Rolling Lap（滚动最佳圈）、Sector Times、Speed Trap(s)。与其他计分板不同：**每辆车在每一列各自排名**；高亮各车可快速判断相对性能。可切换选项显示“x 最快分段/极速的平均值”或“x% 最快的平均值”；x Best / x Best % 使用的圈数在 Backstage Options 中定义。

## Yellow flag scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/yellow-flag-scoreboard/

汇总本节计时 feed 中出现的所有 caution period（黄旗时段），至少显示 FCY、SC、VSC；若该系列在 feed 中传递 local yellow flag（局部黄旗）信息，也会一并显示。

## Pit stop scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/pit-stop-scoreboard/

每辆车每次进站的汇总；**Pit #1 是每辆车最后一个 stint**（编号从后往前数）。每站信息：

- Lap number（发生进站的圈号）
- Stop time（Pit-In 到 Pit-Out）
- In lap time（赛道上 S/F 到 Pit-In）
- Out lap time（Pit-Out 到赛道 S/F）
- Elapsed time at Pit-In（进站时的已用时间）
- **Tip**：带 `[ ]` 标记的进站表示发生在 S/C、VSC 或 FCY 时段内。
- **Stationary Time Option**：ribbon bar 可切换显示计算出的 "Stationary time"（停站时间）代替 pit lane time，使用 track item parameters 中的 "Pit Lane Stop & Go Time"。

## Crossing order scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/crossing-order-scoreboard/

显示每辆车相对总领跑者完成每一圈时冲过终点线的顺序。规则：

- 车辆按其 **class color**（组别颜色）着色；在 ribbon bar 中设置的 reference cars（参考车，例中为 #1）除外。
- 总领跑者（overall leader）始终是每行第一辆。
- 各组别领跑者（class leaders）用边框框标出。

## Lap chart scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/lap-chart-scoreboard/

Lap chart 显示每圈结束时每辆车的 scored position（得分排名）。车辆默认按 class color 着色；指定 reference cars 后这些车覆盖为参考车颜色。可输入多个参考车，用逗号分隔（如 `1,2,3`）。

## Lap analysis scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/lap-analysis-scoreboard/

快速比较本车与驾驶员相对全场表现的计分板；在 ribbon bar 输入 reference car 决定所有 delta（示例中为 #31）。三个分区：

1. 全场各车的 best lap times 与分段，相对参考车的 best（可配合 Filtering 过滤掉其他组别，如过滤掉 LMP2）。
2. 参考车每位驾驶员一行，时间相对该车的 best。
3. 该车的上一圈与当前圈，相对该车的 best。

**Reference car display mode（三种显示模式）**：

- **Overall position**：每列显示该车相对全场的位置。
- **Visible position**：每列显示相对计分板当前可见车辆的位置。
- **Time**：每列显示实际时间。

## Live crossing order scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/live-crossing-order-scoreboard/

实时过线顺序，帮助快速了解本车相对交通与领跑者的位置——车辆按**即将**冲过终点线的顺序排列。

- **两种模式**：① 总领跑者置顶，其余车辆按相对领跑者的过线顺序排列；② 下一辆过线的车置顶，过线后循环到列表底部。
- 标记：总领跑者用**虚线水平线**指示，组别领跑者用**实线水平线**。
- **列说明**：绿色条=该车当前所在分段；图标按 class color 着色，**方形**表示该车在领先圈（lead lap）；Car #；Outlap indicator（仅在 out lap 时显示）；Driver Categorisation（需在 ribbon 勾选 "Show Driver Categorisation"）；当前驾驶员；当前 stint 圈号；到参考车（例中 #97）的 on-track gap；当前在 pit lane 的车辆及已停留时长。
- **Pit stop ghosts**：`F`（Fuel Only）与 `F+T`（Fuel + Tyres）表示“现在进站”的预估落点位置，损失时间按 Backstage Options（Time lost ghost cars）输入的参数计算；幽灵车旁的 gap 表示与前车、后车的差距，箭头指示该 delta 参照哪辆车（例：6 号加油后落在 32 号后 0.6 s、61 号前 0.8 s）。

## Championship point scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/championship-point-scoreboard/

实时追踪赛事期间的 championship（锦标赛积分）形势。

- **Starting Points**：ribbon bar 的 Starting Points 按钮输入起步积分，可手动录入，也可在项目之间导入/导出。
- 积分结构在 **Championship configuration**（Settings & options）中定义。
- **Manufacturers points modes（厂商积分模式）**：按组织规则计算各制造商总积分；用 ribbon 的 "Allowed Class" 过滤只显示目标组别的制造商。
  - **IMSA 模式**：制造商按其在场最好赛车的位置排序计分。
  - **WEC 模式**：用每个制造商最好赛车的**组别位置（class position）**计算积分。

## Multi-session scoreboard

> 原文URL：https://help.hhtiming.com/displays/scoreboards/multi-session-scoreboard/

合并多个节次（sessions）得出最终排名，适用于多节次共同决定排位名次的赛制。用 ribbon 的 **Select Sessions** 按钮选择要纳入的 sessions；可选“取各节 best 的平均值（average of the best of each session）”计算排名，不勾选则按每辆车在任一节中的 best 排名。

# Track maps 子组

## Track maps（共通功能）

> 原文URL：https://help.hhtiming.com/displays/track-maps/

所有赛道地图共享的功能：

- **Track Map Highlighting（高亮）**：高亮用户重点关注的车（如队内车），按其 car color 着色并跟随箭头；高亮后 ghost 才能显示该车进站后相对交通的出站位置，以及 S/C 期间 wave by（套圈放行）信息。跟随设置位于 backstage settings。
- **Car Colouring（车辆着色）**：默认按 class color；可选 by class colour / by car colour / by tyre manufacturer（轮胎供应商）。按轮胎着色在参赛者众多的赛事（如 VLN）中便于区分；默认车辆未分配轮胎供应商（可在 car options 手动分配），此时除高亮车外全部同色。
- **FCY / Safety Car / VSC**：处于这些 caution 状态时 track maps 会**黄色闪烁**。
- **Use Computer Time To Draw Positions**：默认用 timing feed 的 session time 插值画车辆位置；feed 更新慢或有延迟时车辆会跳动。启用本选项后改用计算机本地时钟：每次车辆过线记录计算机时间戳，线间用真实流逝时间沿预期路径动画， movement 平滑连续。该选项在 Full Track Map 和 Circle Track Map 的 ribbon 中提供。
- **Pit Lane List**：每个 track map 底部列出当前在 pit lane 的所有车辆。
- **Wave By List**：底部列出被高亮（通常为队内车）且有资格获得 wave by 的车辆。

## Full track map

> 原文URL：https://help.hhtiming.com/displays/track-maps/full-track/

完整赛道轮廓图，从 Displays tab 添加。选择赛道轮廓的两种方式：

- **Components Tab**：Select Contour 按钮，一次性设置项目中所有 Full Track display 的轮廓（基础用法足够）。
- **Track Item**：适合高级用户，可按每场赛事更新更多高级设置（见 track item parameters）。
- **Tip**：赛道轮廓用户不可编辑；软件未包含所需赛道或需要不同赛道配置时联系官方支持。

**Appearance**

- 默认显示所有车辆；除 Filtering 外，还可用 **Highlight Classes**（Main Track Map ribbon）：勾选后重点组别（focus class，例中 GTLM）正常显示，其他组别（如 GTD 橙色）缩小为小点但仍可见，且各组领跑者仍显示。类名语法必须与 timing feed 中一致（可在项目树 Category Configuration 核对）。
- **Temporary Highlighting**：当某组已被过滤掉时，点击地图右上角 "plus" 输入车号，可临时把该车当作未过滤一样显示（用于应对涉及隐藏车辆的 race control message）。

**Labeling Options**：ribbon 中可配置——Color sectors、Color by Slow Zone Sectors（如 Le Mans）、Show sector labels、Show corner labels、Show marshal sectors、Show marshal sector labels、Show slow zone sectors、Show slow zone sector labels。

**Car Position Methods**

- **Default**：按 timing line 过线绘制；用每车历史分段完成时间估算分段内位置，每次过线校正；并结合 track status，只用当前状态相关的数据提高精度。
- **GPS**：勾选 Use GPS Feed，用 feed 中的 GPS 位置绘制。适合：排位赛中各圈速度差异大时寻找有效空档；Le Mans 等长赛道 timing line 间距大的情况。
- **Use Computer Time**：见共通设置。

**Sector heat map on track map**：可在 ribbon 的 colour mode 中按两车之间的 delta 给分段着色。reference car 留空时自动取与 Delta Car 同组别的最佳车。Heat map mode 决定用于比较的分段数据：

- **Best**：best lap 分段（多参考车时取整圈最佳者）。
- **Theoretical**：各分段最佳合成的理论最佳圈（多参考车时取理论最佳者）。
- **Rolling**：best rolling lap 分段。
- **Last**：最近完成圈的分段（多参考车时取最近完成圈者）。
- 未指定 reference car 时，使用 Delta car 所在组别内该 mode 的最佳值。

**Zoom**

- Corner/Sector label size 两个滑条调节标签大小。
- Ctrl + 鼠标滚轮缩放地图。
- **Focus On Car**（ribbon）+ 滑条可聚焦某辆车缩放。

**Show energy deploy and regen**：仅 Indycar RIS 协议可用；启用后车辆边框显示能量状态——红边=Deploy（输出）、绿边=Regen（回收）。

**Virtual finish car**：ribbon 可启用一辆按平均圈速行驶的理论车（红点）。其位置使得剩余时间为 0 时恰好过 S/F 线：**红点前方的车**还能在结束前过线再跑一圈；**后方的车**无法开新圈（例：剩 20 s 时 1 号在理论车后，无法再做一圈）。

## Gap track map

> 原文URL：https://help.hhtiming.com/displays/track-maps/gap-track/

以**时间 gap** 表示每辆车相对参考车在赛道上的位置；参考车固定在 0 秒（默认在地图中部）。

- 同圈车辆用**方形**车号图标，不同圈用**圆形**图标。
- 绿旗（或局部黄旗）条件下地图每 0.1 s 更新；分段线之间按两车圈速差估算 gap，每次过线用实际 gap 校正。**Safety car 条件下线间不估算，gap 保持恒定**。本节第一圈 gap map 不可用。
- 参考车可更改，但需等每辆车过下一个 sector line 后地图信息才全部正确；地图范围（前后）可改且立即生效。

**Blue Flag Warning**：当更快组别的车正以足够速率追近参考车时触发蓝旗警告，可选视觉和/或听觉提示（ribbon 配置）。激活条件：gap 在用户定义阈值内，**且**接近速率超过用户阈值。默认接近速率 0.03 s/s——120 s 的圈即 3.6 s 圈速差，足以区分 LMP1/LMP2 等。

**Traffic ahead on gap track map**：预测未来赛道位置，便于规划进站避开交通；多组别同场时特别有用（也适用于高衰减赛道上的 Indycar）。由 ribbon 选项控制；目前使用 assumed pace（假设配速）计算。

**Time to catch a car**：显示参考车预计何时追上前车（秒），数值显示在被追车辆号下方；前车无数值表示其平均圈速更快、正在拉开。ribbon 可开关。

**Line where a car will be caught**：若追及时间有值且小于参考车平均圈速的 2 倍，可在赛道上显示预计发生追及/超车的线；用参考车平均圈速和各 on-track loop 平均通过时间计算，需要本节跑过若干圈后才准确。ribbon 可开关。

**Catching zones**：可在 loop 之间自定义额外区域，精确定位超车发生位置。每区需定义：Display name、Previous line on track、Delta time（从前一线到该区起点）。计算命中该区域时控件显示区域名代替线名。

## Circle track map

> 原文URL：https://help.hhtiming.com/displays/track-maps/circle-track/

全赛道地图的线性化表示：每个分段等长显示；**组别领跑者用矩形图标**，其余车辆用小圆点；S/F 线始终在顶部；用户可控制车辆顺时针或逆时针移动方向。

- **Car Position Methods**：Default（与 full track map 相同的 timing line 过线插值）与 Use Computer Time（见共通设置）。
- **Show Gap Overlay**：Circle track map 也支持 gap 叠加层，详见 Track gap display 的 Options 说明。

# Graphing 子组

## Scatter

> 原文URL：https://help.hhtiming.com/displays/graphing/scatter/

散点图，X、Y 轴均可完全自定义，大量参数可用于两轴绘图。

- 可通过 ribbon 的 **Edit Series** 给 plot series 添加过滤器，只看感兴趣范围（例如给 lap time 图加上限以剔除 In/Out laps）。
- **Reference Car**：Scatter Plot 选项中的 Ref Car 字段选择参考车；设置后 Y 轴显示相对该车的 delta。
- **Relative Delta (%)**：启用后 Y 轴 delta 以相对参考车的百分比显示；未选参考车时该选项禁用。
- **Reference Lines**：Edit Reference Lines 按钮添加水平参考线，每条线含名称、Y 值和颜色；多条线的名称显示在图表右侧以区分。

## Raising Average

> 原文URL：https://help.hhtiming.com/displays/graphing/raising-average/

用于分析练习/排位或正赛：绘制“前 X 名最佳圈的平均圈速”随 X（从 1 开始）变化的曲线。例：x=60 处的 y 值是各车最佳 60 圈的平均圈速。

- 反映车/驾驶员的**一致性**：斜率越平缓，在所示圈数范围内越稳定。
- 适合看整节的整体表现；**不能**分析单个 stint 或连续圈段。

## Gap Graph

> 原文URL：https://help.hhtiming.com/displays/graphing/gap-graph/

仅用于分析正赛：显示其他车相对参考车的 gap。Y 轴为 gap（秒），X 轴为比赛圈号或 session 已用时间。多圈累积具有过滤效应，比原始 lap time 更清晰地反映相对 pace。

- **Gap Convention**：默认 Y 正值=落后参考车、负值=领先；ribbon 的 "Reverse Y Axis" 可反转。
- **Reference Modes**：
  - **Reference Car**：每圈末各车相对所选参考车的 gap。
  - **Reference Time**：各车相对一个固定圈速的 gap，相当于相对“整场都跑同一圈速的假想车”；ribbon 按钮可编辑参考时间，并选择按 **lap** 或 **sector** 更新图表。
- **Reference Lines**：与 Scatter 相同的水平参考线功能（名称 + Y 值 + 颜色，名称显示在右侧）。
- **X Axis Modes**：水平轴两种模式（圈号 / 已用时间）。
- **Laps down display**：仅 Reference time 模式可用；"Laps down to show" 控制显示落后 x 圈的理论 gap 线（按预定义参考圈速计算）。
- **Reset under yellow**：仅 Reference time 模式；启用后每个 yellow lap 后领跑者 gap 重置为 0，其他车用相同 offset 修正。
- **Single-class mode**：仅 Reference time 模式；多组别比赛中 laps down 与 reset under yellow 默认按各组领跑者独立运作，启用本模式后所有车按**全场领跑者**处理（laps down 线只显示全场领跑者所在组别的，yellow 重置 offset 也基于全场领跑者组别）。
- **Track status highlight**：非绿旗时段背景变为对应旗色（SC 黄、FCY 紫）；ribbon 的 "Show Track Status" 可关闭。
- **Ghosts**：幽灵线表示该车在当前圈末进站后的落点 gap，分 "Fuel" 与 "Fuel and Tyres" 两类；在 ribbon 手动输入车号，多车用逗号 `,` 分隔。
- **Projected laps**：按各车平均圈速绘制未来各圈 gap 演化线，圈数由 ribbon 数值控制。

## GPS Speed

> 原文URL：https://help.hhtiming.com/displays/graphing/gps-speed/

在 feed 提供 GPS 数据的系列（如 WEC、Formula E）中可视化速度曲线与赛道位置（driving lines）。

- **数据限制**：feed 只给位置，GPS speed 由位置微分得到，误差来源为 GPS 测量误差与数值微分误差；数据无时间戳，点间时间需估计。结果只能视为估计值，可滤波但应知其局限。
- 从 ribbon Displays tab 创建 GPS Speed graph。

**Using the GPS graph**

- **Add live follow**：会话中自动添加/移除圈。选车后选择圈类型：Previous and current laps（当前圈实时显示 + 上一圈；当前圈结束自动移除旧上一圈）；Cars ahead and behind（按总排名显示所选车前后车的当前与上一圈）；Best lap（始终显示所选车最佳圈）；All save laps（显示该车所有 save laps）。
- **Add laps**：打开窗口从任意车、任意节次加载多圈。
- **Remove selections**：从图中移除项目。
- **Export CSV**：导出图中数据，每圈一个 CSV 文件。
- **Other options**：
  - **Plot mode**：在 speed graph 与 position graph（看 racing lines）间切换。
  - **GPS type**：feed 中的 GPS 类型，保持默认 rGPS。
  - **Show best lap**：始终显示本节最佳圈；仅当 GPS graph 从 live session 开始就打开时有效，不适用于已激活（activated）的 session。
  - **Save lap minimum coast required**：判定 save lap 的最小滑行距离（如 100 m——单次滑行超过 100 m 的圈标为 save lap）。
  - **Use speed from feed**：保持 false（feed 无速度）。
  - **Y axis auto scale max**：Y 轴最大值上限（仍可鼠标缩放，但限制绝对上限）。
  - **Max acc threshold**：见下方计算算法。
  - **Filter speed & speed filter window size**：移动平均滤波平滑计算速度；窗口大小=参与平均的点数（窗口 4 即前后各 2 点）。窗口越大滤波越强、图形偏移也越大。

**Elements on the graph**

- **Corner markers**：垂直网格线为弯角，按 Full track map 所选赛道轮廓计算。
- **Driver inputs**：底部图显示由速度导数推算的驾驶输入——正值=加速，>-0.1 m/s²=滑行（coasting），<-0.1 m/s²=制动（braking）。
- **Lap list**（底部表格列）：
  - **L#**：圈号；**LT**：圈速（秒）。
  - **Coast length / coast point / brake point**：在图上单击右键设置 brake zone analysis（例：在 9 号弯附近右键）；表格给出该刹车区的 coast length，以及相对弯心（最低速点）多少米开始滑行/制动。ribbon 的 coast length variation 按钮打开“coast length vs lap number”图（覆盖图中所有圈与车）。
  - **Delta ref / delta**：勾选 delta ref 选参考圈，勾选 delta 选对比圈；在图上**双击右键**设置时间差计算起点（例从 6 号弯起算）；在 x=0 处双击恢复整圈计算。
  - **Show**：取消勾选可隐藏某圈。

**GPS speed calculation algorithm**：先用相邻经纬度距离除以基准时间间隔求速度；时间间隔假设错误时会出现大跳变，**Max acc threshold** 用于剔除跳变过大的点。通常保持默认，可微调改变图形外观。

# 其他独立 Display

## Overviews

> 原文URL：https://help.hhtiming.com/displays/overviews/

**Strategy overview**：总览每辆车的所有 stints 与 pit stops。每行一辆车（按位置排序、车号标识），X 轴为时间；每个块是一个 stint，块间断为进站。便于对比不同车的策略。ribbon bar 提供全部选项。

- **Race Duration** 字段与 Backstage Options → Session Settings 同步：改这里会同时改 Strategy Overview 和 Backstage 设置。
- **Default information**：每 stint 默认显示 Driver name、Sanitized average lap time、stint 圈数。
- **Future stints**：可显示未来 stint——一个从当前时刻向前推算，一个从比赛结束倒推回当前；两者重叠可视化各车进站窗口。可在 ribbon 选择显示一个、两个或不显示。计算方法两种（在 Backstage Options 选择，依赛事规程而定）：**Predicted Stint Lengths** 与 **Fixed Stint Lengths**。
- **Modifying shown information**：ribbon 的 Select Parameters 按钮可增删、重排每 stint 显示的参数。
- **Annotations**：可添加提示/备注，支持区域（area）和单线两种。
- **Auto scaling in X direction**（Appearance 区）：**Complete Session**（时间轴=整个 Race Duration）；**Time Elapsed**（自动缩放到已进行时间）；**Window**（固定窗口，如 1 小时，随比赛滚动显示最近 1 小时）；**Manual Mode**（取消 Auto-Scale Enabled 后手动设横向刻度）。Auto Scale 启用时下方横向滚动条失效。
- **Colour mode**：Driver（Car Options 中驾驶员颜色）/ Driver Categorization（feed 支持时）/ Car（Car Options 车辆颜色）/ Average Lap Time Heat map / Lap Time degradation Heat map（两者目前均按车计算）。

**Lap overview**：概念类似 Strategy overview，但每块是一圈，块内显示该圈圈速。可选着色：Colour blocks by car colour、Colour In and Out laps、Individual best lap colouring、Colour laps with heat map by stint、Colour laps with heat map by all laps、Add border lines to blocks by car colour。

**Track status**：两种 overview 顶部显示赛道状态条——Full Course Yellow 紫色、Safety Car 黄色、Slow zones 绿黄条纹。

**Stint analysis**（Ribbon Overviews 区，仍在开发中）：目标是在练习中结合多 stint 预测 pace/圈速衰减，在正赛中检测衰减。右键每个 stint 可手动编辑用于计算轮胎衰减的圈；右键非首个 stint 可将 stint 合并。

## Filtering displays

> 原文URL：https://help.hhtiming.com/displays/filtering-displays/

Filtering ribbon 控件用于过滤 display 上显示的车辆，可按 category 或单车过滤。三个按钮：

1. **Filter tree**：展开项目中所有 category 的树；每组可展开到单车，用复选框隐藏/显示。树中另有 **Class Leaders** 节点——无论其余树如何配置，始终显示每组领跑者。
2. **Add to Project**：命名后把当前过滤保存为项目中的 **Car Filter Project Item**，供其他 display 快速复用，无需逐个取消选择。
3. **Pull from Project**：选择已有 Car Filter Project Item 应用到当前 display。
- **Tip**：Apply Filter To All Controls 可把当前过滤应用到所有控件。

## Clocks

> 原文URL：https://help.hhtiming.com/displays/clocks/

**Session Clock**：主 ribbon 可访问。剩余时间通常由 live feed 提供，也可手动改 session 长度；可显示 time remaining 或 elapsed time。背景反映赛道状态（Green Flag / Yellow（或 S/C）/ Red Flag）；ribbon 可开启赛道状态变化（如绿→黄）的**声音警告**。

**Car Stopwatch**：主 ribbon 可访问；可为任意多辆车创建任意多个秒表。用于掌握本车（或其他车）在赛道上的位置、决定何时通联无线电。背景色=Car Options 中的车辆颜色。三种模式：

- **On Track During Stint**：左上=在赛道上；右上=被跟随车号；右下=距上次过终点线的时间；左下=当前所在分段。
- **Car Enters Pit Lane**：左上=已进 pit lane 及进入的 session time；右上=车号；右下=已进站时长；左下=当前分段（取决于维修区终点线位置）。
- **Car Exits Pit Lane**：左上=已出站及刚完成的停站时间；右上=车号；左下=当前分段。
- **Count Down to Pit Stall Option**：Pit Stopwatch 的 ribbon 复选框。用于紧急进站时快速判断车辆还有多久到 box。启用后右下角换成“若本圈进站、预计多久静止在 box”的倒计时。配置：勾选 "Count down to pit stall"；输入**分号分隔**的典型分段时间列表，三段赛道示例：`Time(S/F-->Pit Stall); Time(S1line-->Pit Stall); Time(S2line-->Pit Stall)`。

**Advanced Car Stopwatch**：同样可建多个，背景色为车辆颜色。显示所选车**最近越过的线**；线名可用 ribbon 的 Edit sector and loops table 设置别名（alias）。**Keep** 选项可保留车辆上次越过某线的时刻，并相应显示赛道状态与流逝时间。**Hide Sectors** 可隐藏分段线（如 Le Mans 全是速度/加速度 loop 时）。WEC/ELMS 赛事可启用 **Pit Entry Status** 与 **Pit Exit Status** 显示各自状态。

**Time of Day Clock**：feed 提供本地时刻时显示（部分 feed 不含）。多数 feed 发 UTC，ribbon 可加偏移（offset），也可自动获取 feed 的 UTC offset（**自动偏移仅支持 AlKamel 流**）。feed 无时刻或未连接时显示计算机时钟。

**Green Timer**：正赛中显示自上次 caution 以来赛道保持绿色（green）的时长——对 IMSA 等有“距上次黄旗多久”规程的系列特别有用。其他节次（练习/排位）显示扣除红旗后的 session time（当前已用时间减去本节总红旗时间）。

## Car off track

> 原文URL：https://help.hhtiming.com/displays/car-off-track/

检测赛道上的慢车（slow cars）：安全用途（快速告知车手危险）或策略用途。**有 GPS 时效果最好**；无 GPS 时效果很大程度取决于分段长度。

- 正常时全绿显示 "OK"；有车慢于预期时显示慢车车号及该车停住的分段线；线名可用 Edit sector and loops table 设别名。
- **无 GPS 的 feed**：取消勾选 Use GPS——软件检查车辆是否在分段线迟到，比较实际分段用时与该车估算分段时间，差值超过 tolerance 触发报警。
- **有 GPS 的 feed**：勾选 Use GPS——不使用 tolerance，直接检测 5 Hz 信号下速度低于 **40 kph** 的车。
- **Disable on Out Lap**：不使用 GPS 时，out lap 第一分段的慢车不会被标记，但其他分段可能被标记；复选框可将 out lap 车辆从 car off track scoreboard 中列入黑名单（不报警）。
- **Blacklisted Cars**：事故车可能仍显示在赛道上；文本框可将其加入黑名单移出该 scoreboard。
- **Automatic spotter update on full track map**：检测到慢车后自动出现在 Full track map 的 spotter 选项中，快速可视化哪辆车、在何处出问题；车辆从 car off track display 清除（或被拉黑）后 spotter 列表同步更新。可用 track map ribbon 的 "Show Stopped Cars Arrow" 关闭。

## Track Limits Warning

> 原文URL：https://help.hhtiming.com/displays/track-limits-warning/

显示本节所有 track limits（越界）事件。**特定系列才支持**（协议须传递该消息）：Asian Le Mans Series / ELMS / WEC（Alkamel v2 Protocol）、GT World Challenge Europe（Swiss Timing Protocol）、Supercars（Natsoft XML Protocol）。

- 显示字段：car number、session time、time of day（feed 未带 offset 时需在 ribbon 使用 offset）、lap number、location。
- **Danger（注意）**：lap number 不由 feed 传递，是用 session time 反推的——若错过若干圈可能算错；TLW 若被撤销（cancelled），feed 不传撤销信息，HH Timing 中仍会显示并计入 TLW 计数。
- **Ribbon Options**：Reference Car（逗号分隔的参考车列表）；**Flash For**（All / Reference / None——新消息到达时闪烁 15 s：全部车、仅参考车、或不闪）；offset（加到 Scoreboard 的 Time Of Day 上）。
- **Scoreboard**：参考车列表中的车会以其颜色高亮并闪烁对应事件。
- **其他计分板中的 TLW**（因计数由软件计算，列名 **#TLW**）：Main Scoreboard 显示每车总 TLW 数；Driver Scoreboard 显示每驾驶员总数；Car Scoreboard 可添加 TrackLimits 列查看每圈是否因越界无效。

## Race Control Messages

> 原文URL：https://help.hhtiming.com/displays/race-control-messages/

有组织方消息时显示。默认显示 session time（hh:mm:ss）与消息内容。

- **Reference Car**：ribbon 更改参考车，用该车颜色高亮所有相关消息；多个参考车用逗号分隔。
- **Using time of day**：勾选 "Use Time of Day" 可用 feed 传来的时刻代替 session time。feed 时刻可能是本地时间或 UTC（如 2024 勒芒 24h 16:00 CET 开赛，feed 发的是 UTC）。显示本地时间两种方式：手动 offset，或使用 feed 的 offset（若可用），均需在相应控件填写。
- **Display decimals**：默认时间四舍五入到秒；ribbon 可改 display decimals 显示更精确时间。
- **Search**：搜索栏实时（每敲一个字符）过滤消息行；过滤时列表上方出现提示标签显示仅显示子集；清空搜索恢复全部。

## Pit Light Display

> 原文URL：https://help.hhtiming.com/displays/pit-lights/

**仅 WEC 和 ELMS 可用**。

- **Mode Selection**：ribbon 下拉选择两种模式——**Pit Entry** 或 **Pit Exit**。
- **Status Display**：垂直红绿灯布局三个圆指示灯：
  - 顶圈 **Red**——pit entry/pit exit 关闭；不激活时灰色。
  - 中圈 **Green**——pit entry/pit exit 开放；不激活时灰色。
  - 底圈 **Blue**——蓝旗（blue flag）；不激活时灰色。
  - 两侧竖排显示 "PIT ENTRY" 或 "PIT EXIT" 标签（随模式变化）。

## Track gap display

> 原文URL：https://help.hhtiming.com/displays/track-gap-display/

参考车居中显示，左右为最近的前车/后车及与各自的时间 gap。Ribbon Options：

- **Car Number**：设置参考车。
- **Gap Type (Overall)**：与总排名中紧邻的前车/后车比较。
- **Gap Type (Category)**：与同组别（classification）中紧邻的前车/后车比较。
- **Gap Type (Track)**：与赛道上最近的前车/后车比较。
- **Hide Lap Down**：仅适用于 Track gap 类型；启用后隐藏 delta 标签上的套圈前缀（如 `1L`），时间 gap 仍显示。

（Circle track map 的 Show Gap Overlay 详见本页 Options。）

## Connection Status

> 原文URL：https://help.hhtiming.com/displays/connection-status/

显示数据连接与 feed 健康状态：

- **Last data**：距最近一次 car-on-track 消息过去了多少秒；尚无消息时显示 N/A。
- **TOD skew**：feed 的 time-of-day 与计算机 UTC 时钟之差；正值=feed 超前，负值=feed 落后；尚无时刻消息时显示 N/A。
- **Set TOD Datum**（ribbon）：把当前 TOD skew 存为参考偏移并归零。适用于回放或非 UTC feed——绝对差值无意义、只需观察随时间的漂移；设定后显示的 skew 只是按下按钮以来的变化量。

## 常见问答要点

1. **怎么把计分板某一列改成相对某车的 delta？** 右键该列：第一次=delta 值，第二次=delta %，第三次取消；双击右键对全表所有列做同样循环（Delta with Heat Map）。
2. **时间为什么显示成 m:ss.0，能改吗？** 默认 `m:ss.0`；ribbon 的 Time Format 可改为纯秒数，便于计算和跨数据源比对。
3. **Pit stop scoreboard 里 Pit #1 为什么是最后一次进站？** 进站编号从后往前编，Pit #1 对应该车最后一个 stint。
4. **带 `[ ]` 标记的进站是什么意思？** 表示该次进站发生在 Safety Car / VSC / FCY 时段内。
5. **Track map 上车辆一顿一顿地跳怎么办？** 启用 ribbon 的 *Use Computer Time To Draw Positions*，改用本机时钟插值，动画即平滑（Full/Circle track map 提供）。
6. **只想看清自己组别、又不想丢掉交通信息用什么？** Full track map 的 **Highlight Classes**：目标组正常显示，其他组缩小为小点且各组领跑者仍可见；比直接过滤更合适。
7. **某组已被过滤掉，race control 点名了那组的车怎么办？** 点地图右上角 "plus" 输入车号，临时显示该车（Temporary Highlighting）。
8. **怎么判断本圈还能不能多跑一圈？** Full track map 启用 **Virtual finish car**（红点）：红点前方=结束前还能过线开新圈，后方=不能。
9. **蓝旗警告为什么会触发？** Gap track map 需同时满足：gap 进入用户阈值，且接近速率超过阈值（默认 0.03 s/s，120 s 圈约合 3.6 s 圈速差）。
10. **#TLW / TrackLimits 列的数据是 feed 直接给的吗？** 不是——TLW 计数由 HH Timing 计算（feed 不传 lap number 与撤销消息，可能因漏圈偏差、撤销仍计数）；TrackLimits 列仅在 Alkamel / Swiss Timing / Natsoft XML 下可用。
11. **Time of Day 显示不对怎么调？** 多数 feed 发 UTC：在相应 display 的 ribbon 手动加 offset，或用 feed 的自动 offset（**自动方式仅 AlKamel 支持**）；Connection Status 的 TOD skew 可诊断偏差，Set TOD Datum 可把当前偏移归零只看漂移。
12. **Pit Light Display / Show energy deploy 为什么不可用？** 前者仅 WEC、ELMS；后者仅 Indycar RIS 协议——display 的可用性通常受系列与协议限制（同理 Track Limits Warning 仅 Alkamel v2 / Swiss Timing / Natsoft XML 系列）。
