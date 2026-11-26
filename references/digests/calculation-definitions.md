# 计算定义（Calculation definitions）

来源：https://help.hhtiming.com/calculation-definitions/（11 个页面）
涵盖 HH Timing 中各项前向预测与统计计算的公式、模式、示例与显示位置，可直接回答「X 怎么算」。

---

## 1. Assumed Pace（假设配速）

**用途**：HH Timing 多项前向计算的核心假设值——要对当前/未来 stint 做预测，必须先假设一个圈速。

**公式**：
```
Assumed Pace = 最近 5 圈（绿旗有效圈）中最快 3 圈的平均值
```

**过滤规则**：选取「最近 5 圈」时忽略 in/out lap（进站圈/出站圈）以及所有「黄旗圈」（Safety Car、Full Course Yellow 等）。

**显示位置**：作为固定 stint 长度、预测 stint 长度、比赛结束计算等的输入；可在 Track Item 的「Lap Time for a Stint」中按赛道/车队/车辆手工覆盖，未填写时才使用本公式。

**FAQ**
- **Q：Assumed Pace 会把黄旗圈算进去吗？** 不会，选取窗口时已排除黄旗圈与 in/out 圈。
- **Q：能强制指定配速吗？** 可以，在 Track Item（Track item / Track Map / Ghosts）中按 category 或单车填写。

---

## 2. Sanitized average lap time（净化平均圈速）

**用途**：对一个 stint 内的圈速做清洗后的平均值，剔除受安全车/进出站/离群值影响的圈。

**计算步骤**：
1. 取该 stint 的全部圈；
2. 剔除所有 safety car / full course yellow / code 60 圈；
3. 剔除所有 in lap 和 out lap；
4. 对剩余圈求平均；
5. 剔除所有比该平均值慢 20% 以上的圈（20% 为 HH Timing 中当前固定值）；
6. 用剩余圈重新计算平均值，即为 sanitized average lap time。

**FAQ**
- **Q：20% 阈值能改吗？** 文档注明该值目前是软件内固定值，不可配置。
- **Q：为什么要两轮剔除？** 第一轮剔除系统性污染（黄旗/进出站），第二轮剔除离群慢圈，避免个别异常圈拉高平均。

---

## 3. Yellow flag laps（黄旗圈判定）

**用途**：判定某车某圈是否为「黄旗圈」，结果显示在 car scoreboard 上。

**判定条件**（满足任一即为黄旗圈）：
- Safety Car（安全车）
- Full Course Yellow（全场黄旗）
- Slow Zone（慢速区）
- Code 60

**判定时点**：该车**冲过终点线时**（即该圈结束时刻）上述任一状态成立，该圈即记为黄旗圈。

**显示位置**：Car Scoreboard 的黄旗状态列。

**FAQ**
- **Q：圈中段出黄、过线前恢复，算黄旗圈吗？** 不算——只看过线那一刻的状态。
- **Q：黄旗圈影响哪些计算？** 影响 Assumed Pace 窗口选取、净化平均圈速、degradation 过滤、比赛结束计算的黄旗修正等。

---

## 4. Degradation（性能衰退）

**用途**：对每辆车、每个 stint（outing）单独计算圈速衰退率。

**公式**：
```
Degradation = 对该 stint 内所有有效绿旗圈做
              laptime 对 LapNumber 的线性拟合（best fit）的斜率
```
即圈速随圈数变化的斜率（秒/圈），正值表示随圈数增加圈速变慢。

**过滤规则**（不参与拟合的圈）：
- InLap（进站圈）
- OutLap（出站圈）
- SC（安全车圈）
- FCY（全场黄旗圈）
- VSC 圈
- 圈速大于该 stint 平均圈速 120% 的圈

**两种输出**：
- **LapTime Degradation**：如上，自动过滤。
- **Tyre Degradation**：计算与过滤逻辑完全相同，但用户可在 Stint Analysis 中手工勾选/取消某些圈。

**显示位置**：散点图（scatter plot）、Strategy Overview、Stint Analysis。

**FAQ**
- **Q：Degradation 是全场统一还是每车每 stint 一个值？** 每车、每 stint 独立计算。
- **Q：Tyre Degradation 和 LapTime Degradation 有何区别？** 公式一致；前者允许手工调整参与拟合的圈。

---

## 5. Pit stop length（进站时长）

**用途**：为比赛结束计算与未来 stint（fixed / predicted 两种模式）预测提供进站耗时。

**默认公式**：
```
未来进站时长 = 该车此前所有绿旗进站（green flag stops）的平均耗时（按车统计）
```

**覆盖方式**：可在 Session Settings 中手工输入并强制（Enforced pit stop time），配合 Pit stop time mode 使用（详见 digests/settings-options.md）。

**FAQ**
- **Q：什么时候需要手工强制进站时间？** 某些进站（如慢进站、故障）会严重拉偏平均值时。
- **Q：黄旗下的进站算吗？** 默认只统计 green flag stops。

---

## 6. Fixed stint length（固定 stint 长度）

**适用场景**：stint 长度主要由**驾驶时间**规则限制的系列（如 GT World Challenge Europe 限 65 分钟），比按燃油预测的 predicted 模式更合适。

**计算逻辑**：
- 设置位置：Session Settings（Backstage → Session Settings）中的 Fixed stint length（最大 stint 时间，单位分钟）。
- 预测未来 stint 时，假设每车每个 stint 都跑满该最大时长；
- 各未来 stint 能跑多少圈 = 按该车**平均配速**折算（默认用「最近 5 绿旗圈中最快 3 圈」的 Assumed Pace，可按 class/车在 Track Item 覆盖）。
- 示例：Blancpain GT Endurance，最大 stint 65 分钟——图中 8 号与 84 号车预测可跑 30 圈，其余车 29 圈（因各车平均配速不同）。

**显示位置**：
- 主要用于 **Strategy Overview** 预测未来 stint（新建时需把 Backstage 的 Predicted Strategy Type 从默认 Predicted Stint Lengths 改为 **Fixed Stint Lengths**）；
- Main Scoreboard 相关列：Fixed stint time remaining、Fixed stint num stops left、Fixed stint num laps left curr stint、Fixed stint num laps final stint、Fixed stint add info。

**FAQ**
- **Q：新建策略总览后预测结果不对？** 先检查 Backstage Options → Predicted strategy type 是否改成了 Fixed Stint Lengths。
- **Q：默认用什么配速折算圈数？** Assumed Pace（best 3 of last 5 green laps），可在 Track Item 覆盖。

---

## 7. Predicted stint length（预测 stint 长度）

**适用场景**：stint 长度主要由**燃油**决定的系列。

**计算逻辑**：
- 每车的未来 stint 长度 = **截至当前该车最长的绿旗 stint**（longest green stint to date）。
- 例：全绿比赛进行中，每车未来 stint 对应该车历史最长 stint。

**无完整绿旗 stint 时的修正**：若某车没有全绿 stint，或某 stint 被黄旗打断但绿旗圈数多于该车其他 stint，则软件估算最大绿旗 stint 长度：
```
估算时对该 stint 中处于黄旗状态的圈数应用「燃油修正因子」
（correction factor = 黄旗工况预计油耗 / 绿旗圈油耗，值 < 1）
```
该因子为**全局变量**（Track Item → Safety Car Fuel Factor），假设所有车在黄旗下省油比例相同。

**覆盖方式**：可在 Track Item 中按 class / 单车手工指定最大 stint 长度。

**显示位置**：
- Strategy Overview；
- Main Scoreboard 列：Estimated # laps remaining in current stint、Estimated # stops remaining、Estimated # laps in final stint、Estimated finish time、Estimated # laps total、Estimated # laps remaining。
- 新建 Strategy Overview 时使用 Backstage 中的 Predicted Strategy Type（默认即为 Predicted Stint Lengths）。

**FAQ**
- **Q：预测 stint 用的是平均圈速还是最长 stint？** 绿旗 stint 圈数来自「最长绿旗 stint」，圈数折算用各车配速。
- **Q：黄旗打断的 stint 会怎样？** 用 Safety Car Fuel Factor 修正后估算等效绿旗长度。

---

## 8. Race finish calculation（比赛结束计算）

**比赛结束方式（4 种，Session Settings 中选择）**：
- Timed（计时）
- Timed + 1 lap（计时 + 1 圈）
- Distance（里程/圈数）
- Time & Distance（时间与里程先到先得）

**准确性前提**：领先车及关注车至少完成过一个**完整绿旗 stint**——该 stint 每圈均为绿旗（或绿旗 + 局部黄旗），且 stint 首尾进站在绿旗下完成。
若不满足：改用**带黄旗的最长 stint**，并用黄旗燃油缩放因子（Track Item 中设置，应 < 1）修正黄旗期间油耗。

**输入参数（8 个基础列，先算出）**：
| 参数 | 计算方式 |
|---|---|
| Average Lap Time | 最近 5 个绿旗飞驰圈中最快 3 圈的移动平均（同 Assumed Pace） |
| Number of Green Laps in Longest Stint | 最长 stint 中的绿旗圈数 |
| Number of Yellow Laps in Longest Stint | 最长 stint 中的黄旗圈数（理想为 0） |
| Average Pit Stop Time | 所有绿旗进站的平均耗时 |

**再结合比赛长度，计算以下输出列**：
- **Estimated # Laps Remaining in Current Stint**：基于最长绿旗 stint 长度估算当前 stint 剩余圈数；若当前 stint 已超过历史最长绿旗 stint，该值为负（例如因安全车多跑了）。
- **Estimated # Stops Remaining**：按剩余比赛时间 ÷（平均圈速 + 平均进站 + 最大 stint）估算剩余进站次数；假设余下比赛全程绿旗，不对安全车/黄旗做概率假设。
- **Estimated # Laps in Final Stint**：最后一次进站到比赛结束之间能完成的圈数。
- **Estimated Finish Time**：预计完赛时刻（基于计算时刻的领先车）。
- **Estimated Finish Type**（仅 Time & Distance 模式）：该车能否在时间限制内完成规定里程。

**边界规则**：若剩余时间不足以完成「1 次进站 + 最终 stint 至少 1 圈」，则不计该次进站，倒数第二个 stint 成为最终 stint 并追加圈数——此时 stint 长度可能略超最大 stint 限制。

**显示位置**：Main Scoreboard（8 个附加列）与 Strategy Overview。目前结果仅在 scoreboard 上提供。

**FAQ**
- **Q：为什么完赛预测突然变负/跳变？** 可能当前 stint 已长于历史最长绿旗 stint，或黄旗修正被启用。
- **Q：预测假设有安全车吗？** 没有——Estimated # Stops Remaining 假设余下全绿。
- **Q：黄旗下计算准吗？** 需至少一个完整绿旗 stint；否则用带黄旗 stint + 缩放因子，误差更大（黄旗圈数理想应为 0）。

---

## 9. Driving time（驾驶时间）

**两种扣除进站时间的模式（Backstage Options 配置）**：
1. **始终扣除 PIT IN→PIT OUT**，无论进站与出站是否同一车手——多数主流系列采用（默认）。
2. **仅当进站车手 ≠ 出站车手时才扣除** PIT IN→PIT OUT——Bathurst 12 Hours 采用。

**比赛结束时的计算终点（二选一）**：
- 比赛时间耗尽时（When the race time is elapsed）；
- 车辆完成比赛时（When the car finish the race）。
默认 False：计算到车辆最后一次冲过 S/F 线为止。

**红旗**：红旗暂停时间**不计入**车手驾驶时间。

**最大/最小驾驶时间**：在 Car Options 中按车手填写，单位为**分钟**。

**显示位置**：
- **Driver Scoreboard** 列：
  - Driving Time：开赛以来总驾驶时间；
  - DT Last 6 Hrs：最近 6 小时驾驶时间（>3 小时变橙，>4 小时变红）；
  - TT Max DT：距最大驾驶时间倒计时（<1 小时变橙，归零变红）；
  - TT Min DT：距最小驾驶时间倒计时（同上）；
  - 4in6 Get OUT：为不违反「6 小时内最多 4 小时」必须下车的会话时刻（假设在车上的车手可立即接上）；
  - 4in6 Nxt 4H at：之后最早可再连续驾驶 4 小时的时刻（同时考虑最大驾驶时间；若无法再排出 4 小时块则为空）；
  - 4in6 ET to Fin：既能守「6h/4h」规则又能完赛的最早上车时刻。
- **Main Scoreboard**：可显示当前在车车手的同类列。

**已知不准场景（注意）**：
- 丢失计时信息：软件会自动补偿 stint 中的连接问题，但若 PIT IN/PIT OUT 消息未被处理，驾驶时间会错；
- 车辆未经过 PIT IN/PIT OUT 环线（如经辅助道路驶回维修区），在车车手驾驶时间会错。

**FAQ**
- **Q：驾驶时间怎么算？** 由圈速 + PIT IN/PIT OUT 时间推算，按上述模式扣除站内时间，不含红旗时间。
- **Q：最大/最小驾驶时间填在哪？** Car Options，按车手，单位分钟。
- **Q：4in6 列为什么有空值？** 该车手在剩余比赛中无法再凑出连续 4 小时驾驶块。

---

## 10. Projected lap time（预测圈速）

**三种模式（Backstage → General 下选择）**：

### 模式 A：Best sectors（最佳分段拼接）
```
Projected = 本圈已完成分段之和 + 该车剩余各分段的历史最佳值
```
示例（第 7 圈）：已完成 S1=51.758；剩余最佳 S2=33.660、S3=41.045
→ Projected = 51.758 + 33.660 + 41.045 = **126.463 秒**

### 模式 B：%diff to best（对最佳的百分比偏差）
```
delta% = (已完成分段之和 − 对应最佳分段之和) / 最佳分段之和
Projected = 已完成分段之和 + (剩余最佳分段之和) × (1 + delta%)
```
示例：已完成 51.758，最佳 51.663 → delta = (51.758−51.663)/51.663 = 0.184%
→ Projected = 51.758 + 33.660×(100+0.184)% + 41.045×(100+0.184)% = **126.600 秒**

### 模式 C：Best lap（最佳整圈的剩余部分）
```
Projected = 本圈已完成分段之和 + 该车最快圈（图例中为第 6 圈）的剩余分段
```
示例：51.758 + 33.660 + 41.045 = **126.463 秒**

**显示位置（Main Scoreboard 三列）**：
- **Proj Time**：预测圈速数值；
- **Proj Gap**：预测圈速与该车最佳圈速之差；
- **Proj S/F**：用上一圈实际用时 + 预测圈速推算的下一次过 S/F 时刻。

**颜色**：Proj Time / Proj Gap 单元格背景由 Scoreboard → Background 选项控制；更快按既定约定色（best car/overall/driver 等），更慢用「Colour for slower projected time」；颜色删空即为透明。

**FAQ**
- **Q：三种模式差别？** Best sectors 用各分段最佳拼接；%diff 把已完成部分的百分比偏差外推到剩余分段；Best lap 用最快圈的剩余分段。
- **Q：Proj Gap 是和谁比？** 与该车自己的最佳圈速比较。

---

## 11. IMSA Safety car wave-by（IMSA 安全车放行）

**限制**：仅适用于 **IMSA WeatherTech Championship**。

**触发条件**：安全车出动（赛道状态为黄且检测到安全车）时，每辆车每次**冲过分段线**，记录其相对安全车的通过顺序（SC Cross Order）。

**两个参数**：
- **SC Wave By**：当前是否允许该车被放行（该车是否处于安全车与组别领先车之间）；
- **SC Pit For Wave By**：若该车被套圈，需要哪些领跑车（lead lap 上、位于该车与安全车之间的车）进站后才能对其实施 wave by。

**显示位置**：
- Main Scoreboard 三列：SC Cross Order、SC Wave By、SC Pit For Wave By；
- 赛道图（circle 与 full）上对所选车辆显示。

**FAQ**
- **Q：其他系列能用吗？** 不能，仅 IMSA WeatherTech。
- **Q：SC Cross Order 怎么来的？** 安全车在场时，每车过一次分段线就记录一次与安全车的相对顺序。

---

## 站点导航（本章源页面）

| 页面 | URL |
|---|---|
| Driving time | /calculation-definitions/driving-time/ |
| Predicted stint length | /calculation-definitions/predicted-stint-length/ |
| Fixed stint length | /calculation-definitions/fixed-stint-length/ |
| Assumed pace | /calculation-definitions/assumed-pace/ |
| Degradation | /calculation-definitions/degradation/ |
| Pit stop length | /calculation-definitions/pit-stop-length/ |
| Race finish calculation | /calculation-definitions/race-finish-calculation/ |
| Sanitized average lap time | /calculation-definitions/sanitized-average-lap-time/ |
| Yellow flag laps | /calculation-definitions/yellow-flag-laps/ |
| IMSA Safety car wave-by | /calculation-definitions/IMSA-safety-car-wave-by/ |
| Projected lap time | /calculation-definitions/projected-lap-time/ |
