---
url: https://help.hhtiming.com/calculation-definitions/predicted-stint-length/
title: Predicted stint length
slug: calculation-definitions__predicted-stint-length
---

# Predicted stint length

-
- Calculation definition
- Predicted stint length

# Predicted stint length

In series where the stint lengths are primarily determined by fuel parameters the predicted stint length method of determining future stints will be appropriate. The predicted stint length for the future stints of each car are determined by the longest green stint to the current point in the session.

The predicted stint length values are made of primarily in the strategy overview [https://help.hhtiming.com/displays/overviews/#strategy-overview] and the relevant columns in the main scoreboard [https://help.hhtiming.com/displays/scoreboards/main-scoreboard].

An example of future stints being defined with the predicted stint length method is shown below. At this point the race has been all green running and the future stints for each car correspond to the longest stint of each car.

![](https://help.hhtiming.com/assets/images/predicted_stint_length_1-bb5f8566604048684ddc78d492eae9d6.png)

Note that the maximum stint length for each car can be manually overridden in the track item [https://help.hhtiming.com/settings-options/track-item-ghosts] if required on a per class or per car basis.

If there are no full green stints for a car or a stint that is interrupted by a caution period and has more green laps compared to any other stint for that car the software will estimate a maximum green stint length for each car. This is determined by applying a fuel correction factor for the number of laps each car spends under caution for that stint. This correction factor is the ratio expected consumption under caution compared to a green lap. The value should be less than 1, meaning that the car will use less fuel while under caution. It is a global variable and all cars are assumed to save the same ratio of fuel under the caution. This correction factor can be found in the track item [https://help.hhtiming.com/settings-options/track-item-ghosts] as it is a function of the circuit characteristics.

When a new strategy overview [https://help.hhtiming.com/displays/overviews/#strategy-overview] is created it will use the Predicted Strategy Type defined in the backstage options as shown below:

![](https://help.hhtiming.com/assets/images/predicted_stint_length_2-1cb7fec536b4b83a58edfebe0084ade1.png)

The following columns in the main scoreboard [https://help.hhtiming.com/displays/scoreboards/main-scoreboard] use the predicted stint lengths for their future predictions:

- Estimated # laps remaining in current stint
- Estimated # stops remaining
- Estimated # laps in final stint
- Estimated finish time
- Estimated # laps total
- Estimated # laps remaining

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
- main scoreboard — https://help.hhtiming.com/displays/scoreboards/main-scoreboard
- track item — https://help.hhtiming.com/settings-options/track-item-ghosts

