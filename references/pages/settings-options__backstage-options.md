---
url: https://help.hhtiming.com/settings-options/backstage-options/
title: Backstage options
slug: settings-options__backstage-options
---

# Backstage options

-
- Settings & options
- Backstage options

# Backstage options

## Auto-update​

#### Allow check for new versions​

When True: When an internet connection is available, software will check for automatic updates

## Data import​

#### Merge sessions during bulk import​

Currently a disabled option within software.

## General​

#### Car Makes/Teams Colours​

A Collection of Car Make/Teams and associated colour. The colour will be used for new cars with the car make/team (depending of the value of Default Colouring Mode) name containing the key.

[内嵌示意图]

You can use * to set a default colour for all other cars.

#### Default Colouring Mode​

Car Make or Team Name depending of how you want to set car default colour.

## Help​

#### Show project wizard​

When True: the Project Wizard helper will show when starting a new project

## Layout​

#### Confirm before closing worksheet​

When True: user is asked if they are sure they want to close the worksheet

## Misc calculation​

#### Sort cars at sectors during race​

If True: the positions of the cars are updated at the end of each sector, otherwise only at the end of each lap. This is exposed as an option as there can be situations where a certain car will struggle to be picked up by a given sector line. If this happens while cars are being sorted at sectors the software will "think" this car has dropped down the order. This correct order would then only be rectified when crossing the next (working) sector or finish line.

If all equipment is working properly the preferred setting if True. Most commonly this setting needs to be set to False in IMSA as this is where the issue tends to arise occasionally.

## Moving average​

#### Default laps before/after​

Default lower/upper bound of window size for moving average plots.

## Reference car​

#### Default reference car​

For any displays [https://help.hhtiming.com/displays] where a reference car can be set as an option, this defines the default car number that will be chosen.

## Reporting​

#### Best X quantities for report graphs/tables​

A comma-separated list of integers for the X values of the best X calculation in reports (e.g. 5,10)

#### Best X% quantities for report graphs/tables​

A comma-separated list of integers for the X% values of the best X% calculation in reports (e.g. 5,10)

#### Clean function threshold​

Lap time threshold relative to the fastest lap (per car) above which will be excluded from reporting.

#### Default report custom logo​

Default logo/image to be used in new report templates

#### Minimum number of laps in race stint​

Not currently used

#### Report template library​

Default local directory where report templates are saved

## Scoreboard settings​

![](https://help.hhtiming.com/assets/images/scoreboard_options-197aff1eb6b57da22c3191c027fbc26c.png)

#### Colour for best time for car​

Best Lap/Sector/Speed colour convention for each CAR in the session

#### Colour for best time for driver​

Best Lap/Sector/Speed colour convention for each DRIVER in the session

#### Colour for best time in class​

Best Lap/Sector/Speed colour convention of the CLASS in the session

#### Colour for best time in stint​

Best Lap/Sector/Speed colour convention of the STINT for each CAR

#### Colour for best time overall​

Best Lap/Sector/Speed colour convention of ALL CARS for the session

#### Colour for slower projected time​

Colour convention for a CAR doing a slower projected time than its best lap

#### Default scoreboard autosize columns​

When True: Default autosizing behavior of scoreboard columns

#### Default scoreboard black background​

When True: Default background color for tables and views is black

#### Default scoreboard display seconds​

When True: Default time display format is in seconds

#### Number of non-track sectors in scoreboard​

Default number of non-track sectors shown in scoreboards when no session is active. Overridden when session data is loaded.

#### Number of sectors in template​

Default number of sectors shown in scoreboards when no session is active. Overridden when session data is loaded.

#### Number of speed traps in template​

Default number of speed traps shown in scoreboards when no session is active. Overridden when session data is loaded.

#### Reset last sectors every lap​

When True: sectors from previous laps are cleared when CAR crosses S1 in the current lap.

## Session export options​

#### Export session top speed at MPH​

When True: speed data CSV export is in units of MPH

## Session settings​

#### Disable race finish calculation​

When True: disables calculations for the forward predictions. This allows the software to process data much quicker and can be helpful to speed up replays of data-heavy races to a certain point.

#### Enforced number of pit stops​

The number of stops to be used by the strategy prediction calculation when the number is fixed (see below)

#### Enforced number of pit stops enabled​

When True: forces the forward strategy predictions to use the number of stops that have been manually defined.

#### Enforced pit stop time​

If the Pit Stop Time Mode (see below) is set to User Defined Fixed, then this is the value that will be enforced. This should be set to the total time from pit in to pit out for a regular pitstop.

#### Fixed stint length​

If the maximum stint lengths are defined by driving time (such as GT World Challenge Europe) then this is where the maximum stint length that is used for the forward strategy projections is defined. This is utilised to the fixed stint length [https://help.hhtiming.com/calculation-definitions/fixed-stint-length] projections.

#### Pit stop time mode​

Defines the "mode" the software will use to determine the length of future stops for the forward strategy projections. The following options are available:

- User defined fixed
- Average of history
- VLN rules (only relevant for NLS events)
- Calculated

##### User defined fixed​

It uses  the Enforced pit stop time (see above).

##### Average of history​

It uses the average of all previous green flag stops on a per car basis.

##### Calculated​

It uses the stop and go time from the track project options, the refuel rate from either the backstage or the track project item, the time for tyre/driver change from the backstage and fuel/tyres in parallel from the championship config. At each stop it fills the amount of fuel needed and ALWAYS changes tyres/driver.

tip
Example
For example with 20 laps to go and a pitstop in 10 laps, the estimated finish time will be:

9Average Lap Time (calculated or from Track Item) + Average LapTime In Lap Ratio(from Track Item) + Pit Lane Stop & Go Time (from Track Item) + Stopped Time + Average Lap Time Out Lap Ratio (from Track Item) + 9Average Lap Time(calculated or from Track Item)

where Stopped Time (if NOT Fuel and Tyres in parallels) = number of laps in future stint (in this example, 10) * refuel Rate (from Track Item) + Time For Tyre Change (from Track Item)

Stopped Time (if Fuel and Tyres in parallels) = Max(number of laps in future stint (in this example, 10) * refuel Rate (from Track Item), Time For Tyre Change (from Track Item))

#### Predicted strategy type​

Used for the race finish calculations. The following options are available:

- Predicted Stint Lengths
- Fixed Stint Lengths
In most series the appropriate setting will be "Predicted Stint Lengths ". GTWC Europe is an example of when you would use "Fixed Stint Lengths" due to the stint limit being 65 minutes.

#### Race finish mode​

Used to define the end of race condition. The following options are available:

- When leader finishes
- When time elapses
In most series the appropriate setting will be "When leader finishes". VLN/N24 is an example of when you would use "When time elapses" due to the length of the lap.

#### Race length mode​

Used to define the length of the race. The following options are available:

- Time
- Distance
- Time & Distance
Depending on if the race is time or distance limited this setting should be obvious. In cases where the race length is defined as when either a certain time or distance is reached (which ever occurs first), Time & Distance should be used. In the case of the Time & Distance setting the estimated race finish type can be shown in the main scoreboard [https://help.hhtiming.com/displays/scoreboards/main-scoreboard] as an optional column.

#### Session length (hours)​

If race length is time limited the race time can be entered here.

#### Total number of laps to be completed (if distance limited)​

If race length is distance limited the race distance can be entered here.

#### Use time of day for timed session / time certain​

When True: the race finish time is based on the Race finish time of day instead of the session length.

If the race length mode is Distance, the time of day is used as the time certain: the race finishes when the distance is completed or when the time certain is reached, whichever occurs first. The estimated race finish type can be shown in the main scoreboard [https://help.hhtiming.com/displays/scoreboards/main-scoreboard] as an optional column.

#### Race finish time of day​

Local time of day (24H format HH:mm) of the end of the race, or of the time certain for a distance race.

#### Extra lap after time certain​

Only used when the race length mode is Distance and Use time of day for timed session / time certain is True. When True: once the time certain is reached, the leader completes the lap in progress plus one more lap. When False: the race finishes when the leader completes the lap in progress.

## Strategy overview​

#### New tyre colour​

New tyre colour, shown in Strategy Overview when tyres are displayed.

#### Unchanged tyre colour​

Used tyre colour (from previous stint), shown in Strategy Overview when tyres are displayed.

#### Used in a previous session colour​

Used tyre colour (from a previous session), shown in Strategy Overview when tyres are displayed.

#### Used tyre colour​

Used tyre colour (from the current session), shown in Strategy Overview when tyres are displayed.

## Server mode configuration​

The Server Mode [https://help.hhtiming.com/timing-data-management/hh-timing-server-mode] of HH Timing exists to broadcast the timing feed within your team network in cases where the number of connections to the circuit timing feed is limited by the timing provider. See the Server Mode [https://help.hhtiming.com/timing-data-management/hh-timing-server-mode] section for a detailed description of how to set this up.

#### Timing and scoring server enabled​

When True: this computer will broadcast (forward) a timing feed over the local network to allow other users to receive timing data without direct connection to official timing feed.

#### Timing and scoring server port number​

Port number that other users (clients) will use in the Championship Configuration when connecting to the server computer over the local network. This can generally be left as the default value of 24689.

## Track map highlighting​

#### Car highlighting​

Cars of interest can be "highlighted on track maps to make them easier to find when checking quickly. Multiple cars can be highlighted if needed. If a car is highlighted:

- The colour of the car is set to be the car colour as opposed to the class colour which it is by default
- An arrow points to the highlighted
- The focus car has priority and is rendered on top of other cars that are close together
tip
Example: Car #51
In the top image, car #51 is not highlighted. In lower image, it is.

![](https://help.hhtiming.com/assets/images/track_map_highlighting_1-f875eaf2ee333fe129c73590762fd1bb.png)

![](https://help.hhtiming.com/assets/images/track_map_highlighting_2-35a078a7f1accaa8a56d0b8996b1ea9e.png)

##### Settings in Backstage Options​

Any cars that you wish to follow should have their number input. Note that you can enter multiple cars as a comma separated list. You must set the checkbox to enable car following on track map to be true.

[内嵌示意图]

##### Settings in Ribbon Bar​

- Car scaling, size of cars can be modified
- Arrow size, changes the size of the arrow used for car following

#### Time lost ghost cars​

The ghost cars settings are detailed in the Track Item / Track Map / Ghosts [https://help.hhtiming.com/settings-options/track-item-ghosts] section.

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
- displays — https://help.hhtiming.com/displays
- fixed stint length — https://help.hhtiming.com/calculation-definitions/fixed-stint-length
- main scoreboard — https://help.hhtiming.com/displays/scoreboards/main-scoreboard
- Server Mode — https://help.hhtiming.com/timing-data-management/hh-timing-server-mode
- Track Item / Track Map / Ghosts — https://help.hhtiming.com/settings-options/track-item-ghosts

