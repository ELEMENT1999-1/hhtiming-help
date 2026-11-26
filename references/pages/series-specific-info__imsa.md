---
url: https://help.hhtiming.com/series-specific-info/imsa/
title: IMSA
slug: series-specific-info__imsa
---

# IMSA

-
- Series specific information
- IMSA

# IMSA

## Live Data Connection​

Information
3 type of connections will be available:

- Traditional IMSA Enhanced RMon Timing connection - explain below in this document
- Al Kamel V2 Prococol - On Site [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2] - connection in pit lane on the same network as IMSA Enhanced RMon Timing
- Al Kamel V2 Protocol - On Cloud [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2] - connection via internet
Both Al Kamel V2 connections will perform the same and use the exact same protocol.

To connect live to an IMSA event, you need to setup your championship configuration depending of the protocol.

### Al Kamel V2 North America​

#### Cloud​

 |  |
| Protocol | Al Kamel V2 North America
| Host | imsa.datapublisher.alkamelcloud.com
| Port | 11001

[内嵌示意图]

#### On Site​

 |  |
| Protocol | Al Kamel V2 North America
| Host | timing-data.aks
| Port | 11001

[内嵌示意图]

If the connection cannot be established via timing-data.aks as host, please try by replacing it with the following IP address : 10.95.74.12

#### Micro-Sectors​

Micro-Sectors [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/#microsectors---using-micro-sectors-as-main-sectors] are available in IMSA SportsCar Championship using Alkamel v2 feed.

#### List of loops Per Track​

#### Daytona: FL,T2,IM1,T4,T5,T6,T7,IM2,T9,TA,TB,TC,TD,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_1-461f37ac9129cf7098b6b1c3acb666c3.png)

#### Sebring: FL,T2,IM1,T4,T5,T6,IM2,T8,T9,TA,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_2-68c38afb755eb496e1120cc33fa70204.png)

#### Long Beach: FL,T2,T3,T4,T5,IM1,T7,T8,IM2,TA,TB,TC,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_3-7acf9b10c3b8b30071bfd9556865c883.png)

#### Laguna Seca: FL,T2,T3,T4,IM1,T6,IM2,T8,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_4-40537ffb4e3c21c4eca9679b3d68e283.png)

#### Detroit: FL,T3,T4,IM1,T6,T7,T8,T9,IM2,TB,TC,TD,TF,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_5-a53d6a9a0e3c113f4a70ddf42ada3c80.png)

#### Mid-Ohio: FL,T2,IM1,T4,T5,T6,T7,T8,IM2,TA,TB,TC,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_6-f68951ad95cab9990ae71600c02ad795.png)

#### Watkins Glen: FL,T2,T3,IM1,T5,T6,T7,IM2,T9,TA,TB,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_7-6431ff08e862a491001e78920596bd9f.png)

#### Canadian Tire Motorsport Park (CTMP): FL,T2,IM1,T4,IM2,T6,T7,T8,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_8-f2838f9042f442dd126761e54132a6b7.png)

#### Road America : FL,T2,IM1,T4,T5,T6,IM2,T8,T9,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_9-8efde0b12c90e894dacdd385b2ac9a6f.png)

#### VIR : FL,IM1,T3,T4,IM2,T6,T7,T8,T9,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_10-4d2235efd4905ffb7863c805e8ccbdf7.png)

#### Indianapolis : FL,T2,T3,T4,IM1,T6,T7,T8,T9,IM2,TB,TC,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_11-0b1463f9f52818aecac65a7bb5aea9f0.png)

#### Road Atlanta : FL,T2,IM1,T4,IM2,T6,T7,T8,Speed1,PitIn,PitOut​

![](https://help.hhtiming.com/assets/images/imsa_track_12-f777708a533aaa32cb721d07dcae343b.png)

These timing loops can be used to create custom sectors, in the additional options of the championship configuration before connecting. Here is the list of micro-sectors per track for the IMSA SportsCar Championship:

 | Track | Micro-sectors
| Daytona | FL,T2;T2,IM1;IM1,T4;T4,T5;T5,T6;T6,T7;T7,IM2;IM2,T9;T9,TA;TA,TB;TB,TC;TC,TD;TD,FL
| Sebring | FL,T2;T2,IM1;IM1,T4;T4,T5;T5,T6;T6,IM2;IM2,T8;T8,T9;T9,TA;TA,FL
| Long Beach | FL,T2;T2,T3;T3,T4;T4,T5;T5,IM1;IM1,T7;T7,T8;T8,IM2;IM2,TA;TA,TB;TB,TC;TC,FL
| Laguna Seca | FL,T2;T2,T3;T3,T4;T4,IM1;IM1,T6;T6,IM2;IM2,T8;T8,FL
| Detroit | FL,T3;T3,T4;T4,IM1;IM1,T6;T6,T7;T7,T8;T8,T9;T9,IM2;IM2,TB;TB,TC;TC,TD;TD,TF;TF,FL
| Mid-Ohio | FL,T2;T2,IM1;IM1,T4;T4,T5;T5,T6;T6,T7;T7,T8;T8,IM2;IM2,TA;TA,TB;TB,TC;TC,FL
| Watkins Glen | FL,T2;T2,T3;T3,IM1;IM1,T5;T5,T6;T6,T7;T7,IM2;IM2,T9;T9,TA;TA,TB;TB,FL
| CTMP | FL,T2;T2,IM1;IM1,T4;T4,IM2;IM2,T6;T6,T7;T7,T8;T8,FL
| Road America | FL,T2;T2,IM1;IM1,T4;T4,T5;T5,T6;T6,IM2;IM2,T8;T8,T9;T9,FL
| VIR | FL,IM1;IM1,T3;T3,T4;T4,IM2;IM2,T6;T6,T7;T7,T8;T8,T9;T9,FL
| Indianapolis | FL,T2;T2,T3;T3,T4;T4,IM1;IM1,T6;T6,T7;T7,T8;T8,T9;T9,IM2;IM2,TB;TB,TC;TC,FL
| Road Atlanta | FL,T2;T2,IM1;IM1,T4;T4,IM2;IM2,T6;T6,T7;T7,T8;T8,FL
You can choose the name you want but the value should always be: Loop1;Loop2

You can only define additional sectors on a computer directly connected to Alkamel V2 North America Protocol (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

Live Excel Export

- If Use Micro Sectors As Main Sectors is set to true:Standard sectors S1 to S9 will correspond to your new main sectors so SZ1 to SZ9. ![](https://help.hhtiming.com/assets/images/imsa_28-35189e4fd7a26f4527ea6a6be62a885c.png)
- It is required to define the Number of Non-Track Sectors in the backstage option (e.g., 3):
- ![](https://help.hhtiming.com/assets/images/imsa_29-5641eca752c6c49e6dc514b857f2a3c3.png) Then, NTS1 to NTS3 will correspond to the original S1 to S3.
- ![](https://help.hhtiming.com/assets/images/imsa_30-1043188009ad53e9c59eff66c91dca88.png)

- If Use Micro Sectors As Main Sectors is not set or set to false:Standard sectors remain named S1 to S3.
- All non-track sectors, including slow zones, will appear as NTS entries (e.g., NTS1, NTS2, ...).

#### Championship configurations examples​

Information
Find Below some examples of championship configurations :

- Al Kamel V2 Prococol - On Site - Micro - Auto Generated - connection in pit lane on the same network as IMSA Enhanced RMon Timing with micro sectors as main sectors
- Al Kamel V2 Prococol - On Site - Standard - connection in pit lane on the same network as IMSA Enhanced RMon Timing
- Al Kamel V2 Prococol - On Cloud - Micro - Auto Generated - connection via internet with micro sectors as main sectors
- Al Kamel V2 Prococol - On Cloud - Standard - connection via internet

### IMSA Enhanced RMon Timing connection​

 |  |
| Protocol | IMSA Enhanced RMon Timing
| Host | timing-data.aks
| Port | 10030

[内嵌示意图]

If the connection cannot be established via timing-data.aks as host, please try by replacing it with the following IP  adress : 10.95.74.12

#### Additional Option​

[内嵌示意图]

It happens that some wrong best lap time correction message get send on the IMSA Enhanced RMon Timing protocol. This can lead to laps not being displayed when replaying/activating a session. If this is the case the option can be set to True. By default, the option is at False.

#### Additional Sectors​

In the Additional Options, you can now create your own sectors, using the timing lines names [https://help.hhtiming.com/tips_tricks/copy-loops-list].
For example, at Daytona, timelines names are:
On Track:T1,T3,T4
In Pits: P5,P1,P2

![](https://help.hhtiming.com/assets/images/imsa_3-4df80039f4c58759278c42a46c85922d.png)

You can choose the name you want, but the value should be `Entry Timeline;Exit Timeline`. For example if you want to create a sector from SF Line to Pit Entry, you will need to enter `T1;P5` as value:

[内嵌示意图]

### Championship Regulations​

The championship regulations should be set as follow:

 |  |
| Fuel and Tires in Parallel | True

[内嵌示意图]

## Track Maps​

The track maps for each events needs to be selected in the IMSA Folder:

[内嵌示意图]

## Post Session CSVs Data Import​

2 types of CSVs can be imported in HH Timing using the Import T&S Data [https://help.hhtiming.com/timing-data-management/timing-scoring-data-import] function.

### Alkamel "Time cards"​

This file can be download directly following a session on results.imsa.com/ inside a specific session. This files only contains the 3 sectors information.

![](https://help.hhtiming.com/assets/images/imsa_7-2cb8b8e7561bdd7de02bf2282f666dca.png)

This file can be imported using the Al Kamel North America file format and using the appropriate Timed or Race option.

[内嵌示意图]

## IMSA telemetry​

HH Timing can now record and display IMSA telemetry data provided by IMSA GTP & GTD telemetry website: https://www.imsa.com/gtp-telemetry/.

Add the Enable Telemetry Reading parameter to the championship config from either IMSA Enhanced RMon Timing protocol (IMSA Timing) or Al Kamel V2 North America protocol to enable the recording.

[内嵌示意图]

Recorded from the telemetry, the following columns will be available on the main scoreboard:

- Energy Rem
- Energy % consumed Last Lap
- Energy Refill Time

![](https://help.hhtiming.com/assets/images/imsa_17-2b7bcd415e8d3d9a9911c284c946c67e.png)

Those metrics can be plotted using lap numeric tag graphs.

![](https://help.hhtiming.com/assets/images/imsa_18-9bce80bbc3e305fdf34f0da8b91bc86d.png)

The Y-Axis can be selected using the Configure Graph option:

[内嵌示意图]

Here is an example for the energy remaining:

![](https://help.hhtiming.com/assets/images/imsa_21-723df6f741d7c7b45a71cd721af795f6.png)

The Energy Refill Time can also be used directly as an input for the custom ghost by enabling the Incl GTP Refill Time option in the custom ghosts [https://help.hhtiming.com/settings-options/track-item-ghosts/#custom-ghosts] settings.

Although currently named GTP, this option can also be used for GTD.

[内嵌示意图]

Example on full track map:

![](https://help.hhtiming.com/assets/images/imsa_23-b73cd7f9fa7d789c2a54afda12f550b8.png)

Data Fidelity
The intention of IMSA is to provide an immersive experience and insight of the race strategy for fans, TV and radio commentators. Therefore the data is unofficial and may not reflect the reality. The website provides 1 Hz filtered and rounded data.

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- Workbooks & layouts — https://help.hhtiming.com/workbooks-layouts/
- Displays — https://help.hhtiming.com/displays/
- Timing data management — https://help.hhtiming.com/timing-data-management/session-data/
- Settings & options — https://help.hhtiming.com/settings-options/backstage-settings/
- Excel exports — https://help.hhtiming.com/excel-exports/live-excel-export/
- Reporting — https://help.hhtiming.com/reporting/
- Series specific information — https://help.hhtiming.com/series-specific-info/imsa/
- IGTC — https://help.hhtiming.com/series-specific-info/igtc/
- WEC & ELMS — https://help.hhtiming.com/series-specific-info/wec-elms/
- Le Mans 24 Hours — https://help.hhtiming.com/series-specific-info/lm24/
- NLS & N24 — https://help.hhtiming.com/series-specific-info/nls-nbr24/
- N24 2023 — https://help.hhtiming.com/series-specific-info/nbr24-2023/
- Indycar — https://help.hhtiming.com/series-specific-info/indycar/
- Supercars — https://help.hhtiming.com/series-specific-info/supercars/
- SRO America — https://help.hhtiming.com/series-specific-info/sro-america/
- FIA GT World Cup Macau - 2026 — https://help.hhtiming.com/series-specific-info/macau/
- Super GT & Super Formula — https://help.hhtiming.com/series-specific-info/supergt-super-formula/
- EWC — https://help.hhtiming.com/series-specific-info/ewc/
- ADAC Gt Masters — https://help.hhtiming.com/series-specific-info/adac-gt-masters/
- iRacing — https://help.hhtiming.com/series-specific-info/iracing/
- rFactor 2 — https://help.hhtiming.com/series-specific-info/rfactor2/
- FIA Formula 2 / Formula 3 — https://help.hhtiming.com/series-specific-info/f2-f3/
- GTWC Europe — https://help.hhtiming.com/series-specific-info/gtwc-europe/
- DTM — https://help.hhtiming.com/series-specific-info/dtm/
- FormulaE — https://help.hhtiming.com/series-specific-info/formulae/
- Asian le mans series — https://help.hhtiming.com/series-specific-info/asian-le-mans-series/
- Porsche Sprint Challenge North America and US West — https://help.hhtiming.com/series-specific-info/porsche-sprint-challenge-na-usw/
- MotoGP — https://help.hhtiming.com/series-specific-info/MotoGP/
- NASCAR — https://help.hhtiming.com/series-specific-info/nascar/
- GT Open — https://help.hhtiming.com/series-specific-info/gt-open/
- Creventic 24H Series — https://help.hhtiming.com/series-specific-info/creventic/
- Timekeeper specific info — https://help.hhtiming.com/timekeeper-specific-info/natsoft/
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/
- Al Kamel V2 Prococol - On Site — https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2
- timing lines names — https://help.hhtiming.com/tips_tricks/copy-loops-list
- Import T&S Data — https://help.hhtiming.com/timing-data-management/timing-scoring-data-import

