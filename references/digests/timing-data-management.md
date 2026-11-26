# 计时数据管理（Timing data management）

来源：https://help.hhtiming.com/timing-data-management/（8 个页面）
涵盖会话数据、实时连接、导入导出、回放、服务器模式与数据恢复。

---

## 1. Session data（会话数据）

**数据来源（项目 Data 树中的四类）**：
1. **Recorded**：连接实时计时数据时自动录制进项目（Live timing feed connection）；
2. **Imported**：从赛后数据导入（通常 CSV 等格式，Timing and scoring data import）；
3. **Replayed**：回放（模拟连接直播，Replays）；
4. **Activated**：激活（静态查看最终结果，不逐条回放）。

**管理**：数据都在项目树 Data 分支下；数据多时可在 Sessions 上右键创建文件夹整理。

**回放**：Data 树中任意已有数据右键 → Replay。

**激活**：右键会话 → Activate；适用于回放数据或导入的 T&S 数据，静态呈现该会话最终状态。

**FAQ**
- **Q：Replay 和 Activate 有什么区别？** Replay 按时间逐条重放（可控制速度/跳转）；Activate 直接加载为静态最终结果。
- **Q：直播数据会自动保存吗？** 会，连接即录制到项目数据库，可随时回放。

---

## 2. Live timing feed connection（实时计时源连接）

**入口**：Ribbon Bar → Data 选项卡 → Connect。

**三种连接类型**（协议与相关选项在 Championship Configuration 项目项中定义）：

### Socket 连接
最常见方式。用户提供计时/记分服务器的 **host（主机名）+ port（端口）**，信息由赛事计时方提供。

### HTML Scraping（网页抓取）
- 用于没有官方数据源的赛事；按固定间隔读取计时网页，根据页面变化推断数据。
- 连接时会在 Championship 中定义的 URL 打开浏览器窗口；可操作菜单切到正确视图，**读数期间不要关闭浏览器**。
- 属非受支持的非官方手段，部分数据靠估算，存在弱点与误差。
- **建议**：赛后分析改用主办方提供的赛后数据导入。

### FTP 服务器
- 计时服务以 FTP 形式发布时使用；目前仅用于官方 Blancpain 计时服务。
- 技术上效率较差，但优点：数据以文件形式保存，**无论何时连接都能取到此前已发布的全部数据**——晚连接或电脑崩溃后仍可补齐错过的数据。

**FAQ**
- **Q：连接信息在哪配？** Championship Configuration（协议、host、port 及系列相关选项）。
- **Q：没有官方 feed 的系列赛后怎么分析？** 用赛后 T&S 数据导入替代 HTML scraping。

---

## 3. Timing and scoring data import（T&S 数据导入）

**性质**：主办方/计时方提供的**静态**计时数据（通常即官方成绩）。导入后**不能回放**——尽快读完并直接显示会话最终结果；所有直播/回放可用的显示对静态数据同样有效。

**单文件导入**：Data 选项卡 → **Import T&S Data** → 选择赛事对应数据格式 → 选择会话类型（Timed 或 Race）→ OK。
（配套视频：YouTube Lndv2Ls1QDo）

**格式**：随系列而异，通常为 CSV、XML、PDF。

**注意**：部分系列（如 WEC、ELMS）提供的 T&S 数据**不含显式 PIT IN/PIT OUT**，驾驶时间不可信；这些系列要准确计算驾驶时间请改用 replay 文件（含所需全部数据）。

**批量导入**：**Bulk Import T&S Data** 可一次导入多个文件，并可选择合并（merge）为单个会话；目前仅支持 **Alkamel** 与 **IMSA Timing** 的 CSV。

**FAQ**
- **Q：导入的数据能 Replay 吗？** 不能，只能 Activate 静态查看。
- **Q：WEC/ELMS 导入后驾驶时间不对？** 因源数据缺 PIT IN/OUT，改用回放文件。
- **Q：批量合并支持哪些格式？** 目前仅 Alkamel 与 IMSA Timing CSV。

---

## 4. Replays（回放）

**四类回放文件**：
1. HH Timing 用**当前项目**录制的回放；
2. HH Timing 用**其他项目**录制的回放；
3. 赛事官方**发布的**回放；
4. 由赛事**发布数据重建**的回放。

### 用当前项目回放
连接直播时数据已自动存入项目数据库；右键会话 → Replay。

### 跨项目回放
- 源项目：右键会话 → Export 导出回放；
- 目标项目：Data 选项卡 → **Load Replay** 载入。
- **关键**：目标项目的 **Protocol 必须与录制时使用的协议一致**。

### 赛事发布的回放
目前仅 **IMSA** 提供，为 .txt 文件，可从 IMSA timing and scoring 网站下载；Data → Load Replay 选择该 .txt。

### 由赛事数据重建
Blancpain 比赛：HH Development 可根据 Swiss Timing 发布数据重建回放文件，所需数据可从现场 FTP 下载。

### 历史回放库
HH Development 保存了多数主要耐力赛系列的历史回放；需要特定回放可邮件联系支持。

### 回放控制
- 右下角控件：调节速度、暂停/播放；
- 蓝色按钮：直接跳到回放末尾（只要最终结果时用）；耗时取决于数据格式、车辆数、比赛长度与电脑性能，一般 1 分钟内完成；
- 时钟图标：弹出输入框，可前后跳到任意会话时刻定位回放。

**加速技巧**：Session Settings 中的 **“Disable race finish calculations”** 可关闭前向预测计算，大幅降低计算负载、加快快进速度；正式比赛前记得取消勾选，否则不会显示前向策略计算。

**FAQ**
- **Q：回放别的项目的数据报错？** 检查当前项目 Protocol 是否与录制时一致。
- **Q：快进太慢怎么办？** 勾选 Disable race finish calculations，到位后取消。
- **Q：哪里下载 IMSA 回放？** IMSA timing and scoring 网站的 .txt 文件，用 Load Replay 打开。

---

## 5. Export session（导出会话）

右键项目树中的会话 → 选择导出选项：

| 选项 | 输出 |
|---|---|
| **Export Replay** | 可在其他电脑/项目回放的回放文件（目标需选相同协议） |
| **Export (IMSA Format)** | 与 IMSA 官方 CSV 列一致的 CSV |
| **Export (Tyres)** | IMSA 格式 + `Tyres` 列 |
| **Export (Telemetry)** | IMSA 格式 + `Energy Remaining`、`Energy Consumed`、`Energy Refill Time` |
| **Export (Supercars Format)** | IMSA 格式 + Location 后两列 `Kerb Hops`、`Shortcuts`（Natsoft XML feed 有赛道限制警告则为 True，否则 False） |
| **Export (Al Kamel Format)** | 与 WEC/ELMS/AsLMS 的 Alkamel 官方 CSV 列一致 |
| **Export Raw Messages** | 软件收到的全部原始消息，用于核对是否收到所有预期消息 |
| **Export Session Data (JSON)** | 会话数据（cars、laps、stints、flag segments）JSON，供外部工具/自定义分析 |

**JSON 导出步骤**：
1. Data ribbon → Export 组 → **Export JSON** 打开 Session Data Export 工作表；
2. Browse… 选择目标文件路径；
3. 右键树中会话 → **Activate** 将数据载入导出工作表；
4. Ribbon → **Export to JSON** 执行导出。
状态栏显示已加载的车辆、圈、stint、flag segment 数量。
每个 lap 携带 `NumericTags` 对象（`Energy Remaining`、`Energy Consumed`、`Energy Refill Time`、`Remaining P2P`），仅包含计时源实际提供的标签；无遥测的会话该对象为空。

**Auto Replay Export（自动回放导出）**：
- Data ribbon → **Auto Replay Export** 打开工作表；
- Browse… 选保存文件夹（不存在会自动创建）→ **Start**；状态变绿显示 Active——会话切换时自动导出；
- 工作机制：检测到新会话时后台导出上一会话——磁盘已有预生成 `.hhreplay` 则直接复制；否则从项目数据库按原始消息重新生成；文件名取会话名（非法字符替换为 `_`)；
- 状态标签更新最近一次成功导出的文件名与时间，或错误信息；
- **Stop** 或关闭工作表页签即停止；已导出的文件保留在目标文件夹。

**FAQ**
- **Q：导出 replay 给同事要注意什么？** 对方项目必须选择与录制时相同的协议。
- **Q：想把数据丢进 Excel 分析用哪个？** 按系列选 IMSA/Al Kamel/Supercars 等 CSV 格式，或 JSON。
- **Q：如何核对丢消息？** Export Raw Messages。

---

## 6. Remote replays database（远程回放数据库）

**用途**：在 HH Timing 内直接下载并运行历史赛事回放。目前仅部分系列/赛事可用，列表会逐步扩展。

**使用方法**：
1. Data ribbon → **Load Remote Replay**；
2. 首次启动会从 HH Dev 数据库下载可用回放列表；
3. 依次选择 Series、Year、Event、Session 与回放类型；
4. 点 **Load Replay**——下载后自动开始回放。

**锦标赛配置检查**：运行前工具会校验当前 Championship Configuration 是否正确；不匹配会报错，点 **Change** 可从适合该回放的配置列表中选择。

**刷新**：赛事期间 HH Dev 数据库有更新时，点刷新按钮即可刷新列表，无需重启 HH Timing。

**FAQ**
- **Q：回放加载失败提示配置错误？** 点 Change 切换到匹配该系列/赛事的 Championship Configuration。
- **Q：列表里没有我需要的赛事？** 目前仅选定系列/赛事，可联系支持。

---

## 7. HH timing server mode（服务器模式）

**用途**：当计时网络只允许**一台电脑**连接官方 feed 时，由一台实例作服务器，把消息转发给团队内任意多台客户端——客户端无需额外的 feed 连接权限。

### 配置服务器
1. 默认关闭；在**用户选项（Backstage Options）**中启用 **Timing and scoring server enabled**，可同时改端口（默认 **24689**）；
2. **重启软件**后生效；
3. 服务器自动在后台启动（界面无提示）；此时像平常一样连接 T&S feed，或开回放测试；
4. 服务器 IP 显示在 Backstage 的 **About** 页签；
5. 防火墙需放行该端口。

**IP 稳定性（关键）**：服务器 IP 变化会导致客户端计时丢数据。方案：
- 给服务器配**静态 IP**；或
- 客户端改用**计算机名**代替 IP（命令行 `hostname` 查本机名）。
文档强调：服务器无静态 IP 是团队用服务器模式出问题的最常见原因。

### 配置客户端
1. 新建（或复制修改）一个 Championship 项目项；
2. IP 填服务器电脑地址，端口填服务器设置的端口；
3. 协议选择 **“HHTiming”**。

**FAQ**
- **Q：为什么客户端连不上？** 检查服务器 IP 是否变化、端口是否一致、防火墙是否放行、协议是否为 HHTiming。
- **Q：默认端口？** 24689。
- **Q：改了服务器设置没生效？** 必须重启 HH Timing。

---

## 8. Session data recovery（会话数据恢复）

**场景**：比赛过程中电脑崩溃，可恢复到崩溃前状态，最大限度减少中断。

**步骤**：
1. Data 选项卡点击 **Recover**；
2. 选择要恢复的会话（通常是刚才连接的会话）；
3. 重新连接实时会话；
4. 被问是否清空 scoreboard 时点 **“No”**。

恢复后，新的实时计时数据会**追加**到已恢复的数据上——整个会话的数据保持为单一数据集合。

**FAQ**
- **Q：点 Yes 清空 scoreboard 会怎样？** 会丢失已恢复的展示状态；恢复流程要求点 No。
- **Q：恢复后数据会重复吗？** 不会，新数据追加到恢复数据之后，仍是同一份会话数据。

---

## 站点导航（本章源页面）

| 页面 | URL |
|---|---|
| Session data | /timing-data-management/session-data/ |
| Live timing feed connection | /timing-data-management/live-timing-feed-connection/ |
| Timing and scoring data import | /timing-data-management/timing-scoring-data-import/ |
| Replays | /timing-data-management/replays/ |
| Remote replays database | /timing-data-management/remote-replays-database/ |
| HH timing server mode | /timing-data-management/hh-timing-server-mode/ |
| Session data recovery | /timing-data-management/session-data-recovery/ |
| Export session | /timing-data-management/export-session/ |
