---
url: https://help.hhtiming.com/timekeeper-specific-info/MyLaps-X2/
title: MyLaps X2 Server
slug: timekeeper-specific-info__MyLaps-X2
---

# MyLaps X2 Server

-
- Timekeeper specific info
- MyLaps X2 Server

# MyLaps X2 Server

This protocol is used mainly at tests where no official timing is provided.
HH Development distributes a stand alone application that connects to the server and transforms the loops crossing information into messages that are interpreted by HH Timing.
The application can be downloaded from here:

## Operation​

The tool is divided into three main sections:

### Settings​

This section mananges all the information required to process the loop crossings

![](https://help.hhtiming.com/assets/images/mylaps_settings-e9a8043335a8103899c4d1e0cb9ec752.png)

#### Cars:​

Enter the basic information of the car (number, category, manufacturer) and the transponder id.
There is not limit in the amount of cars in the configuration.

#### SF Lines:​

List the name of the Start/Finish loops (both on track and in pits).

#### In Pits SF Lines:​

List the name of the Start/Finish loops located in the pit lane. If no dedicated SF loop is available in the pit lane, the Pit In line can be used instead.

#### Pit In Lines:​

List the name of the pit entry loops.

#### Pit Out Lines:​

List the name of the pit exit loops.

#### Sectors:​

List the track sectors. Each sector is defined by an entry timing loop and an exit timing loop.

note
Use the +/- buttons on top of each section to add or remove items

### Timing​

In this section, all the information required to connect to the X2 server is defined.

![](https://help.hhtiming.com/assets/images/mylaps_timing-765f96e9d45f0bb02544ea6ba1384c86.png)

#### X2 Server:​

##### Host:​

Network Address of the X2 Server

##### User Name and Password:​

Login credentials for the X2 Server

#### Timing:​

##### Session Start Time:​

Date and time of the start of the Session

##### Output Port:​

This is the port that HH Timing will use to connect to the tool. The Server Status field below indicates whether the port was successfully acquired at startup.

##### Server Status:​

Indicates whether the processing server started successfully on the configured Output Port. If the status shows Failed to start, the port is already in use by another process — change the Output Port value and restart the application.

#### Session:​

##### Type:​

Sets the session type: Practice or Race. This is used to correctly interpret the timing data received from the X2 server and send it in the correct format to HH Timing clients.

##### Manual Name:​

Optional name to assign to the session. If set, this name will be used instead of the name received from the X2 server.

##### Skip X2 cars:​

When enabled, cars that are defined in the X2 server but not in the local configuration will be ignored and not forwarded to HH Timing.

### Data​

If the connection is succesful, this section will display the current session information and the history of the loops crossings.

![](https://help.hhtiming.com/assets/images/mylaps_data-f9f4aaa9844cf2ce26b3576f4d2e3069.png)

#### Session:​

##### Name:​

The name of the current session as defined in the Timing Tab.

##### Time:​

Current Elapsed Time (based on Session Start Time + last crossing).

#### Passings:​

List of all loop crossings received since the application started, displayed in chronological order.

## Server Connection​

To connect to the timing server use the buttons in the ribbon bar

[内嵌示意图]

In the bottom left part of the software there is a connection indicator. If the connection it succesful it will turn green

[内嵌示意图]

It the connection fails it will turn red

[内嵌示意图]

## Timing Connection​

To connect to the tool create a championship configuration with HH Timing protocol with the following parameters:

- Host: Network address of the X2 application (localhost if running in the same computer)
- Port: Output Port of the X2 application

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

