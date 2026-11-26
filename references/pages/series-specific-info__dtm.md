---
url: https://help.hhtiming.com/series-specific-info/dtm/
title: DTM
slug: series-specific-info__dtm
---

# DTM

-
- Series specific information
- DTM

# DTM

## Live Data Connection​

You can find more information about how to connect to Swiss Timing FTP Protocol here [https://help.hhtiming.com/timekeeper-specific-info/swiss-timing].

### Championship configuration in HH Timing​

You will need to create a new championship configuration for DTM, with the following information.

 |  |
| Protocol | Swiss Timing FTP
| Host | xml-motorsport.sportresult.com
| Port | 21
| Username | racing-dtm
| Password | !DHX-1Er_guP
An internet-based feed is also available. The delay on this one is more important than on the local feed.

 |  |
| Protocol | Swiss Timing FTP
| Host | 52.233.255.131
| Port | 22
| Username | racing-dtm
| Password | !DHX-1Er_guP
Please note the select FTP Directory feature is only available with the local connection.

You will also need to fill the FTP Directory like explain here [https://help.hhtiming.com/timekeeper-specific-info/swiss-timing/#determining-the-file-path].

A Kafka feed is also available, either locally on the timing network or remotely via the cloud host. See the Swiss Timing Kafka [https://help.hhtiming.com/timekeeper-specific-info/swiss-timing/#kafka-connection] section for general setup. The connection details for DTM are:

Local (timing network at the circuit):

 |  |
| Protocol | Swiss Timing Kafka
| Host | 10.2.40.3
| Port | 9093
Cloud:

 |  |
| Protocol | Swiss Timing Kafka
| Host | evhns-prod-realtime-msp-westeurope.servicebus.windows.net
| Port | 9093
By default, a championship called "Swiss Timing Kafka" is created in all new projects. Double click on it to open it in your workbook and verify the settings above.

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
- here — https://help.hhtiming.com/timekeeper-specific-info/swiss-timing

