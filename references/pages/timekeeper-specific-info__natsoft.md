---
url: https://help.hhtiming.com/timekeeper-specific-info/natsoft/
title: Natsoft
slug: timekeeper-specific-info__natsoft
---

# Natsoft

-
- Timekeeper specific info
- Natsoft

# Natsoft

The Natsoft protocol is used exclusively in Australia. Championships that use Natsoft include:

- Australian Supercars
- Australian GT
- Bathurst round of IGTC
To connect to a live Natsoft feed you will first need to obtain the Host and Port number from the timekeepers and enter into the championship configuration [https://help.hhtiming.com/settings-options/championship-configuration].

To run a replay of Natsoft data, the Host and Port number are not required but you do need to first create the championship [https://help.hhtiming.com/settings-options/championship-configuration].

[内嵌示意图]

## Microsectors​

The use of microsectors is optional but when they are available from the timing feed they need to be entered in pairs as a semicolon/comma separated list.

As an example is there were four microsectors available at a circuit and the timing lines that defined them were:

- Finish Line to Position 1
- Position 1 to Interval 1
- Interval 1 to Position 3
- Position 3 to Finish Line
The microsector string would be:
I3,P1;P1,I1;I1,P3;P3,I3

You should check with the time keeper for which sector lines are available for the event you are taking part in as they are track specific.

tip
The user can decide to use the Micro Sectors as main sectors instead of the regular S1/S2/S3. To do switch the option in the additional options to True

![](https://help.hhtiming.com/assets/images/natsoft_2-2ebd71381285302c51a0301a9c44c303.png)

In addition, the user would need to select the correct map contour:

![](https://help.hhtiming.com/assets/images/natsoft_3-b3f9b26622ad16a7e2413eee7b02124f.png)

## Pit lane configuration​

With the Natsoft protocol, the control line can sometimes be at Pit in or at Pit out. For example at Bathurst it is at Pit In. Also sometimes the same timing line can be used as both the control line and the pit in/out line. There are three parameters in HH Timing that are used to configure this:

- Control Line At Pit Out
- Use Control Line As Pit Out
- Use Control Line As Pit In
It is important to set these parameters correctly in the championship configuration to ensure HH Timing interprets the timing feed correctly:

![](https://help.hhtiming.com/assets/images/natsoft_4-93377816593bb64a191a12e4087f712d.png)

For Supercars, please refer to this table [https://help.hhtiming.com/series-specific-info/supercars/#timing-settings-per-track] for the correct settings for each track.

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
- championship configuration — https://help.hhtiming.com/settings-options/championship-configuration

