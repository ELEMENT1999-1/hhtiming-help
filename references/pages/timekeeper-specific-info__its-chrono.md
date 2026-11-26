---
url: https://help.hhtiming.com/timekeeper-specific-info/its-chrono/
title: ITS Chrono
slug: timekeeper-specific-info__its-chrono
---

# ITS Chrono

-
- Timekeeper specific info
- ITS Chrono

# ITS Chrono

## Series Using ITS CHRONO​

- Macau GP
- Ultimate Cup Series
- French GT4
- EWC

## Live Data Connection​

Access to the timing feed is via the internet, tethering from a mobile phone connection is generally fine if circuit internet is not available.

You will need to make a new championship configuration [https://help.hhtiming.com/settings-options/championship-configuration] and select the ITS Protocol as shown below.

[内嵌示意图]

Unless advised otherwise by ITS the host should be set to: https://api-live.its-live.net/v1/DataFeed

The ApiKey and event specific information should be requested directly to ITS for each event. The contact person for ITS is Sebastien Mascret.

The SessionId should be set "auto" to connect to the live session. For each event, each session is represented by a number. It is also possible to enter directly the SessionId of a specific session to retrieve the data for this specific session. The SessionId will be available close to the event once the structure of the event is created by ITS.

### How to find ChampionshipId, SeasonId and EventId​

- Go to https://www.its-live.net/home
- Open your championship (for example EWC):

![](https://help.hhtiming.com/assets/images/its_2-cdcef46380cf5ddf5da4a5e3310a3cd4.png)

- If needed, change season:

![](https://help.hhtiming.com/assets/images/its_3-5f0eaa5c33ce9ee3208d62856a6cec76.png)

- Open the event:

![](https://help.hhtiming.com/assets/images/its_4-4768ad2dde6c872400a5675cbce13c08.png)

- Look at the URL:

![](https://help.hhtiming.com/assets/images/its_5-2ca769ecffa140bacb7bd866d4caa660.png)

- The ChampionshipId is the first block after its-live.net/live Here it is ewc.
- The seasionId is the second block after its-live.net/live. Here it is 2019-20.
- The EventId is the third block after its-live.net/live. Here it is 24hmotos.

![](https://help.hhtiming.com/assets/images/its_6-596e14fcfcadac6069b77db105ed69f5.png)

caution
Be Careful, all fields are case sensitive!

Once this is complete you can click the connect button [https://help.hhtiming.com/getting-started/ribbon-bar/data].

## Post session analysis​

You can import xls file from its-results.com website.

- Select the event

![](https://help.hhtiming.com/assets/images/its_7-e5f95777c7a40e5e2a4367f6f2e1d72a.png)

- Download lap by lap ranking xls file

![](https://help.hhtiming.com/assets/images/its_8-5e3692f2695cad9998a7c8a5870f68cc.png)

- Open the file to get the worksheet name and close it.

![](https://help.hhtiming.com/assets/images/its_9-afdba41581284acd65d01eab523e3251.png)

- In Data > Import T&S, select ITS XLS Import as file format, select your file and enter the worksheet name find at step 3.

![](https://help.hhtiming.com/assets/images/its_10-9af61a1c6200b1eb71230bfb634d8986.png)

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
- Timekeeper specific info — https://help.hhtiming.com/timekeeper-specific-info/natsoft/
- Swiss timing — https://help.hhtiming.com/timekeeper-specific-info/swiss-timing/
- Time service — https://help.hhtiming.com/timekeeper-specific-info/time-service/
- TSL Timing — https://help.hhtiming.com/timekeeper-specific-info/tsl-timing/
- ITS Chrono — https://help.hhtiming.com/timekeeper-specific-info/its-chrono/
- Alkamel V2 — https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/
- Alkamel standard — https://help.hhtiming.com/timekeeper-specific-info/aklamel-standard/
- USAC Timing — https://help.hhtiming.com/timekeeper-specific-info/usac/
- Perugia Timing — https://help.hhtiming.com/timekeeper-specific-info/perugia-timing/
- MyLaps X2 Server — https://help.hhtiming.com/timekeeper-specific-info/MyLaps-X2/
- MyLaps HTML Scraping - Speedhive — https://help.hhtiming.com/timekeeper-specific-info/MyLaps-SpeedHive/
- Cronococa Enhanced RMon Timing — https://help.hhtiming.com/timekeeper-specific-info/Cronococa/
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/
- new championship configuration — https://help.hhtiming.com/settings-options/championship-configuration
- connect button — https://help.hhtiming.com/getting-started/ribbon-bar/data

