---
url: https://help.hhtiming.com/series-specific-info/supercars/
title: Supercars
slug: series-specific-info__supercars
---

# Supercars

-
- Series specific information
- Supercars

# Supercars

## Championship configuration​

 |  |
| Protocol | Natsoft XML
| Host | 192.168.4.1
| Port | 8889

[内嵌示意图]

Micro sector
The user can decide to use the Micro Sectors as main sectors instead of the regular S1/S2/S3. To do switch the option in the additional options to True

![](https://help.hhtiming.com/assets/images/supercars_2-2ebd71381285302c51a0301a9c44c303.png)

In addition, the user would need to select the correct map contour:

![](https://help.hhtiming.com/assets/images/supercars_3-b3f9b26622ad16a7e2413eee7b02124f.png)

## Time certain​

Supercars races are distance races with a time certain: if the distance is not completed when the time certain is reached, the leader completes the lap in progress plus one more lap.

The time certain is read from the timing feed (scheduled end of the race) and the following session settings [https://help.hhtiming.com/settings-options/backstage-options] are set automatically at the start of a distance race:

 |  |
| Race Length Mode | Distance
| Use time of day for timed session / time certain | True
| Race finish time of day | Time certain sent in the feed
The Extra lap after time certain option needs to stay at True (default value).

## Tyre compound​

The colours for the tyre compound can now be controlled within the software. This can be found under the Strategy Overview option in the backstage under Tyre Specification Colours:

[内嵌示意图]

![](https://help.hhtiming.com/assets/images/supercars_5-1e3456b494372ba6cf4af3dda2b656d5.png)

By default, the colours follow the Supercars convention (Soft "S" = BLACK and HARD "H" = ORANGE).

The current tyre compound can be shown on the Main Scoreboard using the Curr Tyres (Tyres on the car) and Prev Tyres (Tyres on the car during the last stint) column:

![](https://help.hhtiming.com/assets/images/supercars_6-c858866ec06730906550108dffe819d0.png)

The same information can be found in the stint scoreboard of the car scoreboard [https://help.hhtiming.com/displays/scoreboards/car-scoreboard/#stints]:

![](https://help.hhtiming.com/assets/images/supercars_7-3a6c6639ac3f7e2d3ba13dd09c634879.png)

In addition, the compound information can be displayed in the strategy overview [https://help.hhtiming.com/displays/overviews/#strategy-overview]:

![](https://help.hhtiming.com/assets/images/supercars_8-485a3662169fd75248daffc82d26fc5c.png)

To configure the line you see on the strategy overview [https://help.hhtiming.com/displays/overviews/#strategy-overview], You need to go to Select Parameters:

![](https://help.hhtiming.com/assets/images/supercars_9-79e5914dbcace86b7b26a9bae767329e.png)

You can display them by compound colour by selecting the option:

[内嵌示意图]

tip
By selecting only the Tyre Used, you can easily see the entire field:

![](https://help.hhtiming.com/assets/images/supercars_11-99bd2530b348bea1204a24cd1c907c2e.png)

## List of Micro-sectors per track​

The list of micro-sectors needs to be changed per track. The list from the table below needs to be copied into the cell in the championship configuration.

 | Track | Micro-sectors
| Adelaide | I3,P1;P1,P2;P2,I1;I1,P3;P3,I2;I2,P4;P4,I3
| Albert Park | I3,P1;P1,P2;P2,P3;P3,I1;I1,P4;P4,I2;I2,P5;P5,P6;P6,I3
| Bathurst | I3,P1;P1,P2;P2,I1;I1,P3;P3,I2;I2,P4;P4,P5;P5,I3
| Darwin | I3,P1;P1,P2;P2,I1;I1,P3;P3,P4;P4,I2;I2,P5;P5,P6;P6,I3
| Gold Coast | I3,P1;P1,P2;P2,I1;I1,P3;P3,P4;P4,I2;I2,P5;P5,I3
| Ipswich | I3,P2;P2,I1;I1,P3;P3,I2;I2,I3
| Newcastle | I3,P1;P1,P2;P2,I1;I1,P3;P3,P4;P4,I2;I2,P5;P5,P6;P6,I3
| Perth | I3,P1;P1,P2;P2,P3;P3,I1;I1,P4;P4,I2;I2,P5;P5,I3
| Phillip Island | I3,P1;P1,P2;P2,I1;I1,P3;P3,I2;I2,P4;P4,I3
| Pukekohe | I3,P1;P1,P2;P2,I1;I1,P3;P3,P4;P4,P5;P5,I2;I2,P6;P6,I3
| Ruapuna | I3,P1;P1,P2;P2,P3;P3,I1;I1,P4;P4,I2;I2,P5;P5,P6;P6,I3
| Sandown | I3,P1;P1,I1;I1,P2;P2,I2;I2,P3;P3,I3
| Sydney | I3,P1;P1,P2;P2,I1;I1,P3;P3,P4;P4,I2;I2,P5;P5,P6;P6,I3
| Symmons Plains | I3,P1;P1,P2;P2,I1;I1,P3;P3,I2;I2,P4;P4,I3
| Tailem Bend | I3,P1;P1,P2;P2,P3;P3,I1;I1,P4;P4,I2;I2,P5;P5,P6;P6,I3
| Tailem Bend WEST | I3,P1;P1,P2;P2,I1;I1,I2;I2,P3;P3,I3
| Taupo | I3,P1;P1,P2;P2,I1;I1,I2;I2,P3;P3,P4;P4,I3
| Townsville | I3,P1;P1,P2;P2,I1;I1,P3;P3,P4;P4,P5;P5,I2;I2,P6;P6,I3
| Winton | I3,P1;P1,P2;P2,I1;I1,P3;P3,I2;I2,P4;P4,I3
| Queensland | I3,P1;P1,P2;P2,I1;I1,P3;P3,I2;I2,I3

## Timing settings per track​

The timing configuration of the pit lane varies from track-to-track.  The following table lists the settings for each track.

 | Track | Control Line At Pit Out | Use Control Line As Pit Out | Use Control Line As Pit In
| Adelaide | True | True | False
| Albert Park | True | True | False
| Bathurst | False | False | False
| Darwin | True | False | False
| Gold Coast | False | False | True
| Ipswich | True | True | False
| Newcastle | False | False | False
| Perth | False | False | False
| Phillip Island | True | False | False
| Pukekohe | True | False | False
| Ruapuna | True | False | False
| Sandown | True | True | False
| Sydney | False | False | False
| Symmons Plains | True | True | False
| Tailem Bend | False | False | False
| Taupo | False | False | False
| Townsville | True | True | False
| Winton | True | False | False

## Track Limits Warning​

Track Limits Warning are sent in the feed in Supercars in practice and qualifying sessions only. It will be displayed in the main scoreboard, the car scoreboard, the driver scoreboard and the Track Limit Warning display. You can find specific help file here [https://help.hhtiming.com/displays/track-limits-warning].

In Supercars, a curb hop or shortcut results in the lap time being deleted during practice and qualifying sessions.

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
- session settings — https://help.hhtiming.com/settings-options/backstage-options
- here — https://help.hhtiming.com/displays/track-limits-warning

