---
url: https://help.hhtiming.com/displays/track-limits-warning/
title: Track Limits Warning
slug: displays__track-limits-warning
---

# Track Limits Warning

-
- Displays [https://help.hhtiming.com/displays/]
- Track Limits Warning

# Track Limits Warning

The Track Limits Warning display will show you all track limits that happened in the session.

Specific series only
The Track Limits message need to be sent in the protocol and the championship. Currently we are receiving the information in:

- Asian Le Mans Series, ELMS and WEC (Alkamel v2 Protocol)
- GT World Challenge Europe (Swiss Timing Protocol)
- Supercars (Natsoft XML Protocol)

In this display you will see the car number, the session time, the time of day (you will need to use the offset in the ribbon if the offset isn't sent in the feed), the lap number and the location.

danger

- The lap number isn't send in the feed so we are using the session time to find it. If you missed some laps, it could be wrong.
- If a TLW is cancelled, we don't receive the information so it will be still displayed in HH Timing, and count in the TLW counter.

## Ribbon Options​

[内嵌示意图]

The Reference Car field is the list of Reference Cars separated by a comma.
Flash For has different value: All, Reference and None to flash for 15s when a new Track Limits Message is received for All cars, only for Reference Cars or to do not flash.
The offset value will be added to the Time Of Day in the scoreboard.

## Scoreboard​

![](https://help.hhtiming.com/assets/images/track_limits_warning_6-e3a0a0cb5e39440442f436decc50bd1e.png)

In This example, car 87 is highlighted as it is in the Reference Cars list,  and is flashing for the Track Limits done at 13:28:04.

## Track Limits Warning in other scoreboard​

We calculate the number of Track Limits Warning as it isn't sent in the feed. You can find this information in two scoreboards (column name: \#TLW):

### Main Scoreboard​

In this scoreboard you will find the total number of Track Limit Warnings for each car.

![](https://help.hhtiming.com/assets/images/track_limits_warning_2-309caa3016125974d4602798a9558a45.png)

### Driver Scoreboard​

In this scoreboard you will find the total number of Track Limit Warnings for each driver.

![](https://help.hhtiming.com/assets/images/track_limits_warning_3-641919bd4e8a401a224019084bad1793.png)

### Car Scoreboard​

In the car scoreboard, you can add a column TrackLimits to see if the lap has been invalided due to track limits.

![](https://help.hhtiming.com/assets/images/track_limits_warning_4-6f4559db1f913e30ddcded2fb5957004.png)

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- Workbooks & layouts — https://help.hhtiming.com/workbooks-layouts/
- Displays — https://help.hhtiming.com/displays/
- Filtering displays — https://help.hhtiming.com/displays/filtering-displays/
- Clocks — https://help.hhtiming.com/displays/clocks/
- Graphing — https://help.hhtiming.com/displays/graphing/scatter/
- Overviews — https://help.hhtiming.com/displays/overviews/
- Scoreboards — https://help.hhtiming.com/displays/scoreboards/
- Track maps — https://help.hhtiming.com/displays/track-maps/
- Car off track — https://help.hhtiming.com/displays/car-off-track/
- Track Limits Warning — https://help.hhtiming.com/displays/track-limits-warning/
- Race Control Messages — https://help.hhtiming.com/displays/race-control-messages/
- Pit Light Display — https://help.hhtiming.com/displays/pit-lights/
- Track gap display — https://help.hhtiming.com/displays/track-gap-display/
- Connection Status — https://help.hhtiming.com/displays/connection-status/
- Timing data management — https://help.hhtiming.com/timing-data-management/session-data/
- Settings & options — https://help.hhtiming.com/settings-options/backstage-settings/
- Excel exports — https://help.hhtiming.com/excel-exports/live-excel-export/
- Reporting — https://help.hhtiming.com/reporting/
- Series specific information — https://help.hhtiming.com/series-specific-info/imsa/
- Timekeeper specific info — https://help.hhtiming.com/timekeeper-specific-info/natsoft/
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/

