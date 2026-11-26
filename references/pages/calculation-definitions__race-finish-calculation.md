---
url: https://help.hhtiming.com/calculation-definitions/race-finish-calculation/
title: Race finish calculation
slug: calculation-definitions__race-finish-calculation
---

# Race finish calculation

-
- Calculation definition
- Race finish calculation

# Race finish calculation

The end of race calculation can be defined in 4 separate ways and can be chosen in the session settings [https://help.hhtiming.com/settings-options/backstage-options/#session-settings].

- Timed
- Timed + 1 lap
- Distance
- Time & Distance
The relevant values in the session settings need to be set in the session settings [https://help.hhtiming.com/settings-options/backstage-options/#session-settings] to make this calculation valid.

For the calculation to be accurate it is required that the overall leader and any cars of interest have completed at least one fully green stint. This means that each lap in the stint is green (or green with local yellow) and the pit stops at the beginning and end of the stint occur under green conditions. If this condition is not met, then the calculation will use the longest stint with yellow flags, using a scaling factor to adjust the fuel consumption under the yellow flag. This scaling factor is set in the track item [https://help.hhtiming.com/settings-options/track-item-ghosts]. The value should be less than 1, meaning that the car will use less fuel while following the safety car. Currently, the results are only available on the scoreboard; there are 8 additional columns created in the scoreboard. The calculation results are shown in the Main Scoreboard and the Strategy Overview. The calculation uses the following parameters:

- Average Lap Time is calculated as a moving average of the best 3 in the last 5 green flying laps.
- Number of Green Laps in Longest Stint is the number of green laps in the longest stint.
- Number of Yellow Laps in Longest Stint is the number of yellow laps in the longest stint. Ideally, this number should be 0 for the calculation to be the most accurate.
- Average Pit Stop Time is the average of all green flag pit stops
These columns are then used, along with the session length value entered earlier to calculate the following columns:

- Estimated # Laps Remaining in Current Stint is calculated based on the length of the longest green stint. Note that if the current stint becomes longer than the current longest green stint then this number will become negative, showing how many laps further the car is going (this could be due to safety cars, for example).
- Estimated # Stops Remaining is calculated based on the amount of time left in the race, using the average lap time, average pit stop time, and maximum stint length. This calculation assumes that the rest of the race will take place under green conditions, no probabilistic assumptions are made for safety cars/yellow flags.
- Estimated # Laps in Final Stint shows how many laps would be completed between the final pit stop and the end of the race.
- Estimated Finish Time shows the time at which each car will finish the race. At the moment the calculation is done on the leader of the race at the moment of the calculation.
- Estimated Finish Type shows for each car if it can complete the distance within the time limit (if Time & Distance is selected as Race Length Mode).
Note that if the car does not have enough time to complete 1 pit stop and at least 1 lap of the final stint, then the pit stop will not be included in the calculation, and the penultimate stint will become the last stint with additional laps added. Note that in this case, the stint length may become slightly longer than the maximum stint length.

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
- track item — https://help.hhtiming.com/settings-options/track-item-ghosts

