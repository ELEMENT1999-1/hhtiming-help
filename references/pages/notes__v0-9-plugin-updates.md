---
url: https://help.hhtiming.com/notes/v0-9-plugin-updates/
title: v0.9 plugin updates
slug: notes__v0-9-plugin-updates
---

# v0.9 plugin updates

-
- Notes
- v0.9 plugin updates

# v0.9 plugin updates

The goal of this document is to outline the changes that are required to update an HH Timing plugin from v0.8.x to v0.9.x.

Please note that not all changes may apply to all plugins.

## Preview version​

To make it easier to migrate the plugin a preview version of HH Timing 0.9 has been made available.  This release contains only minor breaking changes and therefore we believe that this should be sufficient for plugins to be updated.

### Downloading and running the client​

The beta build is available on the  releases page of the website:

### Example plugin​

Please see https://github.com/hh-development/hhtiming-drive-time-plugin/compare/master...release/2025-major for an example commit of a simple plugin being updated.

## Breaking changes​

### TargetFramework​

Replace every hard-coded `net7.0-windows` reference path with `$(TargetFramework)` so the plugin resolves the matching desktop binaries once the host moves to .NET 9.

### Windows Form​

add `WFO1000` in the property group of the csproj so the new Windows Forms analyzers do not block your build.

### Assembly.info​

Add `[assembly: SupportedOSPlatform("windows")]` in assembly.info because WinForms projects now require explicit OS targeting under .NET 9.

### Logging​

NLog was updated from v4 to v5, which made the way how we defined the logger in classes obsolete.

Old:

```
vb:Private Shared logger As ExtendedLogger = NLog.LogManager.GetCurrentClassLogger(GetType(ExtendedLogger))C#private static ExtendedLogger _logger = (ExtendedLogger)LogManager.GetCurrentClassLogger(typeof(ExtendedLogger));
```

New:

```
vb:Private Shared logger As ExtendedLogger = NLog.LogManager.LogFactory.GetCurrentClassLogger(Of ExtendedLogger)()C#private static ExtendedLogger logger = NLog.LogManager.LogFactory.GetCurrentClassLogger();
```

### PluginInfo.json​

A json file called PluginInfo.json with information about the plugin must be placed in the root directory of the plugin.  This is read by HH Timing as part of the loading process.

An example of the file contents follows:

```
{ "EntryDll": "HHTiming.DriveTime.dll", "TargetVersionNumber": "0.9"}
```

- EntryDll: the name of the file that contains the IHHTimingPlugin implementation (i.e. the main assembly of the plugin)
- TargetVersionNumber: the version of HH Timing the plugin is built to support. Currently supported versions are:"0.9"
This list will be updated as new versions of HH Timing are released. Versions will be removed when HH Timing is updated with breaking changes. When this happens, the plugin must be updated to support these changes and the TargetVersionNumber must be updated in order for the plugin to continue to be loaded by HH Timing.

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
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/
- IMSA 2026 replays — https://help.hhtiming.com/notes/imsa-2026-replays/

