---
url: https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/
title: Alkamel V2
slug: timekeeper-specific-info__alkamel-v2
---

# Alkamel V2

-
- Timekeeper specific info
- Alkamel V2

# Alkamel V2

The Al Kamel V2 Protocol is a JSON protocol that Al Kamel introduced in 2017.

## Configuration​

You must obtain a user name and password from Al Kamel to be able to access this data. This information needs to be entered in the “Additional Options” area of the Championship Configuration in HH Timing.

There are 3 options for the GPS field:

- rgps - the real GPS position
- gps - an estimated GPS position
- no - if you don't want to use GPS
For the Record GPS field, select:

- true - if you want to save all GPS messages in the replay.
- false - if you don't want to save them.

![](https://help.hhtiming.com/assets/images/aksv2_1-dab89119570409e851e25b19a198f1c9.png)

### Host​

 |  |
| FIA WEC, ELMS, FE On-Track | timing-data.aks
| FIA WEC On-Cloud | fiawec.datapublisher.alkamelcloud.com
| IMSA On-Track | timing-data.aks
| IMSA On-Cloud | imsa.datapublisher.alkamelcloud.com
caution
For IMSA, please select the Al Kamel V2 North America protocol. This handles the FCY period as S/C.

### Read History​

You can now get the full history since the beginning of the session by adding an option "Read History" in the Additional Options.

![](https://help.hhtiming.com/assets/images/aksv2_2-deec8b00b261d93c9bf374b0f7abeb29.png)

As it will read the history of all completed laps, you might lose some information, like sectors or pit stops.

### Additional loops (Specific championships)​

In some championships, Al Kamel provides some additional loops that are not shown by default in HH Timing.

Users can define their own sectors using the timing loops provided by Al Kamel.  As can be seen in the following screenshot, these sectors are defined in the “Additional Options” grid.  The sector name (chosen by the user) is defined in the first column, and the second column defines the start and end timing loops for the sector, separated by a semi-column ";" character (example: S9-1;A11-1 will give you the time between these two lines).

A custom sector can also be defined by the addition of several sub-sectors using the following syntax: StartLine1;EndLine1;StartLine2;EndLine2;StartLine3;EndLine3 ...etc. In that case you can easily sum non-consecutive sectors.

[内嵌示意图]

Choose any name, but always set the value to `Loop1;Loop2`.

Important

- The name of any of the additional sectors can not be the same as any of the sectors or speed traps in the main feed which are: S1, S2, S3, Speed1 (and PORSCHE, FORD, T6, T7 before 2025).
- If you make a change to the definition of the custom sectors, for these to be shown in the software the data needs to be re-processed.
- Graphs that are made that include custom sector data may need to be remade if the custom sector definition is changed.
- If CONNECTED LIVE: You will need to disconnect, replay the session you were just connected to, re-connect to the live session (do not clear scoreboard). The data that was sent while you were disconnected will not be recorded by the software. For this reason it is better to stay connected to the live session and only replay to re-process the data once the session finishes if you do not need this additional data during the session.
- If NOT CONNECTED LIVE: Just replay the session with the new sectors definition active and the new sectors will appear.
- You can only define additional sectors on a computer directly connected to Alkamel V2 Protocol (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

### Speed Traps for Custom Sectors​

HH Timing can create speed traps for any of the custom sectors that are defined in the  championship configuration. A third argument can be entered after the START and END loops that define the custom sector, which is the distance between the timing loops separated by a semi-colon. An example is shown below in the hypothetical case that custom sector AA4 has 30.7 meters between the two timing loops that define it.

![](https://help.hhtiming.com/assets/images/aksv2_14-e56aca0b29c94274c81a8c0d1697e335.png)

### Microsectors - Using Micro Sectors as main Sectors​

The use of microsectors is optional, but when available from the timing feed, they need to be entered in pairs as a semicolon/comma-separated list (and sectors will be named MS1, MS2, ..., MSx), or in a triplet with name,entry,exit. It will improve the data precision and allow for more accurate gaps on live crossing order, or gap track map, and a more precise ghost cars calculation.

As an example, Slow Zones can be created as Micro Sectors in Le Mans using the timing lines from the feed:

- FL to Z4
- Z4 to IP1
- IP1 to Z12
- Z12 to A7-1
- A7-1 to A8-1
- A8-1 to SCLB
- SCLB to PORIN
- PORIN to POROUT
- POROUT to FL
The microsector string would be: `SZ1,FL,Z4;SZ2,Z4,IP1;SZ3,IP1,Z12;SZ4,Z12,A7-1;SZ5,A7-1,A8-1;SZ6,A8-1,SCLB;SZ7,SCLB,PORIN;SZ8,PORIN,POROUT;SZ9,POROUT,FL`

Checking with the timekeeper for the availability of timing lines for the event is necessary, as the names of loops can change over time.

#### Auto-Generated Micro Sectors​

Instead of specifying loop pairs manually, set the `Micro Sectors` value to `auto-generated`. All available timing loops from the live feed (ordered by their index as provided by Al Kamel) are used to automatically create consecutive micro sectors MS1, MS2, ... for the current track, with the last sector wrapping back to the first loop.

 | Name | Value
| Use Micro Sectors As Main Sectors | true
| Micro Sectors | auto-generated
note
This works across all tracks without requiring manual updates when the loop list changes.

The option "Use Micro Sectors As Main Sectors" should be set to true to utilize them.

 | Micro Sectors | SZ1,FL,Z4;SZ2,Z4,IP1;SZ3,IP1,Z12;SZ4,Z12,A7-1;SZ5,A7-1,A8-1;SZ6,A8-1,SCLB;SZ7,SCLB,PORIN;SZ8,PORIN,POROUT;SZ9,POROUT,FL
| Use Micro Sectors As Main Sectors | true
To ensure full functionality — including features such as ghost cars — the dedicated Track Map must be used.

![](https://help.hhtiming.com/assets/images/aksv2_7-43fd9549a80b25b37f979ad26e82ebd9.png)

![](https://help.hhtiming.com/assets/images/aksv2_9-ac0b51fea4ef7214daa14e814671f75e.png)

Live Excel Export

### Live Excel Export​

- If Use Micro Sectors As Main Sectors is set to true (example with 9 micro sectors):Standard sectors S1 to S9 will correspond to your new main sectors so SZ1 to SZ9. ![](https://help.hhtiming.com/assets/images/aksv2_11-35189e4fd7a26f4527ea6a6be62a885c.png)
- It is required to define the Number of Non-Track Sectors in the backstage option (e.g., 3):
- ![](https://help.hhtiming.com/assets/images/aksv2_10-5641eca752c6c49e6dc514b857f2a3c3.png) Then, NTS1 to NTS3 will correspond to the original S1 to S3.
- ![](https://help.hhtiming.com/assets/images/aksv2_12-1043188009ad53e9c59eff66c91dca88.png)

- If Use Micro Sectors As Main Sectors is not set or set to false:Standard sectors remain named S1 to S3.
- All non-track sectors, including slow zones, will appear as NTS entries (e.g., NTS1, NTS2, ...).

## GPS track map (specific championships)​

For the software to render the cars on the main track map by GPS data rather than the normal interpolation method this must be specified in the main track map ribbon bar control as shown below.

![](https://help.hhtiming.com/assets/images/aksv2_4-f7ffd02c3a7393bb8833c10da4e39f7d.png)

note

- The GPS data used to render the cars on the main track map is always available to the software when connected to the Premium protocol. No cars/classes need to be specified in the Additional Options.
- Track map highlighting such as ghost cars can't be displayed on a GPS based map. To display ghost cars, the user needs to revert to the traditional non-GPS track map by un-checking the check box.

## GPS speed and driving line​

The control to display the GPS Speed and the driving line can be accessed from the Ribbon Bar. Click on  Display and then on GPS Speed:

![](https://help.hhtiming.com/assets/images/aksv2_5-a6a5ca78caba70f46e82fc04ad97ded6.png)

Laps can be selected to be displayed by using the Add Live Follow or Add Laps buttons.

![](https://help.hhtiming.com/assets/images/aksv2_6-d085e27bb441ca3de47ec7497313d244.png)

## Lap deletion and ranking​

The software automatically monitors track limit violations to manage best lap times and ranking. When a lap is marked as invalid:

- The lap is highlighted in the car scoreboard [https://help.hhtiming.com/displays/track-limits-warning/#car-scoreboard].
- The best lap time is removed and the ranking is updated accordingly.
danger
If the "invalid" status message from Al Kamel is missing or delayed, the software cannot delete the lap automatically. This may result in an incorrect ranking during practice or qualifying sessions.

### Scoreboard construction logic​

HH Timing builds its own scoreboard internally rather than relying on the timing provider ranking feed. This approach prioritizes race session accuracy and data integrity:

- Data Integrity: Building the scoreboard internally ensures that lap numbers and elapsed times remain correct even in the event of a total timing feed failure.
- Historical Reliability: Past sessions have shown inconsistencies in some timing provider ranking feed. By calculating the rank internally, the software maintains a consistent state regardless of external feed behavior.
info
The internal calculation provides the most robust balance for endurance racing. While this ensures the integrity of the lap counter, specific session rankings (particularly in qualifying) may occasionally show minor differences compared to the official feed.

### Using feed-based data​

To match the "official" TV ranking or the provider's specific qualifying logic, use the feed-specific columns in the Main Scoreboard.

Add the following columns to view the raw provider data:

- P (Feed) / PIC (Feed): Position and Position in Class according to the feed.
- Gap (Feed) / Gap Class (Feed): Gaps according to the feed.
- Best (Feed): The best lap time as recorded by the provider.
These columns allow for a direct comparison between the HH Timing internal calculation and the timing provider's ranking.

![](https://help.hhtiming.com/assets/images/aksv2_13-73d9a048ecf0c91407c876b88a91987e.png)

## Session Filtering​

Please note that from 2026, Al Kamel is filtering the sessions based on credentials.

A team that has purchased access to the feed will not see any session name as long as the sessions from the championship it is participating in are not sent in the feed.

note
Example : An ELMS team will only see the ELMS sessions when active. During support series sessions, only the green dot at the bottom left of HH Timing will still appear, without any session name

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

