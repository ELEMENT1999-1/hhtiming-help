---
url: https://help.hhtiming.com/series-specific-info/asian-le-mans-series/
title: Asian le mans series
slug: series-specific-info__asian-le-mans-series
---

# Asian le mans series

-
- Series specific information
- Asian le mans series

# Asian le mans series

## Live Data Connection​

In Asian Le Mans Series, Alkamel [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2] is the timing provider.

## V2 Protocol​

Prior to get access to the timing data, make sure that you have purchased the V2 Protocol on the Alkamel store:

- There is a per event fee or a full season pack fee.
- Each license includes 4 connections to the V2 Protocol.
- The license is filtered per championship: Asian Le Mans Series and Asian Le Mans Cup need one license each.
- Alkamel will provide you with credentials by email.
The V2 Protocol is available on cloud or on-site (garage network), for the same price:

- Cloud - you only need an internet connection. No specific router is needed, you can use your own. You get the same data as on-site.
- On-site - available since 2026 for teams with the necessary infrastructure, through the garage network. Teams without it will be connected on cloud. You may have to use a router provided by Alkamel, they will inform you on how to proceed.
Asian Le Mans Cup is available on cloud only.

 |  | Cloud | On-site
| Protocol | Al Kamel V2 | Al Kamel V2
| Host | alms.datapublisher.alkamelcloud.com | timing-data.aks
| Port | 11001 | 11001
| Username | Provided by Alkamel | Provided by Alkamel
| Password | Provided by Alkamel | Provided by Alkamel
You can find specific help file for V2 protocol here [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2].

## Track Limits Warning​

Track Limits Warning are sent in the feed in Asian Le Mans Series. It will be displayed in the main scoreboard, the car scoreboard, the driver scoreboard and the Track Limit Warning display. You can find specific help file here [https://help.hhtiming.com/displays/track-limits-warning].

## Troubleshooting​

If you can't connect, it may come from a network problem, from wrong credentials or because you reached the maximum number of connections.

### Network problem​

To check that your network configuration is correct:

- Open a command prompt and type "If you get a response like :Reply from 192.168.74.12: bytes=32 time=3ms TTL=64, your network configuration is correct and you should contact Alkamel to see if they activated the feed for your team.
- Otherwise type "If you get a response like :Reply from 192.168.74.12: bytes=32 time=3ms TTL=64, you have a DNS issue. Please check your setup with your IT department.
- Otherwise, please check your network setup with your IT department.

### Wrong credentials (V2 Protocol)​

Please ask Alkamel to confirm that you are using the right credentials to connect to the feed.

### Number of connections​

Alkamel limits the number of connections to their feed to 4 per license.

Additional sectors
On each track, there are more timing loops that you can use to create custom sectors.

For example at Sepang, there are 7 loops, FL, SCL2, IP1, IP2, PL1 and SCL1. You can create a sector from FL to SCL2 for example by adding it to the additional options of the championship configuration before connecting:

[内嵌示意图]

You can choose the name you want but the value should always be: Loop1;Loop2

You can only define additional sectors on a computer directly connected to Alkamel V2 Protocol  (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

## Micro-Sectors​

Micro-Sectors [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/#microsectors---using-micro-sectors-as-main-sectors] are available in Asian Le Mans Series using Alkamel v2 feed.

### AsLMS List of Micro-Sectors Per Track​

#### List of loops per track​

Abu Dhabi: FL, SCL2, IP1, VMAX2, IP2, SCL1

![](https://help.hhtiming.com/assets/images/asian_10-9976700895777e9cf49abffef795436a.png)

Dubai: FL, SCL2, IP1, VMAX2, IP2, SCL1

![](https://help.hhtiming.com/assets/images/asian_11-c7d690110262ed52153a9efa73a73c11.png)

Paul Ricard: FL, SCL2, IP1, IP2, SCL1

![](https://help.hhtiming.com/assets/images/asian_14-352402adaec4043f8821e858556bb163.png)

Sepang: FL, SCL2, IP1, IP2, PL1, SCL1

![](https://help.hhtiming.com/assets/images/asian_12-90f5e34a20ee0cc575b46c18eaefd2aa.png)

These timing loops can be used to create custom sectors, in the additional options of the championship configuration before connecting. Here is the list of micro-sectors per track for the AsLMS championship:

 | Track | Micro-sectors
| Abu Dhabi | FL,SCL2;SCL2,IP1;IP1,VMAX2;VMAX2,IP2;IP2,SCL1;SCL1,FL
| Dubai | FL,SCL2;SCL2,IP1;IP1,VMAX2;VMAX2,IP2;IP2,SCL1;SCL1,FL
| Paul Ricard | FL,SCL2;SCL2,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
| Sepang | FL,SCL2;SCL2,IP1;IP1,IP2;IP2,PL1;PL1,SCL1;SCL1,FL
You can only define additional sectors on a computer directly connected to Alkamel V2 Protocol (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

## Qualifying​

Adding the 2nd Best column during qualifying helps determine the starting grid for the second race. Creating a second scoreboard with this column and activating the 'Show Row Number' option completes the setup.

![](https://help.hhtiming.com/assets/images/asian_7-ca442c76f6f5d02d6c26c37a1a69263e.png)

![](https://help.hhtiming.com/assets/images/asian_8-40161b287bf8e95744d6d007b6ebb6d3.png)

![](https://help.hhtiming.com/assets/images/asian_9-2d89514ff3f748a86348063c7ec88ba9.png)

## Post Session CSVs Data Import 2022​

Download the Analysis CSV from http://alms.alkamelsystems.com/

![](https://help.hhtiming.com/assets/images/asian_1-9e1a1ca7b8ab0fcee75454cf3a1c2de2.png)

In HH Timing, choose WEC/ELMS Alkamel as file format in "Import T&S Data" and select the CSV file.

## Post Session CSVs Data Import before 2022​

Until 2021, TimeService was the timing provider for Asian Le Mans Series. Find here [https://help.hhtiming.com/timekeeper-specific-info/time-service/#post-session-static-data-import] our help file regarding T&S Import with TimeService csv.

## Track Maps​

The track maps for each events needs to be selected in the Asian Le Mans Series Folder:

![](https://help.hhtiming.com/assets/images/asian_5-923393f449b25e206ccbd6f024acc28b.png)

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
- Alkamel — https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2
- here — https://help.hhtiming.com/displays/track-limits-warning

