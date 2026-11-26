---
url: https://help.hhtiming.com/settings-options/track-item-ghosts/
title: Track item / Track Map / Ghosts
slug: settings-options__track-item-ghosts
---

# Track item / Track Map / Ghosts

-
- Settings & options
- Track item / Track Map / Ghosts

# Track item / Track Map / Ghosts

The Track Item is where track specific configurations can be set. The Track Item can be accessed from the project tree by double clicking.

[内嵌示意图]

When a new project is created a Default Track is automatically created. Additional Track Items can be added from the Components tab with the Add New Track button. This is helpful for keeping track specific information stored in your project without overwriting the settings used in previous events.

[内嵌示意图]

Track Items can be transferred between projects using the Import Track button in the Components tab. The default path to find a Track Item from another project is:

C:\Users\%USERNAME%\HH Timing\Projects\PROJECT NAME

## Track Contours​

Here the required track contour is selected. Track contours are built by HH Development, if the contour you need is not listed here, please contact us at support@hh-dev.com.

[内嵌示意图]

## Fuel Only Cutoff​

The software has a function to automatically determine if a stop was "fuel only" or not based on the time spent in the pit lane. This is only relevant if fuel and tyres are not able to be changed at the same time in the championship of interest.

[内嵌示意图]

When the cutoff value is enabled, output of the "fuel only" calculation is found in the last column of the Pit Stops section of the car scoreboard [https://help.hhtiming.com/displays/scoreboards/car-scoreboard].

![](https://help.hhtiming.com/assets/images/track_item_5-b649e569473009ba8af38c1793176748.png)

## Strategy Parameters​

Strategy parameters relevant to future stints are defined here. For each parameter a value can be defined for a class or car, the behavior is common for all:

- All cars in that category will have this setting enforced, unless:
- A value is defined for a specific car, in which case the car value takes precedence
- If no values are input here for a given class/car then the software makes an approximation based on the historical data in the current session
These values impact the Race Finish Calculations [https://help.hhtiming.com/calculation-definitions/race-finish-calculation/].

![](https://help.hhtiming.com/assets/images/track_item_6-13a53cb91216a37ab006bd1a7313c5a5.png)

## Number of Laps in Stint​

The maximum stint length for future stint calculations. All cars will be assumed to run each of their stints to the maximum length. Using this data the fuel windows are displayed for each car in the strategy overview [https://help.hhtiming.com/displays/overviews/#strategy-overview].

## Time to Refuel Each Lap of Fuel Burned​

The fuel rig rate in s/lap is used for calculating the next fuelling time for each car based on the length of the current stint which is useful for understanding who might pass who in the pit lane at the next stop. The fuel time is calculated by multiplying the number of laps (including the current) in the current stint by the refuel rate. This can be visualised in the main scoreboard [https://help.hhtiming.com/displays/scoreboards/main-scoreboard] by adding the Estimated Refuel Time column.

![](https://help.hhtiming.com/assets/images/track_item_7-851af3ba18f4772e646ee4c262cf26b6.png)

## Lap Time for a Stint​

The average lap time to be used for future stints can be manually defined here. If nothing is entered here the software will assume a pace equal to the average of the best 3 in the last 5 laps for each car individually, calculated with the Assumed Pace expression [https://help.hhtiming.com/calculation-definitions/assumed-pace/].

## Safety Car Fuel Factor​

This value is used by the predicted stint lengths calculation [https://help.hhtiming.com/calculation-definitions/predicted-stint-length]. If there are no full green stints for a car or a stint that is interrupted by a caution period and has more green laps compared to any other stint for that car the software will estimate a maximum green stint length for each car. This is determined by applying the Safety Car Fuel Correction factor for the number of laps each car spends under caution for that stint. This correction factor is the ratio expected consumption under caution compared to a green lap. The value should be less than 1, meaning that the car will use less fuel while under caution. It is a global variable, and all cars are assumed to save the same ratio of fuel under caution.

## Maximum Driving Time Rules​

These values are used by the drive time plugin [https://help.hhtiming.com/plugins/drive-time-plugin] to determine maximum driving time parameters for each driver.

## Track Parameters / Ghosts​

![](https://help.hhtiming.com/assets/images/track_item_8-f8a63cd5d97d7c68daecbdcc1c21f505.png)

Stop and Go Pit Loss: This input defines the time loss for a stop & go compared to cars on track. This is used by the software when the refuel time compensated [https://help.hhtiming.com/settings-options/track-item-ghosts/#advanced] ghost car option is used to determine the time loss for the Stop & Go only.

The track map highlighting options in the backstage options [https://help.hhtiming.com/settings-options/backstage-settings]  allow drawing the “Fuel” and “Fuel & Tyre” cars on the track map. These cars represent the projected track position of the cars after a pit stop, if you pitted on this lap. There are two calculations available:

- Basic (fixed)
- Advanced (refuel time compensated)

![](https://help.hhtiming.com/assets/images/track_item_11-50d83dec4d4ddbc8102cde5dd029d592.png)

### Basic​

The ghost cars are set with a fixed time offset to your current position on track. These should represent the total time loss relative to a normal green flag lap for completing this stop type (Fuel or Fuel & Tyres).

If you will lose:

- 111.8s for a Fuel and Tyres stop, and
- 44.8s for a Fuel only stop
The settings in the backstage options [https://help.hhtiming.com/settings-options/backstage-settings] shown below are what you should use:

![](https://help.hhtiming.com/assets/images/track_map_highlighting_5-ca660dd210e343077a656c65dadafab3.png)

### Advanced​

The advanced method updates your projected track position after a stop based on the amount of fuel you will need to add at the next stop. The loss of a Stop & Go and changing tyres are also considered.

If you will lose:

- 41.8s to complete a Stop & Go in the pit lane (including the time to connect fuel rig)
- 18.5s to change tyres
- 1.1s for every lap worth of fuel you must fill with the fuel rig
The settings in the backstage options [https://help.hhtiming.com/settings-options/backstage-settings] and Stop & Go Pit Loss shown below are what you should use:

![](https://help.hhtiming.com/assets/images/track_map_highlighting_6-862054907e8d9a799b417b35f0d73c73.png)

[内嵌示意图]

### Calculation Explanation​

Depending on the championship, tyres and refueling may or may not be carried out at the same time. This can be selected in the Championship configuration [https://help.hhtiming.com/settings-options/championship-configuration#championship-specific-information] settings. Then:

If Fuel & Tyres can NOT be changed in parallel:

Fuel Ghost Offset = Stop & Go Pit Loss + Number of laps since last pit stop * Seconds to add to pit stop per lap of stint length

Fuel & Tyres Ghost Offset = Stop & Go Pit Loss + Number of laps since last pit stop * Seconds to add to pit stop per lap of stint length + Time for Tyre and Driver Change

The used value for “Seconds to add to pitstop per lap of stint length” is defined as follows :

- If a value has been precisely defined for a car, this value will be used
- Otherwise the category value will be used by default.
- If no value is defined in the track options, the software will use the value defined in the backstage options
If Fuel & Tyres can be changed in parallel:

Fuel & Tyres Ghost Offset = Stop & Go Pit Loss + max(Number of laps since last pit stop * Seconds to add to pit stop per lap of stint length, Time for tyre and driver change)

So, if the fuel fill will take longer than the tyre change, then the fuel fill will determine the stop time.

Note that the "Time lost for fuel and tyres pit stop" and "Time lost for fuel only pit stop" inputs are ignored in the Advanced mode.

Pit Lane Stop & Go Time: This input defines the time it takes to go from Pit In to Pit Out while doing a Stop & Go in the box. This input is used to calculate the "Last Pit Stationary Time" column in the main scoreboard as well as the "Correct for pit lane time" option in the Pit Stop Scoreboard.

Pit not at start finish: Check it to TRUE if the pit lane is offset compared to the Start finish line. This is used for handling timing specificity at track where the pit lane is offset.

Allow first lap as best: At some event, depending on how the timing provider handle the first out lap in some session, the first lap in the timing is either considered the out lap or the first flying lap. This option allows you to choose if the software handles it as an OUT lap or a flying lap. This will impact the ranking of the cars in the scoreboard.

IN and OUT Lap ratio: The IN and OUT Lap ratio are lap time ratio between an average green lap time and the IN or OUT Lap time. Those values are used to improve the end of race calculations [https://help.hhtiming.com/calculation-definitions/race-finish-calculation].

In Lap Ratio = Average IN Lap time / Average Green Lap time with IN Lap Time going from S/F(track) to PIT IN

Out Lap Ratio = Average OUT Lap time / Average Green Lap time with OUT Lap Time going from PIT OUT to S/F(track)

Use Default Map Average For Extrapolation: This option allows to fix the time used for extrapolation on the track map to the default value. On a regular race event, this option should be set to false, to make sure that the software uses its optimization algorithm to position the cars. This option is useful on single sector track map where optimization is not possible.

## Custom Ghosts​

The custom ghosts cars can be used to display other offsets from the running car. The display of these cars is not controlled by the "Enable time lost cars on track map" [https://help.hhtiming.com/settings-options/backstage-options/#time-lost-ghost-cars] option and there is no limitation in the number of ghosts that can be defined in the track item.

![](https://help.hhtiming.com/assets/images/track_item_12-af66e342f416a72bf7554d1395d7c939.png)

Each ghost has the following properties:

- Name: ghost display name.
- Offset: constant offset applied to the running car.
- Multiplier: variable offset applied to the running car. The value of the variable offset is N Laps in the stint x Multiplier.
- Fuel: Add fuel time to the ghost offset. This value is set in the Strategy parameters of the track item. If a value has been precisely defined for a car, this value will be used, otherwise the category value will be used by default. If no value is defined in the track options, the software will use the value defined in the backstage options (detailed above).
- Include stop & go pit loss: Add pit time loss to the ghost offset. As a reminder, this value is defined in the Track parameters of the track options.
- Enabled: this option is used to hide or show ghosts on the go.
The total expression for the custom ghost offset calculation will then be : 

Custom offset = Offset + N Laps in the stint x Multiplier + N Laps in the stint x Time to refuel each lap of burned fuel + Stop & Go Pit Loss

[内嵌示意图]

Technical Pit Stop

This section allows the configuration of the Mandatory Technical Pit Stop in races like 24 Hours of Spa.

[内嵌示意图]

This will affect the Technical Pit Stop column on the main scoreboard.

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- Workbooks & layouts — https://help.hhtiming.com/workbooks-layouts/
- Displays — https://help.hhtiming.com/displays/
- Timing data management — https://help.hhtiming.com/timing-data-management/session-data/
- Settings & options — https://help.hhtiming.com/settings-options/backstage-settings/
- Backstage options — https://help.hhtiming.com/settings-options/backstage-options/
- Car options — https://help.hhtiming.com/settings-options/car-options/
- Championship configuration — https://help.hhtiming.com/settings-options/championship-configuration/
- Track item / Track Map / Ghosts — https://help.hhtiming.com/settings-options/track-item-ghosts/
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
- car scoreboard — https://help.hhtiming.com/displays/scoreboards/car-scoreboard
- Race Finish Calculations — https://help.hhtiming.com/calculation-definitions/race-finish-calculation/
- main scoreboard — https://help.hhtiming.com/displays/scoreboards/main-scoreboard
- Assumed Pace expression — https://help.hhtiming.com/calculation-definitions/assumed-pace/
- predicted stint lengths calculation — https://help.hhtiming.com/calculation-definitions/predicted-stint-length
- drive time plugin — https://help.hhtiming.com/plugins/drive-time-plugin
- backstage options — https://help.hhtiming.com/settings-options/backstage-settings
- race calculations — https://help.hhtiming.com/calculation-definitions/race-finish-calculation

