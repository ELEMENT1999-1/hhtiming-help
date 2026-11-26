---
url: https://help.hhtiming.com/displays/clocks/
title: Clocks
slug: displays__clocks
---

# Clocks

-
- Displays [https://help.hhtiming.com/displays/]
- Clocks

# Clocks

## Session Clock​

The session clock is accessible from the main ribbon bar of the software. Usually the time remaining is provided by the live feed; however the user can change the length of the session manually. The session clock can show the time remaining or the elapsed time. Those options are accessible from the ribbon bar of the control. The session clock background will reflect the condition of the track (Green Flag / Yellow (Or S/C) / Red Flag). There is an option for an audible warning when the track status changes (Green to Yellow for example), this option is accessed via the ribbon bar control for the session clock.

![](https://help.hhtiming.com/assets/images/clocks_1-494b4ac2d441cf186c752fe2c31799ba.png)

## Car Stopwatch​

The car stopwatch is accessible from the main ribbon bar of the software. You can create as many stopwatches as you want for as many cars as you want. The stopwatch is a useful tool to know where your car (or another) is on track, to know when you should speak on the radio for example. The background colour is set to the same as what is defined in the  Car Options. There are 3 modes the Car Stopwatch switches between:

### On Track During Stint​

- Top left shows car is on track
- Top right shows car number that is being followed
- Bottom right shows the time since the car last crossed the finish line
- Bottom left shows the sector the car is currently in

![](https://help.hhtiming.com/assets/images/clocks_2-126f24fbcba5765a8c34e3d5de799ec3.png)

### Car Enters Pit Lane​

- Top left shows car has entered the pit lane. The session time the car entered is shown.
- Top right shows car number that is being followed
- Bottom right shows the time since the car entered the pit lane
- Bottom left shows the sector the car is currently in (will depend on position of finish line in pit lane)

![](https://help.hhtiming.com/assets/images/clocks_3-fb42424359b89c35ed08723dfb076391.png)

### Car Exits Pit Lane​

- Top left shows car has exited the pit lane. The time of the just completed pit stop is shown.
- Top right shows car number that is being followed
- Bottom left shows the sector the car is currently in

![](https://help.hhtiming.com/assets/images/clocks_4-e388e694751973e553175575772249e6.png)

### Count Down to Pit Stall Option​

There is a check box in the ribbon bar control for the Pit Stopwatch to "Count down to pit stall". The purpose of this is to allow engineers and/or mechanics to be able to quickly understand how far away the car is form arriving in the box should an emergency stop need to happen at short notice at the end of the current lap. When this is active this replaces the time field in the bottom right with a counter estimating how long until the car will arrive stationary in the box if the car pitted this lap. To configure this option:

- Check the "Count down to pit stall" box
- Enter a semicolon separated list of typical sector times for the car of interest.
Example for a 3 sectors track: Time(S/F-->Pit Stall) ; Time(S1line-->Pit Stall) ; Time (S2line-->Pit Stall)

## Advanced Car Stopwatch​

The advanced car stopwatch is accessible from the main ribbon bar of the software. You can create as many stopwatches as you want for as many cars as you want. The background color is set as the car color.

The stopwatch displays the last line that the selected car crossed:

[内嵌示意图]

The name of the line can be replaced by an alias using the Edit sector and loops table from the ribbon bar:

[内嵌示意图]

![](https://help.hhtiming.com/assets/images/clocks_7-ccf88bedd3d87195b34198e9a3a4496f.png)

There is an additional option called "Keep" that allows to keep the last time a car crossed a certain line on track and to display the track status and the elapsed time accordingly:

![](https://help.hhtiming.com/assets/images/clocks_8-a48202922623a18db8fea71c8dcbf78e.png)

![](https://help.hhtiming.com/assets/images/clocks_9-7031a0ec11ba6ca7bcc2f359b304018e.png)

Sector lines can be hidden (for example in Le Mans where there are all speed / acc loops) by enabling the "Hide Sectors" option.

[内嵌示意图]

For WEC and ELMS events, enabling the Pit Entry Status and Pit Exit Status allows the display of their respective statuses.

[内嵌示意图]

## Time of Day Clock​

If the local time of day is available over the timing feed it can be shown with this clock.

info
Note that this feature is not compatible in all timing feeds as some feeds do not include time of day data.

Most of the timing feeds send the time of day in UTC. An offset function is available in the ribbon car control if necessary. There is also an option to automatically get the UTC offset from the timing feed.

[内嵌示意图]

info
The automatic timing feed offset is only supported on AlKamel streams.

If time of day is not available, or when the software is not connected to the timing feed, the clock will display the time of day from the computer clock.

## Green Timer​

During a race session, the display shows the amount of time the track status has remained green since the last caution period. This is particularly useful in series such as IMSA where some regulations depend on how long it has been since the last caution period.
During other session types (such as practice and qualifying) it shows the session time corrected by red flags. It shows the current elapsed time minus the total red time in the session.

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

