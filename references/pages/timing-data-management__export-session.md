---
url: https://help.hhtiming.com/timing-data-management/export-session/
title: Export session
slug: timing-data-management__export-session
---

# Export session

-
- Timing data management
- Export session

# Export session

Exporting a session could be useful if you want to save or share a replay, or if you need to have data in a csv format to import them in Excel for example.

## Export a session​

To export a session, you need to do a right click on a session in the tree, and then select one of the export option:

![](https://help.hhtiming.com/assets/images/export_1-b56df5717fe4cfe0de50fb0653ceb629.png)

### Export Replay​

It will export a file you will be able to replayed on another computer or in another project (you will need to select the same protocol).

### Export (IMSA Format)​

It will export a CSV file with the same columns than CSVs provided by IMSA.

### Export (Tyres)​

It will export a CSV file with the same columns than CSVs provided by IMSA with  an additional column "Tyres".

### Export (Telemetry)​

It will export a CSV file with the same columns than CSVs provided by IMSA with additional columns for the telemetry-derived lap values: "Energy Remaining", "Energy Consumed" and "Energy Refill Time".

### Export (Supercars Format)​

It will export a CSV file with the same columns than the IMSA format plus two columns after "Location": "Kerb Hops" and "Shortcuts", True when at least one such track limits warning was reported on the lap (Natsoft XML feed), otherwise False.

### Export (Al Kamel Format)​

It will export a CSV file with the same columns than CSVs provided by Alkamel in WEC/ELMS/AsLMS.

### Export Raw Messages​

It will export in a file all messages received by the software. It can be useful to check if you have received all the expected messages.

### Export Session Data (JSON)​

This feature allows you to export session data (cars, laps, stints, flag segments) to a JSON file for use in external tools or custom analysis.

To open the Session Data Export, click the Export JSON button in the Export group of the Data ribbon tab:

![](https://help.hhtiming.com/assets/images/json_export_1-4624def35316a6e635739082534a634a.png)

This will open a Session Data Export worksheet. From there:

- Click Browse... to select the destination file path.
- Right-click on the session in the tree and click Activate to load the session data into the export worksheet.

![](https://help.hhtiming.com/assets/images/json_export_2-4690f1606921ceb32cac00d6050332d6.png)

- Click Export to JSON in the ribbon to perform the export.

![](https://help.hhtiming.com/assets/images/json_export_3-216938cfce5894741bbee87c97bfe092.png)

The status bar at the bottom of the worksheet displays the number of cars, laps, stints, and flag segments currently loaded.

Each lap also carries a `NumericTags` object holding the telemetry-derived lap values, using the same names shown elsewhere in the software: `Energy Remaining`, `Energy Consumed`, `Energy Refill Time` and `Remaining P2P`. Only the tags the timing feed actually supplied are present, so the object is empty for sessions with no telemetry.

## Auto Replay Export​

The Auto Replay Export feature automatically saves a `.hhreplay` file for each session as soon as a new session starts. This is useful at events where sessions follow one another quickly and you want every replay captured without manual intervention.

To open the Auto Replay Export worksheet, click the Auto Replay Export button in the Data ribbon tab.

![](https://help.hhtiming.com/assets/images/auto_replay_export_1-f97bbaa9036cfff1bc28b7ef5e15121d.png)

### Setup​

- Click Browse... to choose the folder where replay files will be saved. The folder will be created automatically if it does not exist.
- Click Start to activate automatic export.

[内嵌示意图]

The status label turns green and reads Active — replays will be exported on session switch.

### How it works​

Whenever a new session is detected, the software exports the previous session in the background:

- If a pre-built .hhreplay file already exists on disk for that session it is copied directly to the destination folder.
- Otherwise the replay is regenerated from the project database using the raw message export.
The exported file is named after the session (invalid filename characters are replaced with underscores).

The status label updates after each export to show the filename and time of the last successful export, or an error message if the export failed.

[内嵌示意图]

### Stopping​

Click Stop to deactivate automatic export. Closing the worksheet tab also stops the export. Any replays already exported remain in the destination folder.

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- Workbooks & layouts — https://help.hhtiming.com/workbooks-layouts/
- Displays — https://help.hhtiming.com/displays/
- Timing data management — https://help.hhtiming.com/timing-data-management/session-data/
- Live timing feed connection — https://help.hhtiming.com/timing-data-management/live-timing-feed-connection/
- Timing and scoring data import — https://help.hhtiming.com/timing-data-management/timing-scoring-data-import/
- Replays — https://help.hhtiming.com/timing-data-management/replays/
- Remote replays database — https://help.hhtiming.com/timing-data-management/remote-replays-database/
- HH timing server mode — https://help.hhtiming.com/timing-data-management/hh-timing-server-mode/
- Session data recovery — https://help.hhtiming.com/timing-data-management/session-data-recovery/
- Export session — https://help.hhtiming.com/timing-data-management/export-session/
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

