---
url: https://help.hhtiming.com/plugins/drive-time-plugin/
title: Drive time plugin
slug: plugins__drive-time-plugin
---

# Drive time plugin

-
- Plugins
- Drive time plugin

# Drive time plugin

The Drive Time Plugin was developed as a free of charge add-in to HH Timing to help teams make better strategic decisions during races with fixed stint times while respecting the event specific drive time rules. It is generally applicable to any event with fixed stint lengths.

## Download and Install​

The latest version of the Drive Time Plugin can be downloaded from our web portal (hh-dev.com) under HH Timing plugins or directly from: https://hh-dev.com/latest/HHT-DT

Once the plugin is downloaded, place the plugin folder (do not unzip) in the following directory:

```
Documents\HH Timing\Plugins\
```

Once the Plugin is placed in the correct directory, the next time HH Timing is started, you will have to go in the backstage and click on the Plugins tabs. All the plugins are listed here. Be sure that the Drive Time plugin is enabled.

[内嵌示意图]

Once you have enabled the plugin, you will need to restart the software. The Drive Time tab will now appear in the main ribbon bar at the top of the screen. This gives access to the Plugin features which can then be created and manipulated like any other component of HH Timing.

The source code for the plugin can be found in the Github Repository.

## Plugin Introduction​

There are different elements to the Plugin:

- Stint Summary
- Continuous Driving Time (Experimental)
- Cumulative Driving Time (Experimental)
- Pit Stop Window
- Pit Stopwatch
The Stint Summary gives an overview of the strategy situation relating to the driving time of the current driver for a single car on track. As many stint summaries for different cars as required can be used simultaneously. The Stint Summary is primarily intended for following your own car(s) but can also be used to understand other competitors driving time situation.

Note that all driver times are considered with respect to the rules where time in pit lane does not count towards the driving time. This is consistent with any other drive time data elsewhere in HH Timing.

tip
The Continuous Driving Time display will show you the elapsed time since your driver is in the car (including Pitstops!) and some informations like the number of laps before hitting the maximum continuous driving time. As it includes pit stop time, do not use it in GTWC.

The Cumulative Driving Time display shows the remaing time to minimum and the maximum driving times. It will shows the number of laps remaining before the minimum driving time, When your driver will have a driving time > minimum driving time, it will show you the number of laps before the maximum driving time, It includes pitstop time in the calculation.

Those two displays are experimental.

The Pit Stopwatch has two modes. When the car is on track it gives the user an estimate of how long until the car will arrive stationary in the pit box should you tell the driver to pit now. When the car is in the pit lane it gives you prompts and countdowns to help with the timing of the release windows for the Maximum Short and Minimum Long pit stop times.

## Assumed Pace​

At the center of many of the calculations used by the Plugin is the “Assumed Pace” assumption. To make forward predictions about the current and future stints a lap time must be assumed. This lap time is defined as the average of the best 3 laps in the last 5 laps.

![](https://help.hhtiming.com/assets/images/drive_time_2-08c0e744f0fa9c586401c80515995295.png)

Note that the above calculation for Assumed Pace ignores in/out laps and any “yellow” laps such as Safety Car and Full Course Yellows when selecting the last 5 laps.

## Stint Summary​

The Stint Summary can be thought of as a strategy tool that considers driving tim e as the primary factor, where traditionally fuel would be the primary consideration. A Stint Summary for Car 43 with David Fumanelli as the current driver is shown below. The background color of the Stint Summary is the colour of the Car defined in the Car Options within the main software to quickly understand which car the Stint Summary relates to.

![](https://help.hhtiming.com/assets/images/drive_time_3-88f20840f4cbda6be1930cf9e37286ea.png)

### Stint Summary Inputs​

The Inputs for the Stint Summary are accessible via the main ribbon bat at the top of the software as shown below. Note that the Driving Time rules are specified in the Track Definition.

- Car Number
- Estimated In Lap Time
- Merge with previous stint. Check this box to merge the current stint with the previous one in case of drive through to get the current stint time since the last
- Driving Time Rules (Set in Track Definition)
- EDS: enable the Extended Driving Stint (+5 min) for the current Stint only. It will be disable at the next pitstop.
The Estimated In Lap time is the time taken from crossing the finish line to the Pit In timing line. This defines the time length of the final lap in the stint, with the exception of the final stint.

### Stint Summary Outputs​

#### Stint Merged​

"Stint Merged" will be displayed when you check the box "Merge with previous stint".

[内嵌示意图]

#### Current Stint Time​

The drive time of the current stint which increments in real time.

#### Session Time if Max Stint​

If the current stint is stretched as long as possible, what will the session/race time be at the end of the current stint.

#### Stint Time if Box This Lap​

The predicted length of the current stint if the car boxes at the end of the current lap.

#### Next Lap​

The predicted length of the current stint if the car completes the current lap then completes one further lap.

#### Remaining Max Stint Time​

The amount of time left in the current stint if the current stint is stretched to the maximum allowed driver time for a single stint.

#### Max Laps Remaining​

The number of complete laps remaining in the current stint if the stint is stretched to the maximum allowed driver time for a single stint. This number is taken from when the car crosses the finish line at the end of the current lap. This is given as a decimal to give an idea of how close the car is from being able to do one more or one less lap in the current stint.

#### Rem. Continuous Driving Time​

The amount of driving time remaining for the current driver while respecting the CONTINUOUS driving time rules (driving time with back-to-back stints). *

#### Remaining Total Driving Time​

The amount of total driving time remaining for the current driver while respecting the TOTAL driving time rules for the entire race. *

## Maximum Stint Time and EDS​

### Maximum Stint Time​

The Maximum Stint Time is the maximum duration a single driver is allowed to drive continuously in a stint before a mandatory driver change is required. This value is defined in the Track Definition (Driving Time Rules) and is used by the plugin as the upper boundary for all stint calculations.

The Remaining Max Stint Time and Max Laps Remaining outputs are both derived from this value. A Box This Lap warning is triggered when the car cannot complete one more full lap without exceeding it.

### Extended Driving Stint (EDS)​

In some SRO events, the regulations allow one driver per car to use an Extended Driving Stint (EDS), which adds 5 minutes to the maximum stint time for that stint only. This is typically used strategically to gain a lap or delay a pit stop.

To activate EDS for the current stint, check the EDS checkbox in the ribbon bar inputs. The plugin will immediately recalculate all outputs using the extended maximum.

caution
EDS applies to the current stint only. It is automatically disabled at the next pit stop. It can only be used once per car per race according to the regulations.

When EDS is active, the EDS indicator is displayed in the Stint Summary:

[内嵌示意图]

#### Minimum Stint Time (No Extra Stops)​

The bottom row of the plugin has two modes, one with a time value, the other as a message.

In normal running conditions, the Minimum Stint Time (No Extra Stop) time will be displayed as shown below. This is the MINIMUM length that the current stint can be without being so short as to force the car to make an extra stop to finish the race. It can be thought of as when the pit window opens for the car in question.

![](https://help.hhtiming.com/assets/images/drive_time_5-2fe12358c17c1fcb39601546faf3e95e.png)

Once the Current Stint Time reaches the Minimum Stint Time (No Extra Stops) which are both highlighted below, the value is replaced by a Pit Window Open Message.

![](https://help.hhtiming.com/assets/images/drive_time_6-f5a8e8c740748827ef38d9087cc7f9b1.png)

![](https://help.hhtiming.com/assets/images/drive_time_7-8da92a2b4851087b910f87c9fbb1783d.png)

Note that in the image directly above, the Current Stint Time is 1:00:48 and the Plugin is telling the user that the pit window is open. In the images further above (which are taken from earlier in the same stint) it is stated the pit window will open at 1:01:57. This is a useful example of showing how the pit window can shift during a stint in this case it is affected by the evolution of pace of Car 43 making the window open earlier.

Once the car has crossed the line and it is predicted that it will not be able to complete any extra laps after the current lap while respecting the driving time rules, a “Box This Lap” message is shown at the bottom of the Stint Summary as shown below. This message flashes red to black to help get the attention of the user. There are three scenarios that can trigger the Box This Lap Warning:

- The maximum stint time will be exceeded
- The maximum continuous drive time will be exceeded
- The maximum total drive time will be exceeded
Inspection of the some of the other parameters below helps in understanding the calculations involved. The Stint Time if Box This Lap value shows that the driving time will not be exceeded at the completion of the current lap. However, the Next Lap value shows that an extra lap at the completion of the current lap will result in the driving time limit of 65 minutes being exceeded. The Max Laps remaining value is less than 1 which indicates that no full laps can be completed at the conclusion of the current lap.

![](https://help.hhtiming.com/assets/images/drive_time_8-92f6442f4dd5962ccb1f8ba02fe756c8.png)

*Note that the 2017 Blancpain GT Series Sporting Regulations state the time spent in pit lane WHILE serving a drive-through penalty is being served DOES count towards the driving time of the driver in the car. Currently, this is not a way for the software to deal with this scenario. Therefore, if a drive-through penalty is served by a car of interest this needs to be accounted for by the team by adding the time spent in pit lane during the drive-through to the driving time of that driver to the continuous and total drive time as necessary.

tip
In the track map shown below we are following Car 43 as indicated by the arrow. Say the value of Max Laps Remaining in the plugin at this moment is 10.2. This means once Car 43 completes the remainder of the current lap the calculation estimates that at the Assumed Pace, Car 43 will be able to complete 10 additional complete laps and stay within the driving time rules.

The 0.2 indicates that if Car 43 attempted to do an 11th lap (after the current lap is complete) the car would be 20% the way around the circuit when the maximum driver time for that stint expired.

Not only does this give the user an idea of how close the car is from completing one more or one less lap in the current stint, it also gives an idea of the margin in the driving time prediction.

![](https://help.hhtiming.com/assets/images/drive_time_9-36735ae5f0bca7af64978b90cd49a7ec.png)

## Pit Stop Window​

In some series like DTM, you need to pit in a predefined window, for example between 20 minutes and 40 minutes in the race. To help you on your strategy, you can use the Pit Stop Window to get some information like the minimal and maximum session time to pit according to your current pace, and the remaining time before the opening and the closure of the window.

### Pit Stop Window Input​

All inputs related to the Pit Stop Window are found in the ribbon bar control at the top of the main software as shown below. These parameters are dependent on the event specific pit stop rules. The average lap time used for the calculation will be the average of the 3 best laps in the last 5 laps, except if you filled the Average Lap Time For a Stint in the Track Item.

- Car Number
- Estimated In Lap Time (from Finish line to Pit-In, in seconds)
- Start of the pit window (in minutes)
- End of the pit window (in minutes)

### Pit Stop Window Outputs​

- Min Remaining Time: the time until the opening of the pit window.
- Max Remaining Time : the time until the closure of the pit window.
- Session Time if Pit after opening of PW: session time if you pit just after the opening of the Pit Window. It uses the current pace of your car + the estimated in Lap Time.
- Session Time if Pit before end of PW : session time if you pit just before the closure of the Pit Window. It uses the current pace of your car + the estimated in Lap Time.
- Min Remaining Laps: remaining laps before the opening of the Pit Window.
- Max Remaining Laps: remaining laps before the closure of the Pit Window.
- Pit Window open in / Pit Window closed in / Pit Window Closed: this will change depending of the session time. Before the opening of the pit window, you will get a countdown until the opening, then a countdown until the closure, and finally it will display Pit Window Closed.

![](https://help.hhtiming.com/assets/images/drive_time_14-60d40508b2c3b385d364366bca66730e.png)

## Pit Stopwatch​

Note because if the system used by the timing provider in Blancpain there can be delays in the timing feed, if there is any delay the Pit Stopwatch will not be accurate with respect to release windows. Generally, teams have their own system for dealing with this such as an in-car GPS based timer. The Pit Stopwatch does therefore form more of a backup option should anything affect a team’s normal method of timing the releases.

![](https://help.hhtiming.com/assets/images/drive_time_10-514ce87304d6a841c6ec61ad0443f424.png)

### Pit Stopwatch Inputs​

All inputs related to the Pit Stopwatch are found in the ribbon bar control at the top of the main software as shown below. These parameters are dependent on the pit lane length, the relative position of the pit box and the event specific pit time rules.

- Car Number
- Estimated In Lap Time (from Finish line to Pit-In)
- From Pit-In (time from Pit-In to Stationary in box)
- To Pit-Out (time from Stationary in box to Pit-Out)
- Maximum Short (short stop rules threshold)
- Minimum Long (long stop rules threshold)
Note that if the Maximum Short Stop is not used in the event, it can be set to zero to prevent it having any influence.

### Pit Stopwatch Outputs​

#### On Track Mode​

When the car is on track the Pit Stopwatch will look as below. The estimated time the car is from being stationary in its box if it boxes on the current lap is shown at the top. The Last Stop parameter gives a quick reference for the last pit stop time.

![](https://help.hhtiming.com/assets/images/drive_time_11-514ce87304d6a841c6ec61ad0443f424.png)

Note that more detailed information about previous pit stops can be found in the individual  Car Scoreboard and the Pit Stop Scoreboard.

#### In Pit Mode​

When the car is in the pit lane the Pit Stopwatch is counting the time since the car crossed the pit-in line, this is always shown on the top row. The bottom row changes in response to the release condition. The sequence is outlined below in text and images. The release window refers to the time the car must be released from stationary in its box.

- Car enters pit lane. The release window for the maximum short stop is open. The background is green.
- 15 seconds before the maximum short stop release window closes a countdown begins. The background flashes orange.
- When the counter reaches zero the release window for the maximum short stop is closed. The background is red.
- 15 seconds before the release window opens for the minimum long stop a countdown begins. The background flashes orange.
- Release window for the minimum long stop is open. The background is green.
- Car crosses pit-out line. Pit Stopwatch returns to on-track mode.

![](https://help.hhtiming.com/assets/images/drive_time_12-8b85c1b190c98f39ef4d814606c4b93a.png)

#### Manual Mode​

If there seems to be any noticeable delay in the timing feed and you are not confident that the Pit Stopwatch will be functioning as intended based on the timing feed then there is a "Manual Mode". If this option is checked, the user needs to click the Pit Stopwatch display when the car enters the pit lane. This click is then used as the trigger for the countdown procedure to begin.

## Plugin Settings Checklist​

The following list should be used as a checklist to ensure all values are correct for the current event and match those used by other team members.

### Backstage options​

- Predicted Strategy Type should be set to Fixed Stint Lengths in GTWC.

### Stint Summary​

- Car Number
- Estimated In Lap Time
- Driving Time Rules (Set in Track Definition)

### Pit Stopwatch​

- Car Number
- Estimated In Lap Time time
- From Pit-In time
- To Pit-Out time
- Maximum Short stop time
- Minimum Long stop time
- Manual Mode

## Testing the Plugin​

Replays of previous events should be used to familiarize yourself with the behavior of the plugin prior to the race. Running a replay is equivalent to being connected to a live timing feed from the perspective of the Plugin.

## Suggested Settings​

### Fixed Stint Lengths​

It is suggested the full 65 minute stint length is used in the  Fixed Stint Length input. This allows the most accurate calculation of the pit windows possible and leaves any “margin” being taken into account within the Engineers judgement only. This is opposed to entering 63 minutes assuming a 2:00 minute lap time which would build 1 lap margin into every stint in the race.

## Limitations​

### Race Finish Estimation​

SRO uses an unusual definition of the race end relating to the driving time of the driver in the car during the final stint compared to other major championships. The SRO Sporting Regulations state the driving time of the driver in the car ends when the time limit of the race is reached.

HH Timing is configured to find the end-of race time for each car based on when each car is predicted to cross the finish line with respect to the finish of the overall leader. This means that depending on the position of the car being tracked by the plugin relative to the leader and the time the leader will cross the finish line after the race expiration time, the software will predict a longer final stint from the perspective of driving time than will occur according to the Sporting Regulations.

For 2018 the plugin has been updated so that the  Minimum Stint Time for No Extra Stops/PIT WINDOW OPEN message matches the regulations. This means that while the calculation correctly matches the regulations, it is now less conservative.

![](https://help.hhtiming.com/assets/images/drive_time_13-e82719e321a97a8ec866efeaee528a45.png)

### Assumed Pace​

There are situations where the Assumed Pace method of predicting the future lap times can lead to some inaccuracy. In parts of the race where the pace changes drastically such as during the first period of transition to and from Full Course Yellow and Safety Car. This will affect all parts of the plugin where future calculations are being made that consider the future pace.

### Technical Stop​

The Technical Stop that must be completed during a window defined by the organiser in some events is not taken account into the forward planning of the future stints. However, after the Technical Stop has been taken by each car its influence on the driving time is included and calculations from that point forward are accurate.

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
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Making your own plugin — https://help.hhtiming.com/plugins/making-your-own-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/

