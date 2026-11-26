---
url: https://help.hhtiming.com/series-specific-info/wec-elms/
title: WEC & ELMS
slug: series-specific-info__wec-elms
---

# WEC & ELMS

-
- Series specific information
- WEC & ELMS

# WEC & ELMS

In WEC and ELMS, Alkamel [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2] is the timing provider.

## V2 Protocol​

Prior to get access to the timing data, make sure that you have contacted Alkamel:

- There is a fee that is usually a per championship fee.
- You would need to get Alkamel to enable V2 protocol for your team.
- They should provide you with credentials.
- They should provide you a router and a WIFI antenna.
- They should also provide you with a Network configuration.
You can find specific help file for V2 protocol here [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2].

## Championship Configuration​

Depending on which protocol you choose, there's 3 default championship configuration for Alkamel:

- WEC Alkamel V2 - you can use this protocol in WEC or ELMS. You will have to fill your credentials. You can add filters for WEC.
- WEC Alkamel V2 Cloud - you can use this protocol in WEC or ELMS. It will use the cloud connection. You will have to fill your credentials. You can add filters for WEC.
- ELMS Alkamel V2 - you can use this protocol in WEC or ELMS. You will have to fill your credentials. You can add filters for ELMS.

## Track Limits Warning​

Track Limits Warning are sent in the feed in WEC and ELMS. It will be displayed in the main scoreboard, the car scoreboard, the driver scoreboard and the Track Limit Warning display. You can find specific help file here [https://help.hhtiming.com/displays/track-limits-warning].

## Troubleshooting​

If you can't connect, it may come from a network problem, from wrong credentials or because you reached the maximum number of connections.

### Network problem​

To check that your network configuration is correct:

- Open a command prompt and type "If you get a response like :Reply from 192.168.74.12: bytes=32 time=3ms TTL=64, your network configuration is correct and you should contact Alkamel to see if they activated the feed for your team.
- Otherwise type "If you get a response like :Reply from 192.168.74.12: bytes=32 time=3ms TTL=64, you have a DNS issue. Please check your setup with your IT department.
- Otherwise, please check your network setup with your IT department.

### Wrong credentials (V2 Protocol)​

Please ask Alkamel to confirm that you are using the right credentials to connect to the feed.

Additional sectors
On each track, there are more timing loops that you can use to create custom sectors.

For example at Spa, there are 7 loops, FL, SCL2, IP1, PL1, IP2, PL2 and SCL1. You can create a sector from FL to SCL2 for example by adding it to the additional options of the championship configuration before connecting:

![](https://help.hhtiming.com/assets/images/wec_1-be8c6e14a1583da0ad445214663074a8.png)

You can choose the name you want but the value should always be: Loop1;Loop2

You can only define additional sectors on a computer directly connected to Alkamel V2 Protocol  (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

## Micro-Sectors​

Micro-Sectors [https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/#microsectors---using-micro-sectors-as-main-sectors] are available in WEC and ELMS using Alkamel v2 feed.

### ELMS List of Micro-Sectors Per Track​

#### List of loops per track​

#### Barcelona: FL, VMAX2, SCL2, IP1, IP2, SCL1​

![](https://help.hhtiming.com/assets/images/elms_5-e5d0632c3be99039aada700e1cf00d17.png)

#### Imola: FL, SCL2, IP1, IP2, SCL1​

![](https://help.hhtiming.com/assets/images/elms_2-e908c339e1468b1535efd406da8c291f.png)

#### Paul Ricard : FL, SCL2, IP1, IP2, SCL1​

![](https://help.hhtiming.com/assets/images/elms_3-352402adaec4043f8821e858556bb163.png)

#### Portimão: FL, SCL2, IP1, IP2, SCL1​

![](https://help.hhtiming.com/assets/images/elms_4-86d944dc9f1975de9bbd4a11e1701849.png)

#### Silverstone: FL, SCL2, IP1, IP2, SCL1​

![](https://help.hhtiming.com/assets/images/elms_6-b5274c62ec92052ad964f9bbba0693f2.png)

#### Spa: FL, SCL2, PL1, IP1, IP2, SCL1​

![](https://help.hhtiming.com/assets/images/elms_1-44a9d79a110043b5afe450c43f0ddac2.png)

These timing loops can be used to create custom sectors, in the additional options of the championship configuration before connecting. Here is the list of micro-sectors per track for the ELMS championship:

 | Track | Micro-sectors
| Barcelona | FL,VMAX2;VMAX2,SCL2;SCL2,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
| Imola | FL,SCL2;SCL2,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
| Paul Ricard | FL,SCL2;SCL2,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
| Portimão | FL,SCL2;SCL2,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
| Silverstone | FL,SCL2;SCL2,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
| Spa | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,IP2;IP2,SCL1;SCL1,FL
You can choose the name you want but the value should always be: Loop1;Loop2

You can only define additional sectors on a computer directly connected to Alkamel V2 Protocol (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

### WEC List of Micro-Sectors Per Track​

#### List of loops per track​

#### Bahrain: FL, SCL2, PL1, IP1, PL2, IP2, PL3, SCL1​

![](https://help.hhtiming.com/assets/images/wec_2-cb649f2295cb3a504b4db54070764c9a.png)

#### Barcelona: FL,SCL2,PL1,IP1,PL2,PL3,PL4,IP2,PL5,SCL1​

![](https://help.hhtiming.com/assets/images/wec_11-c0615cedfee3e22f31e18a5643e5293c.png)

#### COTA: FL,SCL2,IP1,PL1,PL2,IP2,PL3,PL4,PL5,SCL1​

![](https://help.hhtiming.com/assets/images/wec_3-ff7896ada7168d7362a2ccd6393fcbba.png)

#### Fuji: FL,SCL2,PL1,IP1,PL2,PL3,IP2,PL4,PL5,SCL1​

![](https://help.hhtiming.com/assets/images/wec_4-7f5b59b1dcfaa7dc1de653c9bbbc25fe.png)

#### Imola: FL,SCL2,PL1,IP1,PL2,PL3,IP2,PL4,PL5,SCL1​

![](https://help.hhtiming.com/assets/images/wec_5-8f1cef3e0855eef2a136e1e5a67c2354.png)

#### Le Mans: FL,SCL2,Z4,IP1,Z12,SCLC,A7-1,IP2,A8-1,SCLB,PORIN,POROUT,SCL1,FORDOUT​

![](https://help.hhtiming.com/assets/images/wec_10-4c2804417fe88a9fb06562699fbcd444.png)

#### Losail: FL, SCL2, PL1, IP1, PL2, IP2, PL3, SCL1​

![](https://help.hhtiming.com/assets/images/wec_6-608fcc50d96f77528c785141357244e5.png)

#### Monza: FL,SCL2,PL1,IP1,PL2,PL3,IP2,PL4,PL5,SCL1​

![](https://help.hhtiming.com/assets/images/wec_12-7f636265826e14792f7d6b394411a1b8.png)

#### São Paulo: FL,VMAX2,PL1,SCL2,IP1,PL2,PL3,PL4,IP2,PL5,SCL1​

![](https://help.hhtiming.com/assets/images/wec_7-ab9e2c6f02997369bc01cfe193833339.png)

#### Spa: FL, SCL2, PL1, IP1, PL2, PL3, PL4, IP2, PL5, SCL1​

![](https://help.hhtiming.com/assets/images/wec_8-a4203d5aebca9f6b105a194b68699c82.png)

These timing loops can be used to create custom sectors, in the additional options of the championship configuration before connecting. Here is the list of micro-sectors per track for the WEC championship:

 | Track | Micro-sectors
| Bahrain | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,IP2;IP2,PL3;PL3,SCL1;SCL1,FL
| Barcelona | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,PL3;PL3,PL4;PL4,IP2;IP2,PL5;PL5,SCL1;SCL1,FL
| COTA | FL,SCL2;SCL2,IP1;IP1,PL1;PL1,PL2;PL2,IP2;IP2,PL3;PL3,PL4;PL4,PL5;PL5,SCL1;SCL1,FL
| Fuji | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,PL3;PL3,IP2;IP2,PL4;PL4,PL5;PL5,SCL1;SCL1,FL
| Imola | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,PL3;PL3,IP2;IP2,PL4;PL4,PL5;PL5,SCL1;SCL1,FL
| Le Mans | FL,SCL2;SCL2,Z4;Z4,IP1;IP1,Z12;Z12,SCLC;SCLC,A7-1;A7-1,IP2;IP2,A8-1;A8-1,SCLB;SCLB,PORIN;PORIN,POROUT;POROUT,SCL1;SCL1,FORDOUT;FORDOUT,FL
| Losail | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,IP2;IP2,PL3;PL3,SCL1;SCL1,FL
| Monza | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,PL3;PL3,IP2;IP2,PL4;PL4,PL5;PL5,SCL1;SCL1,FL
| São Paulo | FL,VMAX2;VMAX2,PL1;PL1,SCL2;SCL2,IP1;IP1,PL2;PL2,PL3;PL3,PL4;PL4,IP2;IP2,PL5;PL5,SCL1;SCL1,FL
| Spa | FL,SCL2;SCL2,PL1;PL1,IP1;IP1,PL2;PL2,PL3;PL3,PL4;PL4,IP2;IP2,PL5;PL5,SCL1;SCL1,FL
You can choose the name you want but the value should always be: Loop1;Loop2

You can only define additional sectors on a computer directly connected to Alkamel V2 Protocol (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

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

