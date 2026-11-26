---
url: https://help.hhtiming.com/tips_tricks/backing-up-hh-timing-projects/
title: Backing up HH Timing projects
slug: tips_tricks__backing-up-hh-timing-projects
---

# Backing up HH Timing projects

-
- Tips & tricks [https://help.hhtiming.com/tips_tricks/]
- Backing up HH Timing projects

# Backing up HH Timing projects

Backing up your HH Timing projects is important. Hard drives can fail, and you don't want to lose your projects. However, issues can arise if you back up your projects folders while HH Timing is running. OneDrive's backup tool is susceptible to this: if HH Timing is running when you manually trigger a OneDrive backup, it can have sync issues especially with larger projects and poor Internet connections. This can result in the project database being renamed and HH Timing losing track of the database file.

To avoid issues like this, make sure you shut down HH Timing before starting a manual backup, whether that's using OneDrive or Dropbox or the built-in Windows backup tools.

The most common issue that can occur is a renaming of the HH Timing database file. If the file is renamed by the backup tool, HH Timing won't be able to find the database file and will display an error "Unable to load project".

If this happens, go to your My Documents folder, then the HH Timing folder. Find the folder for your project, and look in the DatabaseData folder:

[内嵌示意图]

That folder should only contain a file named HHDatabase.hhdb2. If another file with a similar name exists, it's likely that OneDrive created that new file when it couldn't back up the original file. If the HHDatabase.hhdb2 file is empty, you can delete it then rename the other file to HHDatabase.hhdb2.

If no HHDatabase.hhdb2 file exists at all, just rename the other file to HHDatabase.hhdb2.

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
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Saving screen space — https://help.hhtiming.com/tips_tricks/saving-screen-space/
- Router configuration — https://help.hhtiming.com/tips_tricks/router-configuration/
- Backing up HH Timing projects — https://help.hhtiming.com/tips_tricks/backing-up-hh-timing-projects/
- Switching project — https://help.hhtiming.com/tips_tricks/switching-project/
- Get loops list — https://help.hhtiming.com/tips_tricks/copy-loops-list/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/

