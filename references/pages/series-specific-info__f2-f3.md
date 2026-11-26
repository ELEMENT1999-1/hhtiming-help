---
url: https://help.hhtiming.com/series-specific-info/f2-f3/
title: FIA Formula 2 / Formula 3
slug: series-specific-info__f2-f3
---

# FIA Formula 2 / Formula 3

-
- Series specific information
- FIA Formula 2 / Formula 3

# FIA Formula 2 / Formula 3

## Live Timing Connection​

F2/F3 live timing uses the F2/F3 Signalr protocol. Enter the following URL in the championship configuration:

 | Field | Value
| URL | https://infopages.fomsystem.com
When the connection is started, multiple browser windows will open, each displaying a login form. If Connection Credentials are configured, the software will automatically fill in and submit the form in each. Otherwise, you must enter your FIA-provided credentials manually in each. These browser windows must remain open for the duration of the session.

The connection options are configured in the championship configuration's Additional Connection Information property.

### Additional Options​

The following options can be set as key-value pairs in the Additional Connection Information:

#### Connection Credentials​

 | Key | Value
| Username | Your FIA-provided username
| Password | Your FIA-provided password
If these are set, the software will automatically fill in and submit the login form in both browser windows.

#### SF At Pit In​

 | Key | Value
| SF At Pit In | true or false (default: false)
At some tracks (e.g. Monaco), no start/finish crossing is sent by the feed while a car is in the pits. When this option is enabled, a start/finish crossing is recorded when the car is detected as being in the pit lane, ensuring the in-lap time is correctly captured. A lap result is also sent for the lap being completed.

Enable this option for tracks where in-lap times are not being recorded.

#### Available Tyre Compounds​

 | Key | Value
| Available Tyre Compounds | Compound names separated by ; (e.g., Soft;Medium)
Defines the two tyre compounds available for the session. When a car exits the pit lane, the software automatically assumes it has switched to the other compound.

This option only takes effect when exactly two compounds are provided. For example, if a car started on `Soft` and the available compounds are `Soft;Medium`, the car will be set to `Medium` after its pit stop.

#### Starting Tyre Compounds Per Car​

Any additional key-value pair where the key is a car's racing number is treated as that car's starting tyre compound.

 | Key | Value
| 1 | Soft
| 4 | Medium
Use this to pre-configure the starting compound for each car before the session begins. These values are applied the first time each car appears in the timing feed.

### Example Configuration​

 | Key | Value
| SF At Pit In | false
| Available Tyre Compounds | Soft;Hard
| 1 | Soft
| 2 | Hard
| ... | ...
| 24 | Soft
| 25 | Hard
note
The session time in this protocol has an accuracy of ±1 second as the timing feed does not include milliseconds in its session time updates.

## PDF Import (Post-Session)​

In F2/F3, organizer will provide you differents PDF.

To imports datas into HH Timing, you need to:

- Select XXX_SectorAnalysis_XXX.pdf file in timed session.
- Select XXX_SectorAnalysis_XXX.pdf, XXX_Race1HistoryChart_XXX.pdf , XXX_PitStopSummary_XXX.pdf in race.

[内嵌示意图]

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

