---
url: https://help.hhtiming.com/displays/track-maps/full-track/
title: Full track map
slug: displays__track-maps__full-track
---

# Full track map

-
- Displays [https://help.hhtiming.com/displays/]
- Track maps [https://help.hhtiming.com/displays/track-maps/]
- Full track map

# Full track map

![](https://help.hhtiming.com/assets/images/full_track_1-f08d19171c54e307c53ef68064fb6bc2.png)

Full track maps can be added from the Displays tab. There are two ways to select the circuit contour.

- Components Tab [https://help.hhtiming.com/getting-started/ribbon-bar/components]
- Track Item [https://help.hhtiming.com/settings-options/track-item-ghosts]
For basic use of the software, setting the track contour by the Components Tab will suffice. For more advanced users the Track Item is more suitable as it allows the setting of more advanced settings and features that should be updated for each event.

To set the contour by the Components Tab navigate to the Components Tab and use the Select Contour button. This will set the track contour for any Full Track displays used in the project.

![](https://help.hhtiming.com/assets/images/full_track_2-1a4382414e517429bb0a7011b2ca74a9.png)

tip
Track map contours are not editable by users. If a track map you need is not included in the software or a different circuit configuration is required contact us [https://help.hhtiming.com/support/email].

## Appearance​

By default all cars are shown on the track map. In addition to filtering where you can remove classes/cars you are not interested in, there are some additional options to make it easier to see classes of interest.

### Highlight Classes​

Normally you would not filter out any cars from the track map in order to be able to understand traffic. However, often you are interested in one class over others. In this case you can put emphasis on your class of interest while still being able to see the position of cars in other classes. For this, you can use the Highlight Classes function in the Main Track Map ribbon control, shown below.

By default the Highlight Classes function is unchecked, in the example the focus class is GTLM.

![](https://help.hhtiming.com/assets/images/full_track_3-0b8d5e4ec54b63b81a52afff250288f4.png)

Below is an example of a track map shown with all classes showing which is the default behavior, Highlight Classes is not active here.

![](https://help.hhtiming.com/assets/images/full_track_4-a03ceb851a42fca3999af055a8d9cdce.png)

Below is the same situation but with the Highlight Class set to GTLM. The GTD (in orange) cars are still shown but are shown as small dots. Note that the GTD leader is still shown.

![](https://help.hhtiming.com/assets/images/full_track_5-45d21fda387494e6ddb6f56849639ea0.png)

Note that the syntax for the class must match how the class in defined in the timing feed. You can check this in the project tree under Category Configuration.

### Temporary Highlighting​

In cases where a given class has been filtered out from the main track map, a car from that class can be shown quickly if needed. The control for this is the "plus" sign in the top right of the main track map. For example, you only have your class of interest shown on the track map and all other classes are hidden by being filtered out. If you get a race control message about a specific car from another class (that is hidden) then entering that car number after clicking the "plus" sign will show that car on track as if it hadn't been filtered out.

## Labeling Options​

Options for the labeling and coloring of track sectors, slow zones and corners can be found in the ribbon bar control. The following options are available when applicable:

- Color sectors
- Color by Slow Zone Sectors (for circuits such as Le Mans)
- Show sector labels
- Show corner labels
- Show marshal sectors
- Show marshal sector labels
- Show slow zone sectors
- Show slow zone sector labels

## Car Position Methods​

### Default​

By default the position of cars on the track map are drawn based on the the crossing of the timing lines. The position of each car is approximated based on the historical time for each car to complete each sector. This approximation is continuously being updated on a per car basis and is corrected each time a car crosses each sector. The track status is also taken into account in this approximation which improves the accuracy when track status changes by only using relevant data from the applicable track status.

### GPS​

In series where the GPS position of each car is available over the timing feed the position of each car can be drawn via the GPS data. This is enabled by enabling the Use GPS Feed checkbox. The default method is generally robust in race situations but there are some situations where using the GPS data is helpful:

- During qualifying where the speed of cars is varying a lot between laps. Using the GPS option in this case makes finding a sufficiant gap on track for a qualifying run easier.
- On long circuits such as Le Mans where there can be a large distance between timing lines.

### Use Computer Time​

See Use Computer Time To Draw Positions [https://help.hhtiming.com/displays/track-maps/#use-computer-time-to-draw-positions] in the shared track map settings.

## Sector heat map on track map​

The user can now colour the sectors based on a delta between two cars:

![](https://help.hhtiming.com/assets/images/full_track_6-82b84e82e5815d87d4b236eea34e3a73.png)

The options are controlled in the ribbon bar of the track map under the colour mode option:

[内嵌示意图]

For the reference car, if the car selection is left empty then it will take the best car of the same category of the Delta Car.

### Heat map modes​

The heat map mode determines which sector times are used for the reference and delta comparison. The following modes are available:

- Best — Uses the best lap sector times. When multiple reference cars are specified, the car with the best lap time is selected.
- Theoretical — Uses the best individual sector times (theoretical best lap). When multiple reference cars are specified, the car with the best theoretical lap is selected.
- Rolling — Uses the best rolling lap sector times. When multiple reference cars are specified, the car with the best rolling lap is selected.
- Last — Uses the last completed lap sector times. When multiple reference cars are specified, the car that most recently completed a lap is selected (based on time of day of lap completion).
When no reference car is specified, the heat map uses the best value within the delta car's class for the selected mode.

## Zoom​

### Corner and Sector Label Size​

The corner and sector label size can be adjusted with these two sliders.

[内嵌示意图]

### Zoom on the map​

Zooming in on specific areas of the map is possible by pressing CTRL key and scrolling the mouse wheel.

### Zoom on Car​

Zooming on a specific car is possible by enabling Focus On Car in the ribbon of the Full Track Map.

![](https://help.hhtiming.com/assets/images/full_track_15-1c7fcc1459cae62685f0cf19dfa58808.png)

The slider can then be used to adjust the zoom level on the car.

## Show energy deploy and regen​

info
This option is only available on Indycar RIS protocol

[内嵌示意图]

When this option is enabled in the ribbon bar, the cars outline change if they are regenerating or deploying energy. Red border means Deploy and green border means Regen.

![](https://help.hhtiming.com/assets/images/full_track_11-a08e9882bc2663fddf1c89650ae0502a.png)

## Virtual finish car​

The virtual finish car is a theoretical car running on track at a pace defined in the average laptime value. This car can be enabled from the ribbon bar.

[内嵌示意图]

The position on car is such that at time remaining 0, the car will cross start finish line and therefore it is an indication for cars to be able to do an extra lap during the session.
If a car is on track ahead of the red dot, this car will be able to cross SF line before the end of the session and therefore will do an extra lap. If a car is behind, it will not be able to start a new lap before the end of the session.
In the following picture, with 20 seconds to go in the session, car 1 will not be able to do an extra lap because it is running behind the theoretical car.

![](https://help.hhtiming.com/assets/images/full_track_14-d1f32a7637cf4bb8ac766997ac055230.png)

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
- Components Tab — https://help.hhtiming.com/getting-started/ribbon-bar/components
- Track Item — https://help.hhtiming.com/settings-options/track-item-ghosts
- contact us — https://help.hhtiming.com/support/email

