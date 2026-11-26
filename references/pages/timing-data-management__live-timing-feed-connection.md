---
url: https://help.hhtiming.com/timing-data-management/live-timing-feed-connection/
title: Live timing feed connection
slug: timing-data-management__live-timing-feed-connection
---

# Live timing feed connection

-
- Timing data management
- Live timing feed connection

# Live timing feed connection

The live connection is used to read data from a timing and scoring server during a session. To connect to a live connection the “Connect” button on the Data tab [https://help.hhtiming.com/getting-started/ribbon-bar/data] of the ribbon bar should be used.

There are 3 types of live connection possible with HH Timing:

- Socket connection
- HTML scraping
- FTP server
This section will explain each type of connection. The connection protocol and all related options and settings are defined in the Championship project item [https://help.hhtiming.com/settings-options/championship-configuration].

## Socket Connections​

A socket connection is the most common connection method. In this case, the user should normally just supply the host name and port number of the timing and scoring server. This information should be provided by the timing organization for the championship.

## HTML Scraping​

The HTML scraping connection is generally used for championships that do not provide an official data feed. The protocol works by reading a website with timing data at fixed intervals and determining the timing data based on the changes in the website each time it is read.

When connecting with an HTML scraping protocol a browser window will open at the URL that is defined in the championship project item. This browser can be used to navigate through menus if required to get to the correct website view. The browser should not be closed while data is being read from the website. Often the HTML scraping protocols have some weaknesses and inaccuracies as this is not a supported operation and some of the data has to be estimated by HH Timing.

For carrying out post-race analysis in series where HTML scraping is the only way to get live data, importing the post-session data [https://help.hhtiming.com/timing-data-management/timing-scoring-data-import] supplied by the organizer is suggested.

## FTP Server​

The FTP Server connection is used when the timing and scoring server is implemented as a FTP server. So far this is only used for the official Blancpain timing service. From a technical perspective using an FTP Server for live timing data is a relatively poor option however, there is one advantage. As the data is stored in a file structure all previously published data can be access no matter when you connect during a session. This means if you connect to a session late or have a computer crash, you can still retrieve all missed session data.

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
- Data tab — https://help.hhtiming.com/getting-started/ribbon-bar/data
- Championship project item — https://help.hhtiming.com/settings-options/championship-configuration
- importing the post-session data — https://help.hhtiming.com/timing-data-management/timing-scoring-data-import

