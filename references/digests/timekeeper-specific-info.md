# 计时商特定信息（Timekeeper Specific Information）章节分析摘要

## 概述

本章节覆盖 help.hhtiming.com 中「Timekeeper specific info」下 **12 个计时商/协议**页面。与「系列特定信息」按赛事划分不同，本章按**计时提供方**说明：

1. **适用系列**
2. **Live 连接方式**（协议名、Host/Port/URL、凭据来源）
3. **协议或文件格式**（实时流类型、赛后导入格式）
4. **配置要点**（Additional Options、目录路径、GPS、微扇区、限制与坑）

多数系列页面会回链到本章；配置 championship 时应先确认计时商，再查本章细节。

---

## 各计时商分节

### Alkamel V2
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/
- **适用系列**: FIA WEC、ELMS、Formula E、IMSA（北美变体）、Asian Le Mans、Porsche Sprint Challenge NA、SRO America、Indy 8H 等（2017 起 JSON 协议）。
- **连接/导入方式**:  
  - 协议：Al Kamel V2（及 **Al Kamel V2 North America**——IMSA 必须用北美版以把 FCY 当 SC 处理）。  
  - 凭据：向 Al Kamel 购买并获取 username/password。  
  - Host：现场 `timing-data.aks`；WEC Cloud `fiawec.datapublisher.alkamelcloud.com`；IMSA Cloud `imsa.datapublisher.alkamelcloud.com`；AsLMS Cloud `alms.datapublisher.alkamelcloud.com`；端口常见 `11001`。  
  - 赛后：多站 Analysis CSV（WEC/ELMS Alkamel 或 Al Kamel North America 格式）。
- **协议/格式要点**: JSON 协议；含 GPS（`rgps` / `gps` / `no`）；`Record GPS` 控制是否写入回放；`Read History` 读全会话历史（可能丢扇区/进站细节）。
- **配置要点**:  
  - Additional Options：GPS、Record GPS、Read History、自定义扇区（`Loop1;Loop2`，名不得与主 feed 的 S1/S2/S3/Speed1 等冲突；可加距离作速度陷阱）、Micro-Sectors（成对分号/逗号列表或 `auto-generated`）+ `Use Micro Sectors As Main Sectors=true` + 专用图。  
  - Live Excel Export：micro 作主扇区时 S1–S9 对应新主扇区，需设 Number of Non-Track Sectors（如 3），NTS1–3 对应原 S1–3。  
  - 排名：HH 内部构建记分板（数据完整性优先），官方 TV 名次用 P (Feed)/Gap (Feed)/Best (Feed) 列。  
  - 2026 起按凭据过滤 session：支持系列未开赛时只见绿点无 session 名。  
  - GPS 地图：Premium 下 GPS 可用；**GPS 图上不能显示 ghost**，需关 GPS。  
  - 连接数有限，Formula E 等可用 **server mode** 省连接。  
  - Track Limits：invalid 消息缺失/延迟则无法自动删圈。

### Alkamel standard
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/aklamel-standard/
- **适用系列**: 2017 前旧协议（遗留/部分旧数据）。
- **连接/导入方式**: AlKamel Standard 协议；HH 内置 **Generic Alkamel** 与 **WEC Standard** 两套配置。
- **协议/格式要点**: 旧式协议（非 V2 JSON）。
- **配置要点**: WEC Standard 含 Championship Filters 与 Regulations；用于 ELMS 时须关掉 Championship Filters 或自建 ELMS 过滤配置。

### Swiss Timing
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/swiss-timing/
- **适用系列**: GT World Challenge Europe、DTM、Spa 24H/Prologue、ADAC GT Masters（部分 FTP）等。
- **连接/导入方式**:  
  - **Swiss Timing FTP**：本地 `xml-motorsport.sportresult.com:21`（用户/密码因系列：racing-sro / racing-dtm 等）；云 `52.233.255.131:22`。  
  - **Swiss Timing Kafka**：本地 `10.2.40.3:9093`；云 `evhns-prod-realtime-msp-westeurope.servicebus.windows.net:9093`（默认项目含 “Swiss Timing Kafka”）。  
  - 现场网络：5GHz 无线（如 XMLFEED# / TEAMS2023）或维修墙 RJ45 交换机（建议网线 ≤85m）。  
  - 赛后：GT Team Area 下载 Sector List CSV（计时赛）；比赛需 **Pit Stop List PDF + Sector List CSV**。
- **协议/格式要点**: 独特的 **FTP 目录分发**实时数据；Kafka 低延迟、自动订阅当前 session。
- **配置要点**:  
  - FTP Directory：每站手选（Select FTP Directory 树，仅本地）或 FileZilla 核对；路径末尾可加 `NEWEST` 自动跟最新会话；`FTP Directory=auto`（实验）+ **FTP Block Strings** 屏蔽其他系列。  
  - Additional sectors：`Loop1;Loop2`（仅 server 定义，client 继承）；示例 Imola `F,I1,I2,PI,PO` 等。  
  - Speed Trap Lines：常见 `F,I1,I2`（逗号无空格）；各站可能不同（Monza/Imola/Brands Hatch 等 tip 列表）。  
  - **Use Swiss Timing Lap Number**：排位/练习 false，正赛 true（feed 会覆盖无效圈导致圈数不准）。  
  - TLW 与 invalid 圈：延迟下发，#TLW 列 + Car Scoreboard TrackLimits 列。  
  - 故障排查：先用 FileZilla/ping `xml-motorsport.sportresult.com` 验证是否能访问 FTP，再怀疑 HH Timing。

### TSL Timing
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/tsl-timing/
- **适用系列**: GT World Challenge Asia、British GT、BTCC、IGTC 部分分站（Suzuka 1000km、Kyalami 等）。
- **连接/导入方式**: 互联网 TSL 协议；Host/Port **向计时商申请**（例：Suzuka `asia-gt-feed.tsl-timing.com:5208`；Kyalami `intgtc-feed.tsl-timing.com:5202`）；部分系列需 **API Key + Shared Secret**。
- **协议/格式要点**: 实时 TSL 流；赛后需向 TSL 申请数据访问，选 **sector Analysis.csv** 走标准 T&S 导入。
- **配置要点**: 新建 championship 选 TSL 协议→填 Host/Port/密钥→Connect；手机热点通常可用。

### Time Service
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/time-service/
- **适用系列**: Creventic 24H Series（最常见）、Gulf 12 Hours 等。
- **连接/导入方式**: 协议 **Time Service Team Stream (SSL)**；需向计时商索取 **Host、Port、key（每队唯一密码）**（Gulf 示例 Host `getraceresults.com`，Port `12952`）。赛后从 getraceresults.com 下 **Sector analyse（open CSV）+ Result（open CSV）**。
- **协议/格式要点**: SSL 实时流；赛后双 CSV。
- **配置要点**: `Allow refresh=true` 时补连后可拉齐全部历史圈；false 只收连接之后数据；导入文件格式选 **TimeService**；Creventic 两段赛驾驶时间结转见系列页。

### Natsoft
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/natsoft/
- **适用系列**: 澳大利亚系列——Australian Supercars、Australian GT、IGTC Bathurst 分站。
- **连接/导入方式**: 协议 **Natsoft XML**；实时需向计时商要 **Host、Port**（Supercars/Bathurst 常见 `192.168.4.1:8889`）；回放只需先建 championship（可不填 Host/Port）。
- **协议/格式要点**: XML 实时 feed；微扇区与 pit 控制线语义特殊。
- **配置要点**:  
  - Microsectors：可选；成对 `I3,P1;P1,I1;...`；`Use Micro Sectors As Main Sectors=true` + 正确 map contour。  
  - **Pit lane 三参数**：Control Line At Pit Out / Use Control Line As Pit Out / Use Control Line As Pit In——按赛道设置（Supercars 见系列页表；Bathurst 控制线在 Pit In）。  
  - 微扇区线路因赛道而异，须与计时商确认。

### ITS Chrono
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/its-chrono/
- **适用系列**: Macau GP、Ultimate Cup、French GT4、EWC。
- **连接/导入方式**: 协议 **ITS**；默认 Host `https://api-live.its-live.net/v1/DataFeed`；需 **ApiKey**（联系 Sebastien Mascret）；ChampionshipId / SeasonId / EventId / SessionId。赛后从 its-results.com 下 **lap by lap ranking XLS**。
- **协议/格式要点**: HTTP JSON DataFeed；赛后 XLS。
- **配置要点**: SessionId=`auto`=直播，或数字 session 号回放；ID 从 its-live.net URL 解析（`/live/<ChampionshipId>/<SeasonId>/<EventId>`）；**全部字段大小写敏感**；导入选 **ITS XLS Import** 并填写 worksheet 名（先打开 XLS 查名再关）。

### USAC Timing
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/usac/
- **适用系列**: USAC 相关及 SRO America 等（URL/端口按锦标赛，见 GitHub naming conventions）。
- **连接/导入方式**: 双协议：  
  - **USAC Web Socket Timing Protocol**（推荐：有车手名、1Hz GPS）——URL 按系列查 `https://github.com/usacnation/usac-mlp/...`。  
  - **USAC Multiloop Timing Protocol**——Host `timing.usacnation.com`，Port 按系列。  
  - 赛后：**USAC CSV Import**。
- **协议/格式要点**: Websocket / Multiloop；GPS 1Hz 不能算速度，off-track 显示勿用 GPS 模式。
- **配置要点**:  
  - `add class to name=true`：非官方测试时防同号跨组冲突，车号变为 `CarNumber-ClassName`（HHDM 用户 Car ID 列同构）；官方 session 改回 false。  
  - `Time zone delta`：校正 Race Control 消息的时刻（小时）。  
  - 联系人 Wes Ratcliff（srotiming@usacnation.com）。

### Perugia Timing
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/perugia-timing/
- **适用系列**: Italian GT、Lamborghini Super Trofeo Finals。
- **连接/导入方式**: 协议 **Perugia Live Data Connection Protocol**；互联网连接；Host、Username、Password 由 Perugia 提供；另需 **EventId**。
- **协议/格式要点**: 专有 live 协议。
- **配置要点**: EventId=浏览器打开 live timing URL 的最后一段。

### MyLaps X2 Server
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/MyLaps-X2/
- **适用系列**: 主要用于**无官方计时的测试**。
- **连接/导入方式**: 独立桌面工具连接 MyLaps X2 Server，把 loop crossing 转成 HH Timing 消息；HH Timing 侧用 **HH Timing 协议**（Host=工具地址/localhost，Port=工具 Output Port）。
- **协议/格式要点**: X2 → 本地转发服务 → HH Timing。
- **配置要点**: 工具 Settings 配 Cars（车号/组别/厂牌/应答器）、SF Lines、In Pits SF Lines、Pit In/Out Lines、Sectors；Timing 配 X2 Host/凭据、Session Start Time、Output Port（占用则改端口重启）；Session Type=Practice/Race；Skip X2 cars 忽略未在本地配置的车；连接指示灯绿/红。

### MyLaps HTML Scraping - SpeedHive
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/MyLaps-SpeedHive/
- **适用系列**: 计时发布在 `https://speedhive.mylaps.com/` 的赛事。
- **连接/导入方式**: 协议 **MyLaps HTML Scraping**；互联网；Host=当前 live timing 全屏页基础地址。
- **协议/格式要点**: HTML 抓取（非结构化 feed）。
- **配置要点**: 定义 Number of Sectors（=有效扇区数）；若页面显示「有用扇区间隔一个空扇区」，设 `skip 1 sector out of 2=true`。

### Cronococa Enhanced RMon Timing
- **URL**: https://help.hhtiming.com/timekeeper-specific-info/Cronococa/
- **适用系列**: GT Open。
- **连接/导入方式**: 协议 **Cronococa Enhanced RMon Timing**；互联网；Host/Port 由 Cronococa 提供（GT Open 示例：`2.136.218.66:21546`）。
- **协议/格式要点**: Enhanced RMon 类实时流。
- **配置要点**: 页面信息很少——按计时商给的 Host/Port 填入即可。

---

## 常见问答要点

1. **如何选择正确的计时商协议？**  
   先看系列页写的 provider（Alkamel / Swiss Timing / Natsoft / ITS / TSL / Time Service / MyLaps / Cronococa…），再打开对应 timekeeper 页填 Host/Port/凭据；同一赛事不同分站可能换 provider（IGTC 典型）。

2. **Alkamel V2 与 V2 North America 有何区别？**  
   IMSA 必须用 **North America** 变体（FCY 按 SC 处理）；Host 也不同（Cloud/现场见系列页）。凭据与连接数仍由 Al Kamel 管理。

3. **Swiss Timing 为何要填 FTP Directory？数据不更新怎么排查？**  
   实时数据按赛事文件夹放在 FTP 上，必须指到正确 round/championship（可 `NEWEST` 或 `auto`+Block Strings）。先用 FileZilla/`ping xml-motorsport.sportresult.com` 确认网络与目录可见，再查 HH Timing；Kafka 可作低延迟替代且免选目录。

4. **Micro-Sectors 配置的通用步骤是什么？**  
   Additional Options 填微扇区字符串（或 auto-generated）→ `Use Micro Sectors As Main Sectors=true` → 选 micro/专用赛道图 →（可选）设置 Number of Non-Track Sectors 以保证 Excel 导出列正确。仅 server 端可定义，client 继承。

5. **GPS 车位模式有什么限制？**  
   Alkamel：GPS 图**不能显示 ghost**，需切回非 GPS；USAC Websocket GPS 仅 1Hz，不能算速度，off-track 显示勿用 GPS；Indy 2026 GPS 需 Read Telemetry=true；SRO America GPS 下仍要选对标准/ALT 图。

6. **赛后导入的常见格式对应关系？**  
   Alkamel CSV → WEC/ELMS Alkamel 或 Al Kamel North America；Time Service → TimeService（双 CSV）；Swiss Timing → Sector List CSV（+比赛进站 PDF）；ITS → ITS XLS Import（+worksheet 名）；USAC → USAC CSV；TSL → sector Analysis.csv；MotoGP → MotoGP XML。

7. **连接数超限怎么办？**  
   Alkamel 常限制每许可约 4 路：合并使用、申请加购，或启用 **HH Timing server mode** 让多台客户端共享一路 feed。

8. **Websocket vs Multiloop（USAC）怎么选？**  
   优先 Websocket：有车手名、有 GPS；Multiloop 可能缺车手名。GPS 模式下不要用依赖速度的 off-track 显示。

9. **Speedhive / HTML Scraping 抓取要注意什么？**  
   Host 必须是当前全屏 live 页地址；正确设置扇区数；存在空扇区占位时开 skip 1 sector out of 2。

10. **X2 测试工具连接失败？**  
    检查 X2 Server Host/密码、Output Port 是否被占用（Server Status=Failed to start 则换端口重启）、HH Timing 协议 Host/Port 是否与工具一致；Session Type 与本地车辆列表/SF 线定义是否完整。
