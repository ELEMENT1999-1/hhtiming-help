---
url: https://help.hhtiming.com/calculation-definitions/driving-time/
title: Driving time
slug: calculation-definitions__driving-time
---

# Driving time

-
- Calculation definition
- Driving time

# Driving time

## Calculation option​

The driver drive time can be calculated two ways:

- excluding the time from PIT IN to PIT OUT regardless of the driver at PIT IN or the driver at PIT OUT. (Method used in most major racing series)
- excluding the time from PIT IN to PIT OUT only if the driver at PIT IN is different than the driver at PIT OUT. (Bathurst 12 Hours)
The option can be selected in the backstage options. By default the option is set to False:

[内嵌示意图]

## End of race calculation​

The driving time at the end of the race can be calculated two ways:

- When the race time is elapsed
- When the car finish the race
The option can be selected in the backstage options. By default the option is set to False, which means that the driving time is calculated until the car crosses SF line for the last time

[内嵌示意图]

## Red flags​

The red flag time of a race is not included in the driver driving time.

## Setting up maximum and minimum drive time​

In most series, drivers needs to respect a minimum and maximum driving time. This value can be entered in the car options [https://help.hhtiming.com/settings-options/car-options] for each driver.

Maximum and minimum driving time needs to be entered in minutes.

![](https://help.hhtiming.com/assets/images/driving_time_2-6ac7887ec6f11cdb57b9882e6ec1637e.png)

## Driver scoreboard​

Additional columns were added to the driver scoreboard to be able to better monitor driving time through the race.

![](https://help.hhtiming.com/assets/images/driving_time_3-0286f1d2289804c3d01f2a4abb316543.png)

- Driving Time - Total driving time since the start of the race
- DT Last 6 Hrs - Driving time in the last 6 hours. When the column goes above 3 Hours, the cell will turn orange. When it goes above 4 hours the cell will turn red.
- TT Max DT - Countdown to the Maximum Driving time. When the countdown is below 1 Hour, the cell will turn orange. When it reaches 0 the cell will turn red.
- TT Min DT - Countdown to the Minimum Driving time. When the countdown is below 1 Hour, the cell will turn orange. When it reaches 0 the cell will turn red.
- 4in6 Get OUT - Session time at which the driver would have to get out of the car not to breach the 4 Hours of driving in 6 Hours regulation. For drivers currently out of the car, it assumes that the driver would jump in the car immediately.
- 4in6 Nxt 4H at - Earliest session time at which the driver can jump into the car and drove for 4 hours. This column also accounts for maximum driving time. If it is not possible for a driver to get another 4 Hours block of driving in the race, the call will be empty.
- 4in6 ET to Fin - Earliest session time at which the driver can jump into the car and finish the race without breaching the 4 Hours in 6 Hours rules and the maximum drive time.

## Main scoreboard​

The same column can displayed in the main scoreboard for the driver currently in the car:

![](https://help.hhtiming.com/assets/images/driving_time_4-1990f57b1ffa91fe28f3b916ef629659.png)

caution
The driving time is calculated from lap time and Pit In and Pit Out time. There are some scenarios where the software doesn't have enough information to display an accurate driving time:

- Loss of timing information. The software will compensate automatically for a connection issue during a stint but if a Pit in or Pit Out message is not processed, then the timing information will be wrong.
- If a car do not cross Pit in or Pit Out. If a car is drove back to pit lane though an auxiliary road for example, it would not cross the Pit in loop. In this case the driving time for the driver in the car would be wrong.

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
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Predicted stint length — https://help.hhtiming.com/calculation-definitions/predicted-stint-length/
- Fixed stint length — https://help.hhtiming.com/calculation-definitions/fixed-stint-length/
- Assumed pace — https://help.hhtiming.com/calculation-definitions/assumed-pace/
- Degradation — https://help.hhtiming.com/calculation-definitions/degradation/
- Pit stop length — https://help.hhtiming.com/calculation-definitions/pit-stop-length/
- Race finish calculation — https://help.hhtiming.com/calculation-definitions/race-finish-calculation/
- Sanitized average lap time — https://help.hhtiming.com/calculation-definitions/sanitized-average-lap-time/
- Yellow flag laps — https://help.hhtiming.com/calculation-definitions/yellow-flag-laps/
- IMSA Safety car wave-by — https://help.hhtiming.com/calculation-definitions/IMSA-safety-car-wave-by/
- Projected lap time — https://help.hhtiming.com/calculation-definitions/projected-lap-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/
- car options — https://help.hhtiming.com/settings-options/car-options

