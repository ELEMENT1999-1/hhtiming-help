---
url: https://help.hhtiming.com/displays/track-maps/gap-track/
title: Gap track map
slug: displays__track-maps__gap-track
---

# Gap track map

-
- Displays [https://help.hhtiming.com/displays/]
- Track maps [https://help.hhtiming.com/displays/track-maps/]
- Gap track map

# Gap track map

![](https://help.hhtiming.com/assets/images/gap_track_1-0edb25efb0adf3fb1d06eb296207ad96.png)

The gap map shows the position of each car on the track relative to the reference car, based on the time gap between the cars. The reference car is shown at 0 seconds (by default, in the middle of the map).

Cars on the same lap as the reference car are shown with a square number icon, cars on a different lap are shown with a circular number icon.

Under green flag (or local yellow) conditions the map is updated every 0.1 seconds. In between sector crossings the gap between two cars is estimated based on the lap time difference between the two cars. At each sector crossing, the positions are updated based on the actual gap between the cars. Under safety car conditions, the gaps between the cars are not estimated between sector crossings and remain constant. The gap map is not functional during the first lap of a session.

The reference car can be changed, but please note that each car will need to cross the next sector line before all of the information on the map will be correct. The range of the map (in front and behind) can also be changed - this will update immediately.

## Blue Flag Warning​

The blue flag warning is designed to notify if a car is catching the reference car at a high enough rate that it is from a faster class. A visual and/or audible warning can be given which can be selected in the ribbon bar control.

The criteria for the blue flag warning to be active for an approaching car is:

- The gap to be within a user defined threshold
- The rate of closure is above a user defined threshold
By default the rate of closure is set at 0.03 seconds per second, but is user definable. On a 120 second lap, this gives a lap time difference of 3.6 seconds which should be sufficient to separate LMP1 and LMP2 cars, for example.

## Traffic ahead on gap track map​

On the Gap track map, you can now "predict" future lap positioning on track. This can be useful to plan pit stops with traffic. This feature is especially valuable with different categories on track but could be use in Indycar on high degradation track.

This is controlled from the option in the ribbon bar:

![](https://help.hhtiming.com/assets/images/gap_track_2-ac082da0aca753585bb8e01efda8c330.png)

![](https://help.hhtiming.com/assets/images/gap_track_3-f14f92cd281b46b5a997e642529d91c5.png)

This feature is currently using the assumed pace for calculation.

## Time to catch a car​

The time to catch a car shows the expected time when the reference car will catch a vehicle that is running in front with a slower average laptime. The value is shown in seconds at it is displayed below the number of the car that is going to be caught.

![](https://help.hhtiming.com/assets/images/gap_track_4-1da077a63d6ff5308c07bd406679968f.png)

If a car in front does not have a value below, it means that its average laptime is faster and therefore the vehicle is moving away from the reference.

This is controlled from the option in the ribbon bar:

![](https://help.hhtiming.com/assets/images/gap_track_5-9852e69885b8dc860201f7f9fdeca8f6.png)

## Line where a car will be caught​

If the time to catch a car has a value and that value is less than two times the average lap time of the reference car, there is the possibility to show the line on track where the car will be caught.
This line is calculated using the average lap time of the reference car and the average time of crossing through each on track loop. Therefore, it needs some laps in the session to be able to calculate accurate averages.

![](https://help.hhtiming.com/assets/images/gap_track_6-b378ee5f9db1ef6da3d5117e35b934db.png)

The display of this value is controlled from the option in the ribbon bar:

![](https://help.hhtiming.com/assets/images/gap_track_7-c97cdae87b39875d545e205cc960a0c8.png)

### Catching zones​

Extra zones in between the loops can be created by the user to be able to easily identify the exact track location of the overtake

[内嵌示意图]

For each zone the user must define:
-Display name
-Previous line on track
-Delta time from the previous line to the start of the zone

When the calculation finds a zone that matches the track location of the overtake the control shows the name of the zone instead of the line on track name.

![](https://help.hhtiming.com/assets/images/gap_track_9-02311ccdcfcb425e1f85570bb2d3ef69.png)

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
- Full track map — https://help.hhtiming.com/displays/track-maps/full-track/
- Gap track map — https://help.hhtiming.com/displays/track-maps/gap-track/
- Circle track map — https://help.hhtiming.com/displays/track-maps/circle-track/
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

