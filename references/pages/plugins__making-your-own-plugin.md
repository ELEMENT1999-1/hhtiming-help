---
url: https://help.hhtiming.com/plugins/making-your-own-plugin/
title: Making your own plugin
slug: plugins__making-your-own-plugin
---

# Making your own plugin

-
- Plugins
- Making your own plugin

# Making your own plugin

The plugin framework in HH Timing was created to allow users to implement their own custom logic in the software.

HH Timing has been created using the .Net Framework and so plugins can be created using any .Net Framework language (C# or VB.Net for example).

The user interface of HH Timing was developed using WinForms and so any user interface elements in a plugin must also be developed using WinForms.

Currently the plugin framework allows you to:

- Create a custom tab in the ribbon bar to gain access to the plugin
- Create a display and receive timing data from the software in the form of “messages”
- Create and save items in the project in the software
- Create “data importers” for importing CSV, PDF and other static files
- Create “message parsers” to read data from a timing feed over a network connection, from an HTML web page or from an FTP server
- Access the project database using Entity Framework – note this requires an additional reference to the relevant Entity Framework libraries

## Creating a plugin​

To create a plugin you must have the following programs installed on your computer:

- .NET 9 SDK (installable via the Visual Studio workload selector or from Microsoft if you do not already have it)
- latest version of HH Timing
- latest version of Visual Studio 2022
Create a new Visual Studio project, and ensure that you target `net9.0-windows` (this is not always the default selection when you create a new project, so double-check the target framework before you begin coding).

You must add references to four HH Timing dlls to start creating your plugin:

- HHTiming.Core.Definitions.dll
- HHTiming.Desktop.Definitions.dll
- HHTiming.DAL.dll
- HHDev.ProjectFramework.Definitions.dll
- HHTiming.WinFormsControls.dll can also be added as a reference if you wish to extend any of the basic HH Timing controls. If you need support understanding any of these controls we can send further information or arrange a web meeting as required.
These files are located in the installation directory of the software which by default is
C:\Program Files\HH Development\HH Timing.

Please ensure that the CopyLocal flag is set to false for these references.

In the HHTiming.Desktop.Definitions.PlugInFramework namespace the interface IHHTimingPlugin interface is defined. The IHHTimingPlugin interface is the entry point for your plugin to be used in HH Timing. Your plugin must contain one class that implements this interface for it to be loaded into the software.

Once the IHHTimingPlugin interface has been correctly implemented you can begin writing your own components for HH Timing.

Some other interfaces that are important to understand when writing an HH Timing plugin are:

- IWorksheetControl: each display that is shown in a workbook of HH Timing is shown as a “worksheet”. To be displayed in a worksheet, a UserControl must implement the IWorksheetControl interface.
- IUIUpdateControl: in HH Timing all the processed live data is sent to controls using a messaging system. Each message implements the IUIUpdateMessage interface. The messages are broadcast to each registered IUIUpdateControl. The IUIUpdateControls can also request certain initialization messages from the database (e.g. all lap and sector times for a particular car). All of the IUIUpdateMessage implementations are contained in HHTiming.Core.Definitions.dll
- IProjectObject: each object that is saved to the project must implement the IProjectObject interface. Most importantly, this interface exposes Save and Load functions.

## Debugging your plugin​

Your plugin can only run as part of HH Timing and so you should set the debug start action to launch HH Timing.  To do this right-click on your Visual Studio project and select Properties.  On the Debug tab set the appropriate start action as shown in the following image:

![](https://help.hhtiming.com/assets/images/plugin_1-72c5bb61b4b07ba7a6c481cb1170e05a.png)

The path should be the installation path of HH Timing, which by default is: C:\Program Files\HH Development\HH Timing\HHTiming.Desktop.exe

Now you can use the "Start" button in Visual Studio to debug your plugin.

## Build Events​

Your plugin must be in Document/HH TIming/plugin

To do this right-click on your Visual Studio project and select Properties. On the Build Events tab, in the Post-build Event Command Line enter the following code (Don't forget to replace MyPlugin by your plugin name):

`if $(ConfigurationName) == Debug if not exist "$(registry:HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders@Personal)\HH Timing\Plugins\MyPlugin" mkdir "$(registry:HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders@Personal)\HH Timing\Plugins\MyPlugin"
if $(ConfigurationName) == Debug copy /y "$(TargetDir)" "$(registry:HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders@Personal)\HH Timing\Plugins\MyPlugin`

![](https://help.hhtiming.com/assets/images/plugin_2-d148f376a49be9c230620f52be185abd.png)

![](https://help.hhtiming.com/assets/images/plugin_3-39ae653301501ab78946986d16030e7a.png)

## Using your plugin​

If you didn't set up build even, you will have to place the zipped plugin folder (no need to unzip) in the following directory:

```
Documents\HH Timing\Plugins
```

When you start the software the plugin will appear in its own tab in the ribbon bar.

## Available Plugins​

Drive Time Plugin [https://help.hhtiming.com/plugins/drive-time-plugin]: the Drive Time Plugin was developed for use by teams competing in the GT World Challenge Endurance and provides some additional functionality to help with managing the driving time, stint time and pit stop length regulations.

Sample plugin source code can be found on our Github account.

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
- Drive Time Plugin — https://help.hhtiming.com/plugins/drive-time-plugin

