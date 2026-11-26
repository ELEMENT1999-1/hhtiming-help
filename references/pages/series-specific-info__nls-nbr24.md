---
url: https://help.hhtiming.com/series-specific-info/nls-nbr24/
title: NLS & N24
slug: series-specific-info__nls-nbr24
---

# NLS & N24

-
- Series specific information
- NLS & N24

# NLS & N24

## Connection information​

There are three options to connect to the official timing feed from WIGE during NLS race and N24:

- Wige 1 Sector - this is left over from past seasons when there were no sector times provided for the NLS races
- Wige 5 Sector - this protocol will allow you to see the 5 sector times that are currently available over the timing stream. This is usually used during regular NLS races.
- Wige 9 Sector - this protocol will allow you to see the 9 sector times that are currently available over the timing stream. This is usually used for the Qualy race and N24.

### Connection details​

 |  |
| Host | 192.168.11.233
| Port | 80

[内嵌示意图]

For this stream there are some Additional Options available to handle some specifics in the WIGE protocol:

- Session Start Time - this field is optional and is used to define the session start time, that is used to calculate the session elapsed time each time a car completes a lap. It should be entered in the format HH:mm:ss.ddd. The session time is calculated by subtracting the session start time from the current time of day. If the field is left blank then the value will be taken automatically: 1) sometimes Wige defines a start time in the timing feed, or if this is missing then 2) the value is taken from when the “Connect” button is pressed
- Allow GP Laps - this value can be set to “true” or “false”. When it is set to true, the software will create a new lap each time the car crosses the S/F line whether the lap is a full Nordschleife lap or a GP lap. When the value is set to false, a GP lap will not be counted as a full lap. This value should be set to false for the race.
- Calculate Start Time - this value can be set to “true” or “false”. If set to "true" HH Timing will use the timing information following the first lap of the race to calculate accurately the start time. If used, the user shouldn't have to re-enter the exact stat time. While using this option it is important to still enter a Session Start Time close to the official start time. This value should be set to false for timed session.

#### Example configuration​

- for a qualifying session starting at 9:00AM: ![](https://help.hhtiming.com/assets/images/nls_2-bcf021587bfb69a6ee9beae1f37ce605.png)
- for a race starting at 12PM ![](https://help.hhtiming.com/assets/images/nls_3-a02c051e1016b1244c9a0ee24af0c5b7.png)
Multiple championship configuration
One suggestion to avoid any mistake is to create prior to the event two different championship configurations with the correct settings for the Qualy and the Race and to activate the correct one prior to the session:

![](https://help.hhtiming.com/assets/images/nls_4-7fa34753f2dad683ba0e07837bf91c82.png)

#### Update Session Start Time​

Before the race it is not possible to know the exact time that the race will start and so this can be updated during the session.  On the ribbon bar select the “Set Session Start Time” button:

![](https://help.hhtiming.com/assets/images/nls_5-143a17a9b84247dea4c5bf8962fd4511.png)

In the window that opens enter the updated start time of the session and press OK.

![](https://help.hhtiming.com/assets/images/nls_6-222e374ab348eaa58e64bb5a62ee6e8a.png)

Please note that this does not update any historical data but will correct the data moving forwards.

## NLS Stop Times​

For each race, don't forget to select the correct NLS Stop Times File. A new file will be added only if the stop times are different from the previous race.
We are getting the stop times from this website.

![](https://help.hhtiming.com/assets/images/NLSStopTimes-788174167e931c6a79c063dc7832067f.png)

These values are used for the Race Finish Calculations if you are using VLN Rules as Pit Stop Time Mode [https://help.hhtiming.com/series-specific-info/nls-nbr24/#strategy-overview].

## Multi Session Scoreboard​

The Multi Session Scoreboard can be used to handle qualifying sessions that are split into different sessions in the timing feed, but are considered as one for determining the grid positions.

On the Displays tab of the ribbon bar under Other Scoreboards you can access the Multi Session Scoreboard:

![](https://help.hhtiming.com/assets/images/nls_7-0c232248298eb1034c43438bfe732f01.png)

After opening the scoreboard on the ribbon bar you can use the Select Sessions button to open a window that will enable you to import other sessions into the scoreboard:

![](https://help.hhtiming.com/assets/images/nls_8-6915d2624ddd991bbb12dea99627b3c2.png)

The scoreboard will then import the best lap times from the other sessions.

![](https://help.hhtiming.com/assets/images/nls_9-e7fb583eedeaafa99fc9cb21bd8387b0.png)

The available columns are:

- P and PIC will remain blank
- Best Lap Time: the best lap time from any of the sessions
- Best Lap Time This Session: the best lap time from the currently “Active” session
- Best Session: will show “OTHER” or “THIS” to indicate if the car has set their best time in the currently active session

## Combined Sessions​

From 2022 there is the ability to combine qualifying sessions to have the same result in HH Timing compare to Wige TV feed.

- Add an option in the championship config with Session ID and define a name for the session. This needs to be done for qualifying 1. ![](https://help.hhtiming.com/assets/images/nls_10-4e87959fbf554711fd5e9a3213b3cb79.png)
- Before qualifying 2, if you closed HH Timing between Q1 and Q2 or activate another session you need to replay or recover Q1. [内嵌示意图]
- Keep the same championship config without changing the session start time.
- Connect to the feed for Qualifying 2 without clearing the scoreboard. [内嵌示意图]
Data of Q2 will be added to the Q1.

![](https://help.hhtiming.com/assets/images/nls_13-4c30e7aa614c50b4ba81c771729553ae.png)

Same Steps will need to be done between Q2 and Q3 but the session to recover will be the combined Q1-Q2 session.

Due to the time table with Q3 will be the next day of Q1 and Q2 with a start time between Q1 and Q2 start time, the elapsed time in a Q1-Q2-Q3 combined session will be weird.

![](https://help.hhtiming.com/assets/images/nls_14-91764054aed7a0d5b69567629526f60d.png)

This will missed up the graph using elapsed times.

You can download an example of championship config here.

## NLS Plugin​

Version
A plugin is available for HH Timing with NLS specific features.

You can download it on hh-dev.com, in the Plugin section:

[内嵌示意图]

![](https://help.hhtiming.com/assets/images/nls_16-ad07219db854c32a00d7a9c1fc8ea152.png)

If it does not show on your account, please email us.

The plugin is available as a .zip file and it should be placed directly in Documents\HH Timing\Plugins.  Once the software is launched with the .zip file in the correct location a new tab will appear on the ribbon bar:

![](https://help.hhtiming.com/assets/images/nls_17-c2b2c3c981f740b09c97136214211c81.png)

The only display available in the plugin at the moment is the NLS Pit Stop Scoreboard that displays the minimum pit stop time required by each car as outlined in Appendix 6.1 of the NBR 24H regulations.  Please note that currently Appendix 6.2 is not implemented in the software for cars in the SP10 category.  Please contact us if you want this to be implemented.

![](https://help.hhtiming.com/assets/images/nls_18-30f519a83c0aa6c2fdc501287dab9455.png)

When the car is in the first stint the time from column A of table 1 will be shown.  If less than 70 minutes remains in the race then the information from table 2 will be shown.  Please note that the algorithm based on our understanding of the regulations is that the time remaining is always rounded down.  For example, if there are 69.5 minutes left in the race, then the time for 69 minutes will be shown.  At any other time column B of table 1 will be used.

The only setting required for the scoreboard is that the session length should be set correctly in the backstage options so that the final pit stop time is applied at the correct time.

![](https://help.hhtiming.com/assets/images/nls_19-8d56594caede3e3c65ddda710b34de84.png)

## Strategy Overview​

For the strategy overview to take into account the Nurburgring pit stop rules in its race prediction calculation, the Pit Stop time mode needs to be set to “VLN Rules”.

![](https://help.hhtiming.com/assets/images/nls_20-e12baeff047f21550d9373b2671205b7.png)

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

