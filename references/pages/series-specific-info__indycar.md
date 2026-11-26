---
url: https://help.hhtiming.com/series-specific-info/indycar/
title: Indycar
slug: series-specific-info__indycar
---

# Indycar

-
- Series specific information
- Indycar

# Indycar

## Championship Configuration​

MyLaps RIS Server is now the unique protocol to connect to the timing feed in Indycar. The Multiloop Timing protocol is no longer available.

To connect live you will have to create a championship configuration with the following parameters.

- Protocol - MyLaps RIS Server
- Host - 172.30.16.25 (track) | 64.85.132.67 (remote)
- Username -Provided by Indycar
- Password - Provided by Indycar
- DataSet Name - Depending on the series you want to followIndycar
- INDY NXT

- Session - Leave blank to get the current/latest
- Read Session HistoryTrue will read the full history of the current session when you connect
- False to disable

- Read TelemetryTrue will read and save the telemetry from the feed
- False to disable

- Telemetry Host - 170.30.16.63 (track) | 64.85.132.31 (remote) you must have both Read Telemetry = True and the IP address populated to initialize the telemetry reading
- Save Telem Raw MessagesTrue will save the incoming raw telemetry messages. This will enable the session to be replayed with the telemetry data, but has no impact on being able to view the data after the session. Saving this data will make your project use more disk space.
- False to disable, and decrease the size of your project.

- Save Telem DataTrue will save the incoming telemetry data in your database. This will enable loading telemetry data in the data viewer, or exporting telemetry data.
- False to disable, and decrease the size of your project.

Managing project size
The Save Telem Raw Messages and Save Telem Data settings can be used to manage the project size.  Project size can grow quickly when storing the telemetry data for all cars.  Consider your requirements of the telemetry data when setting these.  If the telemetry data is only needed to show the position of the cars on the track maps, then setting both of these to False will allow the track map to function properly live, and minimize the project size.

Race Control Messages

- Please note that at the moment, when connecting mid-session with the option Read History set to True, the Race Control Messages are not retrieved. The replays from the remote database do not display these messages since they were recorded with the option set to True.
- The Race Control Messages are not yet available on the cloud feed.

### Session Names​

If you want to redownload data throughout the weekend you can use the following session names.

#### Indycar Road Course​

 | Session Name | Note
| Practice 1 | Never active live
| Practice 1 - All Cars |
| Practice 1 - Group A |
| Practice 1 - Group B |
| Practice 2 | Never active live
| Practice 2 - All Cars |
| Practice 2 - Group B |
| Practice 2 - Group A |
| Qualifications | Never active live
| Qualifications - Segment 1 / Group 1 |
| Qualifications - Segment 1 / Group 2 |
| Qualifications - Segment 2 / Top 12 |
| Qualifications - Segment 3 / Firestone Fast 6 |
| Warm-up |
| Race |

#### Indycar Oval​

 | Session Name | Note
| Practice 1 |
| Qualifications |
| Practice High Line |
| Practice Final |
| Race |

#### Indy NXT​

 | Session Name
| Practice 1
| Practice 2
| Qualifications - Group 1
| Qualifications - Group 2
| Race

## Track Map​

The track map should be selected for each configuration (ALT or RACE). Indycar track maps can  be found under the Indycar folder:

![](https://help.hhtiming.com/assets/images/indycar_3-22325a921de6294eedad3c2cceb32d36.png)

### GPS positioning​

Starting in 2026, Indycar will provide GPS positioning live. This can be used to position car on the Full Track Map. to do so, the Car Position Mode should be set to GPS:

![](https://help.hhtiming.com/assets/images/indycar_29-d85f274a74a53be88929f6468bd8b106.png)

note
Please note that to get the GPS Positioning, you will need to set the "Read Telemetry" option to "True" in the Championship Configuration :

[内嵌示意图]

### Extrapolated positioning​

The other option for the Full Track Map is to use the extrapolation method based on sector crossing. For this, the best option to select is the Auto Extrapolated for the Car Position Mode.

## Create Custom Sectors​

Users can define custom sectors in the “Additional Options” grid of the Championship Configuration.

The sector name (chosen by the user) is defined in the first column, and the second column defines the start line and the end line for the sector, separated by a ; character (example: I3 ;I4 will give you the time between these two lines).

A custom sector can also be defined by the addition of several sub-sectors using the following syntax:  StartLine1;EndLine1;StartLine2;EndLine2;StartLine3;EndLine3 ...etc. In that case you can easily sum non-consecutive sectors.

[内嵌示意图]

Any pair of loops can be used to define a custom sector, only the start(s) and end(s) loop need to be defined, the loops do not need to be consecutive.

Important

- The name of any of the additional sectors can not be the same as any of the sectors in the main feed.
- If you make a change to the definition of the custom sectors, for these to be shown in the software the data needs to be re-processed.
- Graphs that are made that include custom sector data may need to be remade if the custom sector definition is changed.
- If CONNECTED LIVE: You will need to disconnect, replay the session you were just connected to, re-connect to the live session (do not clear scoreboard). The data that was sent while you were disconnected will not be recorded by the software. For this reason it is better to stay connected to the live session and only replay to re-process the data once the session finishes if you do not need this additional data during the session.
- If NOT CONNECTED LIVE: Just replay the session with the new sectors definition active and the new sectors will appear.

### Speed Traps for Custom Sectors​

HH Timing can create speed traps for any of the custom sectors. A third argument can be entered after the START and END loops that define the custom sector, which is the distance (in meters) between the timing loops separated by a semi-colon.  StartLine1;EndLine1;Distance (in m)

## Tow analysis​

To use the No-Tow calculation, three prerequisites must be met :

- In the backstage options, under Scoreboard, you need to make sure that the Tow calculator is enabled. Once the option is enabled, the software must be restarted for the change to take effect.

![](https://help.hhtiming.com/assets/images/indycar_33-ed213e30dc91c950401d1c37082e6d71.png)

Those settings can be updated live without restarting the software.

Tow calculator extra sectors - This is to add some sectors prior to the start of the rolling lap to make sure a car didn’t get a tow and then started a rolling lap with no tow.

Tow calculator no tow gap - Filter on Min Gap allowed for the ranking on the main scoreboard

Tow calculator slow sectors threshold - This threshold allows not to take into account cars that are really slow on the race track. We believe that 1.1 (10%) is a good starting number.

- You need to make sure you are in average speed and imperial units:

[内嵌示意图]

- The correct track map needs to be selected.

[内嵌示意图]

### Main scoreboard​

Some additional columns are available in the main scoreboard:

- Last Lap Min Gap - the minimum gap to the car in front throughout the entire last lap
- Best Min Gap - the minimum gap to the car in front on the best lap from the session
- NT P - No-Tow position based on HH Timing settings
- NT Best - No-Tow best lap time based on HH Timing settings
- NT Best At - No-Tow best lap elapsed time based on HH Timing settings
- NT Best In - No-Tow best lap # based on HH Timing settings
- NT Best Min Gap - The minimum gap to the car in front on NT Best based on HH Timing settings
- Indy NT P - No-Tow best position from Indycar feed (9sec | only work on Multiloop currently)
- Indy NT Best In - No-Tow best lap # from IndyCar feed (9sec | only work on Multiloop currently)
- Indy NT Best - No-Tow best lap time from IndyCar feed (9sec | only work on Multiloop currently)

### Car scoreboard​

An additional column is available in the car scoreboard:

- Minimum Gap - The minimum gap to the car in front throughout the entire lap

![](https://help.hhtiming.com/assets/images/indycar_40-87f67541a011e979de6214a5fbb7b1bb.png)

### Tow analysis scoreboard​

![](https://help.hhtiming.com/assets/images/indycar_36-276ea48e947b270cbe7863f89712c2b9.png)

### Scoreboard columns​

- P Act - Actual overall ranking in the session
- P NT - Ranking based on the No Tow lap based on the scoreboard settings
- # - Car Number
- Driver - Driver Report Name
- Team - Team Name
- No Tow - Fastest rolling lap time achieved by the car in the session based on the scoreboard settings
- Best In - Lap in the session in which No Tow lap was done
- Best At - Elapsed time at which the No Tow lap was set
- Min Gap - What was the minimum gap to the car in front when the No Tow lap was done

### Scoreboard settings​

The No Tow Gap filter can be changed for the Tow analysis scoreboard only :

[内嵌示意图]

No Tow Gap - Filter on Min Gap allowed

### Gaps​

The Gaps tab was created to display different gap bins.

![](https://help.hhtiming.com/assets/images/indycar_38-286a59f79ea32c33563231035cf2862e.png)

For example the column “2” filters every lap that has a minimum gap to the car in front <=2.

### Graph​

The graph TAB plots all the rolling laps recorded on a graph. The X-axis is the minimum gap on track to the car in front for the entire rolling lap.

![](https://help.hhtiming.com/assets/images/indycar_39-350632e98518ebbb73cd9a71d5a98f3a.png)

## Pit Commit for Indy​

![](https://help.hhtiming.com/assets/images/indycar_6-47ff8f638d43e4e2fa6dd55e5d95655d.png)

This option was created to remove cars from the track map that are on the pit commit or pit out blend. The car will disappear from the track map and show on a different line at the bottom of the screen. The goal being to better handle traffic in practice.

![](https://help.hhtiming.com/assets/images/indycar_7-1491778639e619c0f34a23467779ee4a.png)

## Distance-based races​

Races can be of three types:

- Time
- Distance
- Time and Distance
The settings need to be set in the Session settings session in the backstage option:

![](https://help.hhtiming.com/assets/images/indycar_8-a00e4e6768928f24006c2578816a7916.png)

Now the session clock can show the lap information instead of the time:

[内嵌示意图]

This is done by choosing the Lap# or Laps to Go as the Clock mode in the option of the Session Clock:

[内嵌示意图]

The strategy overview can also be shown using the lap number:

![](https://help.hhtiming.com/assets/images/indycar_11-2e9b6b8c4ac045f197460c36878e2213.png)

This is done by selecting the Distance Mode option under Strategy Overview:

![](https://help.hhtiming.com/assets/images/indycar_12-1a5e024eee8aa1a99116f08f70679d22.png)

## Tire compound​

The colors for tire compound can now be controlled within the software. This can be found under the Strategy Overview option in the backstage under Tyre Specification Colours:

[内嵌示意图]

By default the colors follows the Indycar convention:

![](https://help.hhtiming.com/assets/images/indycar_14-d6b1ad4ea554d98c0728417416086306.png)

The tire compound can be shown on the Main Scoreboard using the StintTyres column:

![](https://help.hhtiming.com/assets/images/indycar_15-3fb82771c0b41d506391f367a2d1d5ed.png)

The same information can be found in the Car Scoreboard --> Stint:

![](https://help.hhtiming.com/assets/images/indycar_16-efbdb25506192cff8cd9ec0f19997130.png)

In addition, the compound information can be displayed in the strategy overview:

![](https://help.hhtiming.com/assets/images/indycar_17-5fb7c273d0aa05098b11d6e0cf67f1b5.png)

To configure the line you see on the strategy overview, You need to go to Select Parameters:

![](https://help.hhtiming.com/assets/images/indycar_18-79e5914dbcace86b7b26a9bae767329e.png)

By default, the tyres will be displayed as BLACK=USED and RED=NEW. You can display them by compound color by selecting the option:

[内嵌示意图]

tip
By selecting only the Tyre Used, you can easily see all cars in the field:

![](https://help.hhtiming.com/assets/images/indycar_20-61076a102647784a2090022fd59ebb99.png)

## Qualifying Scoreboard​

In display under the Other Scoreboards there are two differents scoreboard that can be used.

### Indy 500 Qualifying Scoreboard​

This is specific scoreboard designed for the Indy 500 specific qualifying system.

![](https://help.hhtiming.com/assets/images/indycar_31-b95fe1dfac0884c8af1ed917d4252240.png)

### Oval Qualifying Scoreboard​

For all other Oval qualifying the regular Oval Qualifying Scoreboard can be used.

![](https://help.hhtiming.com/assets/images/indycar_32-cebf49d755a7b020b587d048d0e241b5.png)

## Weather info​

The weather information from the feed will now be displayed using the Weather Conditions control:

![](https://help.hhtiming.com/assets/images/indycar_24-0817893c786023ad2adcaf5937eb9307.png)

![](https://help.hhtiming.com/assets/images/indycar_25-c734cd404a0779dab2575657df4ba872.png)

tip
The unit scheme can be changed from Imperial to Metric in the backstage option under General:

![](https://help.hhtiming.com/assets/images/indycar_26-9d40dea3f4506c6ebe175fcc1503ac9d.png)

## Telemetry Export​

A telemetry export module is included inside HH Timing under the Data Tab:

![](https://help.hhtiming.com/assets/images/indycar_27-a6f06b6312665f8f7b719d4ed39a56a9.png)

[内嵌示意图]

- Export Directory: folder where the data will be exported to (each car is exported to a dedicated sub folder)
- Export Type: file format(s) to be exported
- Export Source: this is legacy from Multiloop - not needed for RIS
- Export Interval [min]: the interval of the auto export
- Use Time Of Day To Link Laps: this should be set to false starting in 2026. If it is false the telemetry data is exported based on the automatic link with the lap that is created when running live. If true, the software will look at the time of the lap and the timestamps of each data point to associate the data to the lap. This option should not be needed from 2026 onwards.
Note on export

- the export can done at any time, even live during a session
- it is exporting one file per lap and there is one folder per car
- the best lap is marked with a # at the end of the file name
- for the PDS the file needs to be viewed vs distance in PI Toolbox

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
- IGTC — https://help.hhtiming.com/series-specific-info/igtc/
- WEC & ELMS — https://help.hhtiming.com/series-specific-info/wec-elms/
- Le Mans 24 Hours — https://help.hhtiming.com/series-specific-info/lm24/
- NLS & N24 — https://help.hhtiming.com/series-specific-info/nls-nbr24/
- N24 2023 — https://help.hhtiming.com/series-specific-info/nbr24-2023/
- Indycar — https://help.hhtiming.com/series-specific-info/indycar/
- Recommended Settings — https://help.hhtiming.com/series-specific-info/indycar/recommended-settings/
- Supercars — https://help.hhtiming.com/series-specific-info/supercars/
- SRO America — https://help.hhtiming.com/series-specific-info/sro-america/
- FIA GT World Cup Macau - 2026 — https://help.hhtiming.com/series-specific-info/macau/
- Super GT & Super Formula — https://help.hhtiming.com/series-specific-info/supergt-super-formula/
- EWC — https://help.hhtiming.com/series-specific-info/ewc/
- ADAC Gt Masters — https://help.hhtiming.com/series-specific-info/adac-gt-masters/
- iRacing — https://help.hhtiming.com/series-specific-info/iracing/
- rFactor 2 — https://help.hhtiming.com/series-specific-info/rfactor2/
- FIA Formula 2 / Formula 3 — https://help.hhtiming.com/series-specific-info/f2-f3/
- GTWC Europe — https://help.hhtiming.com/series-specific-info/gtwc-europe/
- DTM — https://help.hhtiming.com/series-specific-info/dtm/
- FormulaE — https://help.hhtiming.com/series-specific-info/formulae/
- Asian le mans series — https://help.hhtiming.com/series-specific-info/asian-le-mans-series/
- Porsche Sprint Challenge North America and US West — https://help.hhtiming.com/series-specific-info/porsche-sprint-challenge-na-usw/
- MotoGP — https://help.hhtiming.com/series-specific-info/MotoGP/
- NASCAR — https://help.hhtiming.com/series-specific-info/nascar/
- GT Open — https://help.hhtiming.com/series-specific-info/gt-open/
- Creventic 24H Series — https://help.hhtiming.com/series-specific-info/creventic/
- Timekeeper specific info — https://help.hhtiming.com/timekeeper-specific-info/natsoft/
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/

