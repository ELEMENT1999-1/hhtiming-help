# 系列特定信息（Series Specific Information）章节分析摘要

## 概述

本章节覆盖 help.hhtiming.com 中「Series specific information」下的各赛事系列页面（约 25 个系列 + Indycar 推荐设置子页）。每个系列页面主要说明：

1. **计时数据提供方与连接方式**（Alkamel V2、Swiss Timing FTP/Kafka、Natsoft XML、ITS API、MyLaps、WIGE、TSL、Time Service、HTML Scraping、模拟器协议等）
2. **赛前/赛中 championship configuration 关键参数**（Host、Port、凭据、Additional Options）
3. **赛道地图 / 微扇区（Micro-Sectors）/ 自定义扇区** 配置
4. **系列规则驱动的软件设置**（驾驶时间、最短进站、轮胎、赛道限制警告、策略预测等）
5. **赛后 CSV/XML/PDF/XLS 导入**方式

多数系列依赖具体计时商（见 `timekeeper-specific-info`）；本章页面侧重「本系列用什么协议、怎么配、有哪些坑」。信息密度差异大：Le Mans 24H / IMSA / Indycar / IGTC 内容详尽，MotoGP / GT Open / Cronococa 类页面仅给出连接参数。

---

## 各系列分节

### WEC & ELMS
- **URL**: https://help.hhtiming.com/series-specific-info/wec-elms/
- **数据导入方式**: 实时 Alkamel V2（现场/Cloud）；需联系 Alkamel 购买按锦标赛费用、获取凭据/路由器/WiFi 天线/网络配置。默认配置：WEC Alkamel V2、WEC Alkamel V2 Cloud、ELMS Alkamel V2。
- **特殊设置**: 赛道限制警告（TLW）随 feed 下发；可在 Additional Options 定义自定义扇区（值格式 `Loop1;Loop2`）；支持 Micro-Sectors 作主扇区（ELMS/WEC 分赛道列出 loop 清单）。
- **注意事项**: 仅直连 V2 server 的电脑可定义附加扇区，server mode 客户端自动继承；连不上时排查网络 ping、错误凭据、连接数上限。
- **推荐配置**: 按现场/Cloud 选对应默认配置；需要微扇区时用对应赛道 micro-sector 字符串并选专用赛道图。

### Super GT & Super Formula
- **URL**: https://help.hhtiming.com/series-specific-info/supergt-super-formula/
- **数据导入方式**: Super Formula 可用 RaceNow websocket（`ws://superformula.racelive.jp:6001/get`，3–4 扇区，日/英语言）；Super GT 主要走 HTML Scraping 或赛后 ZIP 内多 CSV（主文件 `YYYY_Rd.X_TRACK_FINAL.csv` + 同目录 `CarNoX.csv`）。
- **特殊设置**: RaceNow 仅 Super Formula 可用；语言字段影响车手/车队名书写系统。
- **注意事项**: HTML Scraping 页面为 Super Formula live 参数；赛后导入须先解压 ZIP 并保证 CSV 同目录。
- **推荐配置**: Super Formula 优先 RaceNow；Super GT 用 Scraping 或赛后 CSV。

### Supercars
- **URL**: https://help.hhtiming.com/series-specific-info/supercars/
- **数据导入方式**: 实时 Natsoft XML（Host `192.168.4.1`，Port `8889`）。
- **特殊设置**: 可将 Micro Sectors 作主扇区（需选对 map contour）；距离赛 + Time Certain（feed 下发结束时刻，自动设 Race Length Mode=Distance、Use time of day=true，Extra lap 保持 True）；轮胎复合物颜色在 Strategy Overview / Tyre Specification Colours 配置（默认 Soft=黑、Hard=橙）；按赛道配置 Control Line / Pit In-Out 参数与 micro-sector 字符串。
- **注意事项**: Practice/Qualifying 有 TLW，违规删圈；每赛道 pit lane 控制线设置不同，必须查表。
- **推荐配置**: 使用各赛道 Micro-sectors 表与 Timing settings per track 表；主记分板加 Curr/Prev Tyres 列。

### rFactor 2
- **URL**: https://help.hhtiming.com/series-specific-info/rfactor2/
- **数据导入方式**: 原型支持；需将 `rFactor2SharedMemoryMapPlugin64.dll` 放入 `\rFactor 2\Bin64\Plugins`，在 Race Center Options 中启用并**完全重启**软件；championship 选 rFactor2 协议，无需其他参数。
- **特殊设置**: 无；HH 端仅选协议。
- **注意事项**: 原型功能，需联系 HH Development；本机需同时连上 rFactor 2。
- **推荐配置**: 联系获取原型版本后再用。

### Porsche Sprint Challenge North America and US West
- **URL**: https://help.hhtiming.com/series-specific-info/porsche-sprint-challenge-na-usw/
- **数据导入方式**: Alkamel V2（北美商店购协议）；可导入官方 championship config 后填用户名密码。赛后 Analysis CSV：`http://usac.alkamelna.com/`，文件格式选 **WEC/ELMS Alkamel**。
- **特殊设置**: GPS 赛道图与 GPS 速度/行车线（仅 V2）；赛道图在 Porsche Sprint Challenge NA & USW 文件夹。
- **注意事项**: 需全程稳定网络，中断会丢数据。
- **推荐配置**: 导入官方 config + 填凭据；启用 GPS 提升定位精度。

### SRO America
- **URL**: https://help.hhtiming.com/series-specific-info/sro-america/
- **数据导入方式**: Alkamel V2 北美；赛后 CSV 来自 `http://usac.alkamelna.com/`，文件格式选 **Al kamel North America**。
- **特殊设置**: 每条赛道有 **ALT 赛道图**——练习/排位必须切到 ALT（减少无效圈）；GPS 模式下仍须选对标准/ALT 图；Am 车手最短驾驶时间在 Car Options 配置（Apply to All / 同类别批量）；Backstage：Predicted Strategy Type=Fixed Stint Lengths，Fixed Stint Length=50 分钟；2026 起 Al Kamel 按凭据过滤 session。
- **注意事项**: GPS 不影响地图选择，选错 ghost 会错位；排位用 Multi Session scoreboard。
- **推荐配置**: 固定进站段 50 分钟 + Drive Time Plugin 管理 Am 驾驶时间。

### NLS & N24
- **URL**: https://help.hhtiming.com/series-specific-info/nls-nbr24/
- **数据导入方式**: WIGE 官方 feed 三种协议：Wige 1/5/9 Sector；Host `192.168.11.233`，Port `80`。
- **特殊设置**: Additional Options：Session Start Time（HH:mm:ss.ddd）、Allow GP Laps（比赛应为 false）、Calculate Start Time；赛后可用 ribbon「Set Session Start Time」修正（不改历史）；NLS Stop Times 文件（VLN Rules 进站时间模式）；多 session 排位用 Multi Session Scoreboard；2022 起可合并排位（Session ID + 保持 config 不清记分板）；NLS Plugin（hh-dev.com）提供最小进站时间记分板；Strategy Overview 的 Pit Stop time mode 设 **VLN Rules**。
- **注意事项**: 建议赛前建好排位/正赛两套 config；Allow GP Laps 正赛 false、计时赛 Calculate Start Time false；NLS Plugin 不适用于无加油/红旗后进站（段表按规则理解，剩余时间向下取整）。
- **推荐配置**: 双 config + Stop Times 文件 + VLN Rules + NLS Plugin。

### N24 2023
- **URL**: https://help.hhtiming.com/series-specific-info/nbr24-2023/
- **数据导入方式**: 与 NLS/N24 相同 WIGE 连接（可精确算正赛开始时刻）。
- **特殊设置**: 每 session 改 Session start time；Race Mode；ghost 车按 N24 进站规则（F / F&T 标记）；首段与后续段进站规则不同（ undercut 时关键，段后改回）；VLN Plugin 最小进站；Avg Lap Time 可手动覆盖。
- **注意事项**: VLN Plugin 在无加油或红旗后进站时不工作；stint 每次进站从 0 重启。
- **推荐配置**: 导入官方 backstage 设置样例，改 Car to follow。

### NASCAR
- **URL**: https://help.hhtiming.com/series-specific-info/nascar/
- **数据导入方式**: NASCAR 协议（multiloop 特殊版）。
- **特殊设置**: **无圈扇区**，仅圈速；软件预置多条 SF 线；未识别时可在 Additional Options 的 `sf lines` 用逗号分隔列出候选（Item1,Item2,...）。
- **注意事项**: 数据以 lap 为基础，不要期望 S1/S2/S3。
- **推荐配置**: 依赖预置 SF 列表；异常赛道手动补 sf lines。

### Le Mans 24 Hours
- **URL**: https://help.hhtiming.com/series-specific-info/lm24/
- **数据导入方式**: Alkamel **现场 / On-Cloud** 两种；V2 JSON 含 GPS。官方预置配置可下载：WEC_LM24_Micro/SZ × Local/Cloud。
- **特殊设置**: 附加 timing loops 定义自定义扇区；Micro Sectors 可 `auto-generated`（Le Mans 约 14 段，配 LeMans_micro 图）或 Slow Zones 作主扇区（字符串 + LeMans_9SZ 图）；自定义扇区可配速度陷阱；建议 race settings：Session Settings、Le Mans 轮廓、每组最大圈数、可选手动平均圈速；检查 Host/Port/Championship Filter/Tyres and Fuel in parallel。
- **注意事项**: 每车本地连接默认 4 路（可付费加）；“Max Number of Connections Reached” 时找 timing and scoring office；SC 编号 1/2/3 绑定 transponder；Slow Zone 结束消息缺失时可用右下角绿旗强制 green；断线恢复：未丢进站 → Recover/Read History=false 不清记分板；丢进站 → Read History=true 清记分板重连。
- **推荐配置**: 下载对应 Local/Cloud + Micro/SZ 预置 config；支持邮箱 support@hh-dev.com。

### iRacing
- **URL**: https://help.hhtiming.com/series-specific-info/iracing/
- **数据导入方式**: 本机须加入 iRacing session（Driver/Crew/Spectator）；championship 选 iRacing 协议即可；可先连 HH Timing 再启模拟器以免丢数据。
- **特殊设置**: iRacing 文件夹赛道图（按扇区长度）；Full Track Map 支持 Distance mode。
- **注意事项**: 黄旗/SC 未处理；组别仅为 iRacing Id 数字；feed 60Hz（精度约 0.0167s）；模拟器 Graphics 中 **Max number of cars 设 63**；账号网站 Connection Type 不能设太低。
- **推荐配置**: Max cars=63 + 足够高连接类型 + 正确赛道图。

### FIA GT World Cup Macau - 2026
- **URL**: https://help.hhtiming.com/series-specific-info/macau/
- **数据导入方式**: ITS Chrono API；需向 ITS 获取 API Key。
- **特殊设置**: Protocol=ITS；Host `https://api-live.its-live.net/v1/DataFeed`；ChampionshipId=`gpmacao`，SeasonId=`2026`，EventId=`73rdmacaugp`，SessionId=`auto`（直播）或 session 号（回放）。**字段大小写敏感**。
- **注意事项**: 赛道图在 "Other" 下；可下载 2019/2022 回放。
- **推荐配置**: 按表填 ID；live 用 SessionId=auto。

### IMSA
- **URL**: https://help.hhtiming.com/series-specific-info/imsa/
- **数据导入方式**: 三种连接：① IMSA Enhanced RMon（Host `timing-data.aks` 或 `10.95.74.12`，Port `10030`）；② Al Kamel V2 北美现场（同 Host，Port `11001`）；③ Cloud（`imsa.datapublisher.alkamelcloud.com:11001`）。赛后：Alkamel Time cards（results.imsa.com，仅 3 扇区）用 **Al Kamel North America** 格式。
- **特殊设置**: V2 支持 micro-sectors（多赛道 loop/micro-sector 表）；Live Excel Export 与 Number of Non-Track Sectors 联动；Championship Regulations：**Fuel and Tires in Parallel=True**；RMon 有忽略错误 best lap 修正的选项；可自定义扇区（`EntryTimeline;ExitTimeline`）；IMSA telemetry（imsa.com/gtp-telemetry）可 Enable Telemetry Reading，主记分板 Energy Rem 等列，可作 custom ghost 输入。
- **注意事项**: telemetry 为非官方、1Hz 滤波取整数据；赛道图从 IMSA 文件夹选；预置 4 种 On Site/Cloud × Micro/Standard 配置。
- **推荐配置**: 现场优先 V2 北美或 RMon；练习/排位注意 micro vs standard 图。

### Indycar
- **URL**: https://help.hhtiming.com/series-specific-info/indycar/ （推荐设置子页：.../indycar/recommended-settings/）
- **数据导入方式**: **唯一** MyLaps RIS Server（Multiloop 已废）。Host：`172.30.16.25`（现场）/ `64.85.132.67`（远程）；Username/Password 由 Indycar 提供；DataSet：Indycar 或 INDY NXT。Telemetry Host：`170.30.16.63` / `64.85.132.31`。
- **特殊设置**: Read Session History / Read Telemetry / Save Telem Raw Messages / Save Telem Data（控制项目体积）；赛道图 ALT/RACE；2026 起 GPS 定位（Car Position Mode=GPS，且 Read Telemetry=True）或 Auto Extrapolated；自定义扇区与速度陷阱；**Tow analysis / No-Tow**（需启用 Tow calculator、平均速度+英制、正确地图）；Pit Commit for Indy；距离/时间赛；轮胎色；Indy 500 / Oval 排位记分板；Weather Conditions；Telemetry 导出模块。
- **注意事项**: mid-session + Read History=true 时 Race Control Messages 可能不取回；cloud feed 暂无 RC 消息；session 名可按赛道类型查表重下；官方无 tow 列（Indy NT*）仅 Multiloop 时有效。
- **推荐配置**: 见推荐设置页——Projected Lap Time Mode=% diff to best、Unit Scheme=Imperial、Race Length Mode=Distance、每赛道 Enforced pit stop time / Stop & Go 表、Car Position Mode=Auto Extrapolated 等。
- **特殊设置（推荐页）**: 分赛道 pit 时间表（St Pete–Laguna Seca）；Pit not as start finish：ALT=TRUE。

### MotoGP
- **URL**: https://help.hhtiming.com/series-specific-info/MotoGP/
- **数据导入方式**: 仅赛后——Import T&S Data 选 **MotoGP XML** 格式并选 XML 文件。
- **特殊设置**: （页面未给更多）
- **注意事项**: 信息极少，无 live 连接说明。
- **推荐配置**: 仅赛后 XML 导入。

### IGTC
- **URL**: https://help.hhtiming.com/series-specific-info/igtc/
- **数据导入方式**: **按分站不同计时商**：
  - Bathurst 12H：Natsoft XML `192.168.4.1:8889`；车库 WiFi 无 feed，最左侧有线口静态 IP（网关 10.0.101.1/2，DNS 8.8.8.8 等）。
  - Spa Prologue / Spa 24H：Swiss Timing FTP（本地 `xml-motorsport.sportresult.com:21` racing-sro；云端 `52.233.255.131:22`）+ Kafka（本地 `10.2.40.3:9093` / 云 servicebus）。
  - Suzuka 1000km：TSL `asia-gt-feed.tsl-timing.com:5208`（需 API Key + Shared Secret，与其他 IGTC 不同）。
  - Indy 8H：Al Kamel NA（可下载 config）。
  - Kyalami 9H：TSL `intgtc-feed.tsl-timing.com:5202`。
  - Gulf 12H：Time Service `getraceresults.com:12952`（联系 Marcel 获取 key）。
- **特殊设置**: Bathurst micro-sectors、3 扇区或 micro 预置 config；**驾驶时间不含维修区**（Bathurst：Driving time continues in pits without driver change=TRUE 的例外说明——页面要求 TRUE 以匹配“同车手不换人则计时”）；Suzuka/Indy/Kyalami：pits 不计驾驶时间→该选项 FALSE，且 Driving time stops at session duration=TRUE；GTWC 类 Fixed Stint Length 模式；Drive Time Plugin；Spa TLW Reset `6/12/18`；Spa 24 Fixed Stint=61 分钟；驱动段可右键覆盖车手名；drive-through 合并 stint（Merge with previous stint）。
- **注意事项**: 每站规则变化大，必须回看本页；Suzuka 键与 GTWC Asia 不同；Kyalami 图在 Blancpain 文件夹；Gulf 图在 IGTC 文件夹；Drive Time Plugin 请用最新版并先用回放练习。
- **推荐配置**: 按站下载/填写对应协议；Suzuka/Indy/Kyalami 最大驾驶 195 分钟（SC/FCY 可扩至 200，插件 EDS）；用 Drive Time Plugin + Track Item 设事件策略参数。

### GTWC Europe
- **URL**: https://help.hhtiming.com/series-specific-info/gtwc-europe/
- **数据导入方式**: Swiss Timing FTP（本地/云）或 Kafka；默认项目含 “GTWC Europe” 与 “Swiss Timing Kafka” 配置。
- **特殊设置**: TLW 随 feed；排位 Multi Session Scoreboard；下载 Drive Time Plugin。
- **注意事项**: 云 feed 延迟更高；Select FTP Directory 仅本地可用；FTP Directory 需按赛事填（或 auto + Block Strings）。
- **推荐配置**: 现场优先本地 FTP 或 Kafka；装 Drive Time Plugin；Fixed Stint 模式（见 IGTC Spa 段）。

### FIA Formula 2 / Formula 3
- **URL**: https://help.hhtiming.com/series-specific-info/f2-f3/
- **数据导入方式**: F2/F3 **Signalr** 协议，URL `https://infopages.fomsystem.com`；连接时会弹多个浏览器登录窗，须保持打开；可在 Additional Connection Information 配 Username/Password 自动填。
- **特殊设置**: Additional Options：`SF At Pit In`（Monaco 类无维修区 SF crossing 时 true）、`Available Tyre Compounds`（两胎名以 `;` 分隔，出站自动换另一胎）、每车号起始胎（key=车号）。赛后 PDF：计时段选 SectorAnalysis；比赛加 Race1HistoryChart + PitStopSummary。
- **注意事项**: session time 精度约 ±1s（无毫秒）。
- **推荐配置**: 配置凭据自动登录；按赛道开 SF At Pit In；两胎名预置。

### FormulaE
- **URL**: https://help.hhtiming.com/series-specific-info/formulae/
- **数据导入方式**: Alkamel V2（费用/凭据/设备同 WEC 流程）；需自建 championship 配置。
- **特殊设置**: Backstage 专有：Attack mode 长度、Extra Time Session Elapsed Time Limit、Maximum Extra Time、激活次数；40 分钟后 extra time 不可增，可手动对齐 marshals；黄旗周期可加 Extra Time 列；Formula E 插件：Best Sector（按 250kW/220kW 过滤）、Remaining Time 记分板。
- **注意事项**: 连不上查凭据/网络/连接数；用 **server mode** 避开连接数限制。
- **推荐配置**: 官网下载最新 FE 插件 + Alkamel V2 + server mode。

### GT Open
- **URL**: https://help.hhtiming.com/series-specific-info/gt-open/
- **数据导入方式**: Cronococa Enhanced RMon；Host `2.136.218.66`，Port `21546`。
- **特殊设置**: （页面仅连接参数）
- **注意事项**: 信息很少。
- **推荐配置**: 新建配置选 Cronococa 协议并填上述 Host/Port。

### EWC
- **URL**: https://help.hhtiming.com/series-specific-info/ewc/
- **数据导入方式**: ITS Chrono API，需 API Key。
- **特殊设置**: Protocol=ITS；Host `https://api-live.its-live.net/v1/DataFeed`；ChampionshipId=`ewc`；SeasonId=`2019-20`；EventId 按站：boldor / 8hofsepang / 24hmotos / 8hofoschersleben / suzuka8h / 24hspa；SessionId=auto 或回放号；**大小写敏感**。
- **注意事项**: 赛道图在 EWC 文件夹。
- **推荐配置**: 按 EventId 表填写；live SessionId=auto。

### DTM
- **URL**: https://help.hhtiming.com/series-specific-info/dtm/
- **数据导入方式**: Swiss Timing FTP（本地 `xml-motorsport.sportresult.com:21`，user `racing-dtm`；云 `52.233.255.131:22`）或 Kafka（同 Swiss Timing 通用端点）。
- **特殊设置**: 需填 FTP Directory（每站不同，参考 Swiss Timing 文档）；Speed Trap 通常 `F,I1,I2`。
- **注意事项**: 云延迟更高；Select FTP Directory 仅本地。
- **推荐配置**: 现场本地 FTP/Kafka；按 FileZilla 树选对 directory。

### Asian Le Mans Series
- **URL**: https://help.hhtiming.com/series-specific-info/asian-le-mans-series/
- **数据导入方式**: Alkamel V2；按站/赛季购买，**每许可 4 连接**；ALMS 与 ALMS Cup 许可分开。Cloud：`alms.datapublisher.alkamelcloud.com:11001`；On-site：`timing-data.aks:11001`（2026 起）。赛后 `http://alms.alkamelsystems.com/` Analysis CSV，格式选 **WEC/ELMS Alkamel**。
- **特殊设置**: TLW；自定义扇区；Micro-sectors（Abu Dhabi/Dubai/Paul Ricard/Sepang 字符串表）；排位加 **2nd Best** 列定第二场发车格（配合 Show Row Number）；2021 及以前为 TimeService 导入。
- **注意事项**: 4 连接上限；仅 server 定义附加扇区；ALMS Cup 仅 cloud。
- **推荐配置**: Cloud 或 On-site V2 + micro-sector 表 + 排位第二好成绩记分板。

### Creventic 24H Series
- **URL**: https://help.hhtiming.com/series-specific-info/creventic/
- **数据导入方式**: 计时商 **Time Service**（详见 timekeeper 章节）：SSL Team Stream + 赛后 getraceresults.com CSV。
- **特殊设置**: **两段赛（Race Part 1/2）驾驶时间结转**：Car Quick Options 中 `Initial Dr [s]`；「Set Current as Initial Driving Times」把当前累计写入初始；「Reset Driving Times」清零。初始驾驶时间存项目文件，重启同项目可保留。
- **注意事项**: Part 2 开始前务必结转，否则 Max/Min Driving Time 规则失真。
- **推荐配置**: Part 1 结束后一键 Set Current as Initial；新赛事 Reset。

### ADAC GT Masters
- **URL**: https://help.hhtiming.com/series-specific-info/adac-gt-masters/
- **数据导入方式**: 两种 live：① Swiss Timing FTP（`scp.sportresult.com:22`，凭据由 Swiss Timing 提供，FTP Client 用 winscp，每站 FTP Directory）；② HTML Scraping（`SportResult.com HTML Scraping`，Website Season `https://www.adac-motorsport.de/adac-gt-masters`，Alternative Link 见页面，IFrameName=`liveStats`）。
- **特殊设置**: Speed Trap Lines=`F, I1, I2`；FTP Directory 示例 Lausitzring 2022 `/data/racing/ADAC GT Masters Lausitzring/ADAC GT Masters/`。
- **注意事项**: FTP Directory 每站不同。
- **推荐配置**: 有 Swiss Timing 凭据用 FTP；否则 Scraping。

---

## 常见问答要点

1. **连不上 Alkamel/现场 feed 怎么办？**  
   先 `ping` 计时服务器 IP；通则查凭据是否正确、是否超连接数（LM24 默认每车 4 路；ALMS 每许可 4 路）；不通则查网络/DNS，或联系计时商确认是否已为本队开通。

2. **Micro-Sectors 和普通 S1/S2/S3 如何切换？**  
   在 championship Additional Options 中设 `Use Micro Sectors As Main Sectors=true`，并按赛道填 micro-sector 字符串（或 Alkamel 的 `auto-generated`）；同时选择对应的 micro 赛道图，否则 ghost 等功能异常。

3. **自定义扇区在 server mode 下为何改了不生效？**  
   附加扇区只能在**直连计时协议的 server 电脑**上定义；client 通过 server mode 自动继承同一套扇区。改定义后 live 中需断开→replay→不清记分板重连，或赛后 replay 才显示。

4. **练习/排位为何要换 ALT 赛道图（SRO America / 部分 IMSA/Indy）？**  
   ALT 扇区定义不同，可减少练习/排位无效计圈；GPS 叠加**不会**自动纠正地图选择，选错图 ghost 位置会错。

5. **赛后导入选什么文件格式？**  
   - Alkamel 系（WEC/ELMS/PSC NA/AsLMS）：**WEC/ELMS Alkamel** 或 **Al Kamel North America**（按页面）  
   - Time Service：**TimeService**（Sector analyse + Result）  
   - Swiss Timing：Sector List CSV（计时赛）+ 进站 PDF + CSV（比赛）  
   - ITS：**ITS XLS Import**（需填 worksheet 名）  
   - MotoGP：**MotoGP XML**  
   - F2/F3：PDF（SectorAnalysis 等）  
   - Super GT：ZIP 内 FINAL.csv + CarNoX.csv  

6. **驾驶时间「进站是否累计」按什么设？**  
   多数 GT（Suzuka/Indy/Kyalami/Gulf 等）：`Driving time continues in pits without driver change=FALSE`，且 `Driving time stops at session duration=TRUE`；Bathurst 有特殊表述需按页面设 TRUE；GTWC 用 Drive Time Plugin 按规则填 Max Driving Time，并用 Merge with previous stint 处理 drive-through。

7. **Indycar / NLS 的 Session Start Time 为何重要？**  
   决定 elapsed time；Indy 排位 session 名有 “Never active live” 的子会话；NLS 可用 ribbon 修正开始时间（不改历史），并建议排位/正赛两套 config。

8. **哪些系列必须装插件？**  
   Drive Time Plugin：GTWC/IGTC/SRO America 等耐力赛；NLS Plugin：N24/NLS 最小进站；Formula E 插件：功率/剩余时间记分板。插件 zip 放 `Documents\HH Timing\Plugins`。

9. **赛道限制警告（TLW）哪些系列有？**  
   WEC/ELMS、Supercars（仅练习/排位，违规删圈）、GTWC Europe、Asian Le Mans、Swiss Timing feed 等；Spa 24 可用 Reset TLW After=`6/12/18` 每 6 小时重置。

10. **模拟器系列（iRacing / rFactor 2）有哪些坑？**  
    iRacing：Max cars=63、Connection Type 调高、黄旗未处理、可先连 HH；rFactor 2：装 SharedMemoryMap 插件到 Bin64\Plugins 并完全重启，championship 仅选 rFactor2 协议。
