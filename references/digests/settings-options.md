# 设置与选项（Settings & options）

来源：https://help.hhtiming.com/settings-options/（6 个页面）
涵盖 Backstage 设置/选项、自动日志上报、车辆选项、锦标赛配置、赛道项目与幽灵车。

---

## 1. Backstage settings（后台设置总览）

**入口**：Ribbon Bar → **File** 选项卡 → **Options**。

**存储属性**：这些设置属于**本台电脑**，不随项目保存（与项目内 Championship/Track 等项目项不同）。

**子区域**：Backstage 设置按子页组织，详细参数见「Backstage options」及同级子页（Auto report logs 等）。

**导入/导出设置**：
- 可导出与导入整套 backstage settings；
- 默认保存路径：`Documents\HH Timing\Backstage Settings`（`.hhset` 文件）。

**FAQ**
- **Q：为什么换台电脑设置没了？** Backstage 设置是机器级的，需导出 .hhset 再导入到新机器。
- **Q：设置和项目一起保存吗？** 不会，项目内保存的是 Championship、Track 等项目项。

---

## 2. Auto report logs（自动错误日志上报）

两个布尔选项：

| 选项 | 为 True 时 |
|---|---|
| **Ask if logs can be auto reported** | 出错时**询问**用户是否把错误日志自动发给 HH Development |
| **Auto report logs** | **直接自动**把错误日志发送给 HH Development |

**FAQ**
- **Q：不想自动上报？** 两个都设为 False（或至少关闭 Auto report logs）。

---

## 3. Backstage options（后台选项，按分区）

### Auto-update
- **Allow check for new versions**：True 时有网络则自动检查更新。

### Data import
- **Merge sessions during bulk import**：软件中当前为**禁用**状态的选项。

### General
- **Car Makes/Teams Colours**：车队品牌/名称 → 颜色的集合。新车的品牌/团队名（取决于 Default Colouring Mode）包含该键时使用对应颜色；可用 `*` 作为其他所有车的默认色。
- **Default Colouring Mode**：按 **Car Make** 还是 **Team Name** 匹配默认颜色。

### Help
- **Show project wizard**：True 时新建项目会显示 Project Wizard 助手。

### Layout
- **Confirm before closing worksheet**：True 时关闭工作表前询问确认。

### Misc calculation
- **Sort cars at sectors during race**：
  - True：每个分段结束即更新排名；否则每圈结束才更新。
  - 暴露为选项的原因：某车可能未被某分段线识别——若开启分段排序，软件会误以为该车掉名次，直到下一正常分段或终点线才纠正。
  - 设备全部正常时**首选 True**；**IMSA 最常需要设为 False**（该问题偶发于 IMSA）。

### Moving average
- **Default laps before/after**：移动平均图窗口的默认下/上界圈数。

### Reference car
- **Default reference car**：任何支持参考车的显示（Displays）默认选中的车号。

### Reporting
- **Best X quantities for report graphs/tables**：报告中「best X」计算的 X 值列表，逗号分隔整数（如 `5,10`）。
- **Best X% quantities for report graphs/tables**：「best X%」计算的百分比列表（如 `5,10`）。
- **Clean function threshold**：相对该车最快圈的圈速阈值，超过者从报告中剔除。
- **Default report custom logo**：新报告模板默认 logo/图片。
- **Minimum number of laps in race stint**：文档标注**当前未使用**。
- **Report template library**：报告模板保存的默认本地目录。

### Scoreboard settings（计分板设置）
颜色约定（最佳圈/分段/速度的着色）：
- **Colour for best time for car**：本会话每辆车自己的最佳；
- **Colour for best time for driver**：每位车手自己的最佳；
- **Colour for best time in class**：组别内最佳；
- **Colour for best time in stint**：每车当前 stint 内最佳；
- **Colour for best time overall**：全场最佳；
- **Colour for slower projected time**：预测圈速慢于该车最佳时的着色（用于 Projected lap time 的 Proj Time/Proj Gap）。

其他：
- **Default scoreboard autosize columns**：True 时列宽自动调整；
- **Default scoreboard black background**：True 时表格/视图默认黑底；
- **Default scoreboard display seconds**：True 时时间默认以秒显示；
- **Number of non-track sectors in scoreboard**：无会话时模板中非赛道分段默认数量（载入会话数据后被覆盖）；
- **Number of sectors in template**：无会话时默认分段数（同上）；
- **Number of speed traps in template**：无会话时默认测速点数（同上）；
- **Reset last sectors every lap**：True 时车辆过当前圈 S1 后清除上一圈的分段数据。

### Session export options
- **Export session top speed at MPH**：True 时速度数据 CSV 导出用 MPH。

### Session settings（会话设置）
- **Disable race finish calculation**：True 时关闭前向预测计算，处理速度大幅加快；常用于快进回放到某点，正式比赛前须取消。
- **Enforced number of pit stops**：策略预测强制使用的进站次数。
- **Enforced number of pit stops enabled**：True 时前向策略预测强制用上述手工进站次数。
- **Enforced pit stop time**：Pit Stop Time Mode = User Defined Fixed 时强制使用的进站时长（应填常规进站的 PIT IN→PIT OUT 总时长）。
- **Fixed stint length**：由驾驶时间限制最大 stint 的系列（如 GTWC Europe）在此定义前向策略用的最大 stint 时长（配合 Fixed stint length 计算）。
- **Pit stop time mode**（未来进站时长的确定方式）：
  - **User defined fixed**：使用 Enforced pit stop time；
  - **Average of history**：该车此前所有绿旗进站的平均（默认逻辑）；
  - **VLN rules**：仅 NLS 赛事相关；
  - **Calculated**：由 stop & go 时间（Track）、加油速率（Backstage 或 Track）、换胎/换人时间（Backstage）、fuel/tyres 是否并行（Championship config）推算；每次加够所需燃油且**总是**换胎/换人。
    - 公式（例：还剩 20 圈、10 圈后进站）：
      ```
      预计完赛时间 = 9×平均圈速 + 平均圈速×In Lap Ratio
                   + Pit Lane Stop & Go Time + Stopped Time
                   + 平均圈速×Out Lap Ratio + 9×平均圈速
      ```
      （9 = 示例中最终 stint 圈数相关系数，来自文档示例）
      - 非并行：`Stopped Time = 未来 stint 圈数 × refuel rate + 换胎时间`
      - 并行：`Stopped Time = max(未来 stint 圈数 × refuel rate, 换胎时间)`
- **Predicted strategy type**：比赛结束计算使用的策略类型——**Predicted Stint Lengths**（多数系列）或 **Fixed Stint Lengths**（如 GTWC Europe，限 65 分钟）。新建 Strategy Overview 时取此值。
- **Race finish mode**：比赛结束判定——**When leader finishes**（多数系列）或 **When time elapses**（VLN/N24，圈长过长所致）。
- **Race length mode**：**Time** / **Distance** / **Time & Distance**（先到先得）；Time & Distance 时 Estimated race finish type 可作为 Main Scoreboard 可选列。
- **Session length (hours)**：时间限制比赛的时长（小时）。
- **Total number of laps to be completed (if distance limited)**：里程限制比赛的总圈数。
- **Use time of day for timed session / time certain**：True 时比赛结束按「时刻」而非会话时长；Distance 模式下该时刻作为 time certain（先完成里程或先到时刻，先到者为准），finish type 可显示。
- **Race finish time of day**：比赛结束/limit 的本地时刻（24H 制 HH:mm）。
- **Extra lap after time certain**：仅 Distance + 使用时刻时有效；True = 到时刻后领先车完成当前圈再多跑一圈；False = 领先车完成当前圈即结束。

### Strategy overview
四条轮胎颜色（Strategy Overview 显示轮胎时使用）：
- **New tyre colour**：新胎；
- **Unchanged tyre colour**：上一 stint 未更换（沿用）；
- **Used in a previous session colour**：上一场比赛用过；
- **Used tyre colour**：本场已用过。

### Server mode configuration
（详见 digests/timing-data-management.md 服务器模式）
- **Timing and scoring server enabled**：True 时本机向局域网转发计时 feed；
- **Timing and scoring server port number**：客户端在 Championship Configuration 中连接的端口，默认 **24689**。

### Track map highlighting
- **Car highlighting**：输入关注车号（逗号分隔可多辆），并勾选启用。高亮效果：车显示为自身颜色而非组别色；有箭头指向；focus 车优先渲染在密集处之上。Ribbon 中还可调 **Car scaling**（车尺寸）与 **Arrow size**（箭头尺寸）。
- **Time lost ghost cars**：详见 Track item / Track Map / Ghosts。

**FAQ**
- **Q：IMSA 排名乱跳？** 尝试把 Sort cars at sectors during race 设为 False。
- **Q：回放快进太慢？** 勾选 Disable race finish calculation。
- **Q：GTWC Europe 该用哪种策略类型？** Fixed Stint Lengths。
- **Q：设置怎么迁移到别的电脑？** Backstage Settings 导出 .hhset 再导入。

---

## 4. Car options（车辆选项）

**入口**：Ribbon Bar → **Components** 选项卡 → **Car Options**。

**每辆车可调参数**：
- Report name（报告名）
- Category（组别）
- Colour（颜色）
- Team name（车队名）
- Car manufacturer（制造商）
- Tyre manufacturer（轮胎商）
- Line style / Line colour / Line width（仅图表用；线色与车色联动）
- Marker style / Marker colour / Marker size（仅图表用）

**每位车手可调参数**（窗口右下区域）：
- Report name
- Driver Categorisation（如 Platinum / Gold / Silver / Bronze）
- Colour
- Line style / Line colour / Line width（图表用）
- Marker style / Marker colour / Marker size（图表用）
- **Maximum Driving Time (Minutes)**：最大驾驶时间（分钟）
- **Minimum Driving Time (Minutes)**：最小驾驶时间（分钟）

**批量应用按钮**：网格中可将某车手的 `Max Dr [min]` / `Min Dr [min]` 应用到**同一 Driver Categorisation** 的所有车手；无 categorisation 的车手则应用到所有同样无 categorisation 的车手。

**FAQ**
- **Q：最大/最小驾驶时间填在哪、什么单位？** Car Options 按车手，单位分钟；用于驾驶时间计算与 TT Max DT / TT Min DT 等列。
- **Q：怎么给同级车手批量填驾驶时间？** 用网格中的批量应用按钮。

---

## 5. Championship configuration（锦标赛配置）

**入口**：Components 选项卡 → **Add New Championship** 创建；项目树中已有各支持系列的默认配置。右键 → **Activate** 激活（激活后在树中**加粗**）。

配置负责三类参数：

### 网络连接信息
- 选择通信协议（Protocol）、输入计时服务器 host/port 及系列相关配置项；
- 新建：Components → Add New Championship → 下拉选协议 → 填数据源信息；不确定协议可咨询支持；host/port 通常向计时方索取；
- 一般每赛季配置一次即可（协议与连接信息分站间通常不变，例外见系列专属文档）。

### 锦标赛过滤（Championship filter）
只放行目标系列数据，阻止其他系列的车辆/车手进入项目。
- **Allow string**：事件名中**必须出现**的词；
- **Block string**：事件名中**不得出现**的词；
- 通常只需填其一；
- **字段区分大小写（case sensitive）**；
- 启用且拦截时屏幕底部显示提示消息；
- 取消勾选复选框可禁用过滤。
- 示例（ELMS）：连接后在 Session Data 页看到会话名含 ` European Le Mans Series`，则 Allow String 可填 ` European Le Mans Series`。

### 导入配置
Components 选项卡 → **Import** 按钮可导入锦标赛配置。

### 系列专属信息
使用 **Championship points scoreboard** 时，须在 Championship Configuration 中定义每个完赛名次的积分。

**FAQ**
- **Q：过滤器没生效？** 检查大小写是否与会话名一致；确认复选框已勾选。
- **Q：同一网络有其他赛事数据混入？** 用 Allow/Block string 过滤。
- **Q：积分记分板没分数？** 先在配置里填各名次积分。

---

## 6. Track item / Track Map / Ghosts（赛道项目 / 赛道图 / 幽灵车）

**入口**：项目树双击 Track Item。新建项目会自动生成 Default Track；Components → **Add New Track** 可添加多个（避免覆盖历史赛事设置）。Components → **Import Track** 可跨项目导入，默认路径：
```
C:\Users\%USERNAME%\HH Timing\Projects\PROJECT NAME
```

### Track Contours（赛道轮廓）
选择所需轮廓；轮廓由 HH Development 制作，缺失请联系 support@hh-dev.com。

### Fuel Only Cutoff（纯加油判定阈值）
当锦标赛不允许加油与换胎同时进行时，软件按维修区停留时间自动判定进站是 “fuel only” 还是含换胎。启用阈值后，判定结果输出在 car scoreboard 进站区（Pit Stops）最后一列。

### Strategy Parameters（策略参数）
对未来 stint 相关参数可按 **class** 或**单车**设值，行为一致：
- 该 category 下所有车强制使用该值；
- 若单车另有定义，**单车值优先**；
- 都未填 → 软件按当前会话历史数据近似。
这些值影响 Race Finish Calculations。包含：

- **Number of Laps in Stint**：未来 stint 计算的最大 stint 圈数；假设每 stint 都跑满；Strategy Overview 据此显示各车加油窗口。
- **Time to Refuel Each Lap of Fuel Burned**：加油速率（秒/圈）。下次加油时间 = 当前 stint 已跑圈数（含当前圈）× 速率；Main Scoreboard 可加 **Estimated Refuel Time** 列查看。
- **Lap Time for a Stint**：未来 stint 使用的平均圈速；不填则用 Assumed Pace（best 3 of last 5 laps）按车计算。
- **Safety Car Fuel Factor**：供 predicted stint length 使用——无全绿 stint 时按黄旗圈数应用该修正因子估算等效绿旗长度；值应 < 1；**全局变量**，所有车同一比例。
- **Maximum Driving Time Rules**：供 drive-time plugin 确定各车手最大驾驶时间参数。

### Track Parameters / Ghosts
- **Stop and Go Pit Loss**：stop & go 相对场上车的时间损失；用于 Advanced（refuel time compensated）幽灵车计算中的 stop & go 部分。
- **Pit Lane Stop & Go Time**：从 PIT IN 到 PIT OUT 完成一次 stop & go 的时间；用于 Main Scoreboard 的 “Last Pit Stationary Time” 列与 Pit Stop Scoreboard 的 “Correct for pit lane time”。
- **Pit not at start finish**：TRUE 表示维修区相对 S/F 线有偏移，用于该类赛道的计时处理。
- **Allow first lap as best**：按计时方对首个 out lap 的处理方式，选择软件把第一圈视为 out lap 还是 flying lap；影响 scoreboard 排名。
- **IN and OUT Lap ratio**：
  ```
  In Lap Ratio  = 平均 IN 圈时间 / 平均绿旗圈时间
                  （IN 圈 = S/F(track) → PIT IN）
  Out Lap Ratio = 平均 OUT 圈时间 / 平均绿旗圈时间
                  （OUT 圈 = PIT OUT → S/F(track)）
  ```
  用于改进比赛结束计算。
- **Use Default Map Average For Extrapolation**：固定赛道图外推用默认时间；常规比赛应为 **False**（用优化算法定位车辆）；单分段赛道图无法优化时才有用。

### 赛道图幽灵车（进站预测位置）
Backstage 的 track map highlighting 可绘制 “Fuel” 与 “Fuel & Tyre” 幽灵车——表示「若本圈进站」后的预计赛道位置。两种算法：

**Basic（固定偏移）**：固定时间偏移，代表该进站类型相对正常绿旗圈的总损失。
例：Fuel & Tyres 损失 111.8s、Fuel only 损失 44.8s → 在 Backstage Options 填这两个值。

**Advanced（加油时间补偿）**：按下次进站需加的油量动态更新；同时计入 stop & go 与换胎损失。
例：Stop & Go 41.8s、换胎 18.5s、每圈油量加油 1.1s → 填 Backstage 值与 Stop & Go Pit Loss。

**计算公式**（由 Championship config 决定是否可并行）：
- **燃油与轮胎不能并行**：
  ```
  Fuel Ghost Offset = Stop & Go Pit Loss
                    + 上次进站以来圈数 × 每圈加油秒数
  Fuel & Tyres Ghost Offset = Stop & Go Pit Loss
                    + 上次进站以来圈数 × 每圈加油秒数
                    + 换胎/换人时间
  ```
- **可并行**：
  ```
  Fuel & Tyres Ghost Offset = Stop & Go Pit Loss
    + max(圈数 × 每圈加油秒数, 换胎/换人时间)
  ```
  即加油比换胎慢时由加油决定停站时长。

「每圈加油秒数」取值优先级：单车精确值 > category 值 > Backstage Options 值。
注意：Advanced 模式**忽略** Backstage 的 “Time lost for fuel and tyres pit stop” 与 “Time lost for fuel only pit stop”。

### Custom Ghosts（自定义幽灵车）
- 显示不受 “Enable time lost cars on track map” 控制，数量无上限；
- 每个 ghost 属性：Name、Offset（固定偏移）、Multiplier（可变偏移 = stint 内圈数 × Multiplier）、Fuel（加油时间，取值优先级同上）、Include stop & go pit loss、Enabled（显隐）；
  ```
  Custom offset = Offset
                + N Laps in stint × Multiplier
                + N Laps in stint × Time to refuel each lap
                + Stop & Go Pit Loss
  ```

### Technical Pit Stop（强制技术停站）
配置 24h Spa 等赛事的 Mandatory Technical Pit Stop；影响 Main Scoreboard 的 Technical Pit Stop 列。

**FAQ**
- **Q：策略参数单车和组别冲突？** 单车值优先；都没填则按会话历史估算。
- **Q：安全车燃油因子填多少？** 应小于 1（黄旗下更省油），全局生效。
- **Q：幽灵车位置不准？** 检查用的是 Basic 还是 Advanced、是否填对 Stop & Go Pit Loss 与每圈加油时间；Advanced 会忽略 Backstage 的固定损失值。
- **Q：新加的赛道轮廓没有？** 联系 support@hh-dev.com。

---

## 站点导航（本章源页面）

| 页面 | URL |
|---|---|
| Backstage settings | /settings-options/backstage-settings/ |
| Auto report logs | /settings-options/backstage-settings/auto-report-log/ |
| Backstage options | /settings-options/backstage-options/ |
| Car options | /settings-options/car-options/ |
| Championship configuration | /settings-options/championship-configuration/ |
| Track item / Track Map / Ghosts | /settings-options/track-item-ghosts/ |
