---
url: https://help.hhtiming.com/excel-exports/live-excel-export/
title: Live excel export
slug: excel-exports__live-excel-export
---

# Live excel export

-
- Excel exports
- Live excel export

# Live excel export

caution
Be careful to don't sync your runsheet on onedrive or similar services.

tip
There is a conflict in Excel in some culture like German, Spanish or Italian. That leads to some wrong values for your lap times and sector times. To avoid that, we recommend to switch th english culture in windows parameters or to remove the dot as thousand separator in additional culture parameters

The live Excel data export allows you to export timing data to Excel in real-time while connected to the timing and scoring feed. This is useful for populating a custom run sheet and can be used for custom fuel/strategy calculations. Data available for export include raw data from the timing feed as well data post-processed by HH Timing, in a range of formats where appropriate.

To set up an Excel export you must first either create a new Excel export profile or import an existing one. Once the profile has been added to the project it will automatically open. The Excel Workbook parameter should be the path to an Excel workbook that will be used for the export.

The video tutorial below explains how to create, configure and make the live Excel export:

[YouTube 视频: https://www.youtube.com/watch?v=VVidK-dUZzA]

## Parameter export frequency​

The following parameters are exported at the end of each lap:

- Lap number
- Elapsed time
- Lap time
- Driver
- Position
- Position in Class
- Track status
- Driving time (current driver)
- Stint lap number
- Moving Average
- Leader Lap Time
- Class Leader Lap Time
- Estimated Total # of Laps In Race
- Stint Number
- Number Of Cars Passed
- Number Of Cars Passed By
- Track Limits
The following parameters are exported at the end of a sector or upon a speed trap crossing:

- Lap Number
- Sector times
- Non Track Sector times
- Speed traps
- Gap to Car Ahead
- Gap to Car Behind
The following parameters are exported at the end of a lap when applicable:

- Pit stop time [Lap]
- Time of pit in [Lap]
- Time of pit out [Lap]
The following parameters are exported after a pit stop:

- Pit stop time
- Time of pit in
- Time of pit out
- In driver
- Out driver
- Pit stop lap number
- Fuel Only/Fuel & Tyres
- Pit Bit
The following parameters are exported at the end of a stint (at pit-in):

- Stint length (# of laps)

## Additional sectors​

If you added sectors in your championship configuration, or if Non-Track Sectors are being sent in the feed (like Porsche, Ford, T6, T7 sectors in Le Mans), you can export them by using NTSx parameters. You need to enter the number of Non Track Sector in the Backstage options.

![](https://help.hhtiming.com/assets/images/live_excel_export_1-671799eff7bcbb651562e4eff361b0b9.png)

## Macro​

The Excel export is capable of calling VBA macros that perform functions within the Excel sheet being exported to. These macros can be called either when a new worksheet is created (when Auto Worksheet mode is enabled) or each time a new value is written to Excel.

tip
In the case that a user wanted a macro to write the string " Written" to cell A1 in Sheet1 every time a value was exported from HH Timing to the Excel sheet. The VBA code to achieve this is shown below:

![](https://help.hhtiming.com/assets/images/live_excel_export_2-386f3b604a9e6693dd1a96f41a423455.png)

In HH Timing, the VBA function should be referenced like this in order to be called:

![](https://help.hhtiming.com/assets/images/live_excel_export_3-770718833d20e39afabc9b438f7fadb2.png)

## Run sheet example​

HH Development developed a simple excel spreadsheet to use in conjunction with the excel export function of HH Timing.

The excel run sheet can be downloaded here.

The template to load in HH Timing can be downloaded here.

Steps to get started:

- Download the template for HH Timing
- Import the Profile in HH Timing

![](https://help.hhtiming.com/assets/images/live_excel_export_4-d527372f7c083d17d14bf304e67d7c7c.png)

- The template will be available on the tree. Double click to open it.

![](https://help.hhtiming.com/assets/images/live_excel_export_5-f92948f6ace6207486ff5e13462c70ac.png)

- Once the template is open you will have the change path of the excel to the path where you downloaded the excel run sheet.

![](https://help.hhtiming.com/assets/images/live_excel_export_6-58d11e0405001106228f2d0537c4cbab.png)

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- Workbooks & layouts — https://help.hhtiming.com/workbooks-layouts/
- Displays — https://help.hhtiming.com/displays/
- Timing data management — https://help.hhtiming.com/timing-data-management/session-data/
- Settings & options — https://help.hhtiming.com/settings-options/backstage-settings/
- Excel exports — https://help.hhtiming.com/excel-exports/live-excel-export/
- Scoreboard live excel export — https://help.hhtiming.com/excel-exports/scoreboard-live-excel-export/
- Reporting — https://help.hhtiming.com/reporting/
- Series specific information — https://help.hhtiming.com/series-specific-info/imsa/
- Timekeeper specific info — https://help.hhtiming.com/timekeeper-specific-info/natsoft/
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/

