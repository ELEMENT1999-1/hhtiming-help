---
url: https://help.hhtiming.com/timekeeper-specific-info/usac/
title: USAC Timing
slug: timekeeper-specific-info__usac
---

# USAC Timing

-
- Timekeeper specific info
- USAC Timing

# USAC Timing

USAC provides timing using two different protocols, both accessible by any computer with an internet connection:

- Websocket
- Multiloop
Websocket
The Websocket protocol has some improved features over the multiloop protocol:

- Driver name - Driver names are sometimes not available on the multiloop protocol.
- GPS position - The Websocket feed provides the car's GPS position
We suggest the use of the Websocket protocol.

## Contact​

The contact person for USAC Timing is Wes Ratcliff. You can contact him at srotiming@usacnation.com

## Live connection​

### Websocket​

#### Championship configuration​

 |  |
| Protocol | USAC Web Socket Timing Protocol
| URL | DEPENDS OF THE CHAMPIONSHIP. CAN BE CHECKED ON https://github.com/usacnation/usac-mlp/blob/main/README.md#naming-conventions
Example (SRO America):

[内嵌示意图]

#### GPS Position​

The feed transmits the car's position at a rate of 1Hz, allowing better positioning of the cars in the track map.

To use this feature make sure you enable the GPS car position mode in the track map display.

[内嵌示意图]

Speed
Because of the low rate of GPS data, the speed of the car can't be calculated. Car off track display [https://help.hhtiming.com/displays/car-off-track/#for-timing-feed-without-gps-data] can't be used in GPS mode and should be use in regular extrapolated mode.

### Multiloop​

#### Championship configuration​

 |  |
| Protocol | USAC Multiloop Timing Protocol
| Host | timing.usacnation.com
| Port | DEPENDS OF THE CHAMPIONSHIP. CAN BE CHECKED ON https://github.com/usacnation/usac-mlp/blob/main/README.md#naming-conventions
Example (SRO America):

[内嵌示意图]

### Additional options​

#### add class to name​

Non-official tests
This option should be set at true during non official tests. There are usually cars with the same race number but in different class. Without this option the scoreboard and ranking in HH Timing could be wrong for those cars.
For official sessions, this option should be set back to false.

A different HH Timing project could be used to keep a clean entrylist between non-official and official sessions.

[内嵌示意图]

With the option set to true, the car number in HH Timing is a concatenation of CarNumber-ClassName:

![](https://help.hhtiming.com/assets/images/usac_4-6ff715138c81755986ccbf4be0f8c63b.png)

DMI
For HHDM users, if the option is set to true while using the DMI, it is important to set the HH Timing Car ID column to the concatenation of CarNumber-ClassName

![](https://help.hhtiming.com/assets/images/usac_5-3a235e938e5df273e9204050c79814d1.png)

#### Time zone delta​

The Time zone delta option is used to correct the time of day of race control messages.

The value is expressed in hours and a positive value increases the time of day displayed in the race control messages display.

[内嵌示意图]

## Post session csv data import​

Post session csv files can be imported by using the Import T&S Data option [https://help.hhtiming.com/timing-data-management/timing-scoring-data-import/].

 |  |
| File format | USAC CSV Import

[内嵌示意图]

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
- Import T&S Data option — https://help.hhtiming.com/timing-data-management/timing-scoring-data-import/

