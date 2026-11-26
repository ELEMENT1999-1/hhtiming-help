---
url: https://help.hhtiming.com/displays/car-off-track/
title: Car off track
slug: displays__car-off-track
---

# Car off track

-
- Displays [https://help.hhtiming.com/displays/]
- Car off track

# Car off track

The car off track display objective is to detect a slow cars on track. This can be used for safety by being able to inform the driver quickly of a danger or for strategy purpose.

caution
The control is really effective when the GPS data is provided inside the feed. Without, it depends a lot on the length of each sectors to be effective of not.

When all cars are going at the expected speed, the display will just be green with the word OK:

[内嵌示意图]

When a car is going slower than expected, it will display the car number of the slow car and the sector line at which the car is stopped:

[内嵌示意图]

The name of the line can be replaced by an alias using the Edit sector and loops table from the ribbon bar:

[内嵌示意图]

[内嵌示意图]

## For timing feed without GPS data​

The checkbox Use GPS needs to be unchecked:

[内嵌示意图]

The software will then check if a car is late at a sector line. It will compare the actual time that a car has been spending on a sector to the estimated sector time for that car. Once the difference is greater than the tolerance it will trigger the alarm.

## For timing feed with GPS data​

The checkbox Use GPS needs to be checked:

[内嵌示意图]

In this case, the tolerance is not used and the software will just detect a car on track that is going slower than 40kph for a 5Hz signal.

## Disable on Out Lap​

Slow cars in the first sector of the out lap won't be flagged as off track if you are not using GPS. However they could be flagged in the other sectors. We added a checkox to be able to blacklist cars in the out lap from the car off track scoreboard.

[内嵌示意图]

## Blacklisted Cars​

Sometimes a car can stays on the race track in HH Timing even after a crash. We added a textbox to be able to blacklist them from the car off track scoreboard.

Example without car blacklisted:

[内嵌示意图]

Example with car 4 blacklisted:

[内嵌示意图]

## Automatic spotter update on full track map​

When a car gets detected on the car off track display, it will automatically appear on the spotter option of the full track map:

![](https://help.hhtiming.com/assets/images/car_off_track_7-a8177ebf996ec9976045434234221160.png)

This allows a very quick visualization of which car has an issue and where on track it happened.

Once the car gets cleared (or blacklisted) from the car off track display, the spotter list from the full track map gets updated as well.

To disable this feature, use the "Show Stopped Cars Arrow" option in the track map ribbon bar:

![](https://help.hhtiming.com/assets/images/car_off_track_Track-84b437e3efd632d0c28e3f1fb86912fb.png)

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

