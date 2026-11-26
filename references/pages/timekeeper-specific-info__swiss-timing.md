---
url: https://help.hhtiming.com/timekeeper-specific-info/swiss-timing/
title: Swiss timing
slug: timekeeper-specific-info__swiss-timing
---

# Swiss timing

-
- Timekeeper specific info
- Swiss timing

# Swiss timing

## Additional Options​

### Additional sectors​

You can create your sectors with all loops.

For example at GTWC Imola, there are 5 timing lines: F, I1, I2, PI and PO, 2 speed traps on track: F and S2 and 2 speed traps in pits: PI and PO. You can create a sector from F to S2 for example by adding it to the additional options of the championship configuration before connecting:

![](https://help.hhtiming.com/assets/images/swiss_timing_1-8145731d7143bbb924547f970de531c2.png)

You can choose the name you want but the value should always be:
Loop1;Loop2

caution
You can only define additional sectors on a computer directly connected to Swiss Timing Protocol (server). Client computers connected via the server mode will receive automatically the same sectors than the server.

### Auto selection of the FTP Directory (Experimental)​

You can now automatically select the FTP Directory by setting FTP Directory to auto.

![](https://help.hhtiming.com/assets/images/swiss_timing_2-50ac71bd3a2fc1d4d6ac9c80dbeac23a.png)

It will automatically connect to the latest session, including sessions from other championships. You can add filters in the championship configuration to avoid getting data from those series.

### FTP Block Strings​

Automatically selecting the FTP directory will connect to each new session. For example, during a GTWC meeting, GT3, GT4, and other series will be recorded. Specific series can be blocked by adding them to the FTP Block Strings options:

[内嵌示意图]

### Use Swiss Timing Lap Number​

In GTWC Europe, invalid laps are overwritten in the feed. This means the deleted lap will not be identified, and when exporting all laps in HHDM or Excel, the total number of laps for the car will be incorrect.
An option has been added to let HH Timing increment the lap number. This option is called "Use Swiss Timing Lap Number". We recommend to set it to false in practice/qualifying and to true in race.

[内嵌示意图]

### Track Limits and invalidated laps​

Swiss Timing now send Track Limits Warnings and invalidated laps. Track Limits Warnings are send few seconds after it happened (between 10s and 1 minute) and are displayed in the Track Limits Warning Scoreboard, and in the Race Control Messages.  You can also add the column #TLW in the Main Scoreboard and the Driver Scoreboard.
Then Swiss Timing add a flag invalid to the lap. The information is often sent many minutes after the TLW happened. It will be displayed in the car scoreboard, in the column TrackLimits. The lap will also be invalidated, so the main scoreboard will be updated if needed.

## Kafka Connection​

Swiss Timing offers a Kafka-based feed as an alternative to FTP. It provides lower latency and does not require selecting an FTP directory — HH Timing subscribes automatically to the active session.

### Championship Configuration​

By default, a championship called "Swiss Timing Kafka" is created in all new projects. Double click on it to open it in your workbook and verify the settings below.

The Kafka feed can be accessed either locally from the timing network at the circuit, or remotely via the cloud host.

Local (timing network at the circuit):

 |  |
| Protocol | Swiss Timing Kafka
| Host | 10.2.40.3
| Port | 9093
Cloud:

 |  |
| Protocol | Swiss Timing Kafka
| Host | evhns-prod-realtime-msp-westeurope.servicebus.windows.net
| Port | 9093

## Live Connection​

### Connecting to Timing Network​

The timing feed network is provided and maintained by Swiss Timing. A diagram provided by Swiss Timing of this network is shown below. Note that there are two ways of connecting to the network:

- Wirelessly via a 5GHz network
- RJ45 network cable at one of the 3 (typically) network switches along the pit wall

![](https://help.hhtiming.com/assets/images/swiss_timing_3-0b4c198d85f00861daf3244cdc93a11f.png)

#### Wireless Connection​

The details for logging into the wireless network should be obtained from Swiss Timing, normally they send documentation to explain the login details. To our knowledge the following login details should be correct:

- Wireless Network name: XMLFEED#
- Network Password: TEAMS2023

#### Wired Connection​

The recommended method of connection is via a physical connection to one of the network switches along the pit wall. Depending on your position in the pit lane, the connection to the wireless network can be mixed. In more modern pit lanes there may be an option to run/use a network cable underneath the pit lane to your garage. Otherwise, you may need to use a pair of point-to-point antennas to "jump" the pit lane and get a reliable connection to the timing feed if you plan to stay in your garage during the sessions as opposed to sitting on the pit wall.

Swiss Timing suggest not using a network cable longer than 85m to connect to the timing network.

### FTP System​

Swiss Timing uses an FTP (File Transfer Protocol) service to distribute live timing data to teams. This is an unusual way to provide timing data with Swiss Timing being the only motorsport timing provider to manage timing data in this way. As a result, connecting to the timing feed is a little more involved than in other championships.

The timing data is stored within a file structure that is hosted on a server that is accessible via a local network at the circuit. The timing data is accessed by the user pointing HH Timing to the correct part of the folder structure for that specific event. This means at each event the user must define the folder path for the timing data for that event.

### Determining the File Path​

#### Using the "Select FTP Directory" button​

To determinate the correct file path, you can use the "Select FTP Directory" button. You will need to complete all protocol information first:

![](https://help.hhtiming.com/assets/images/swiss_timing_4-fefa7be8b9bda294fad868251c732332.png)

Then click on the "Select FTP Directory " button.

[内嵌示意图]

A popup window will appear (for local FTP, it won't work with remote FTP).

The tree structure will depend on your championship. In GTWC for example, the first level contains all rounds. So you have to select the current round by clicking on it.

![](https://help.hhtiming.com/assets/images/swiss_timing_6-0e824fd53f1c50a33505038f9a9bfb2e.png)

The second level contains the different championships (or a folder for Paid sessions and one for "regular' sessions) taking place during this round. GTWC Endurance Cup and GT4 for example or GT WorldChEu and Official Paid. Select your championship by clicking on it:

![](https://help.hhtiming.com/assets/images/swiss_timing_7-3dfb1d58f34d51992a46ecd1c6568558.png)

The next level contains the different sessions. You don't have to select any (HH Timing will automatically select the last session). Just click on Ok.

![](https://help.hhtiming.com/assets/images/swiss_timing_8-6d3590ff8d9fcbcdb9123f17965275d9.png)

The FTP Directory field should now be filled.

caution
You will have to wait few seconds before seeing the tree. If the window remains blank after 10s, or if you have an error (The Page Failed to Load), please check your connection to the timing by opening a command prompt and typing: ping xml-motorsport.sportresult.com

#### Using Filezilla​

To dete*rmine the correct file path you can use a FTP client software. This will allow you to visualize the folder structure to verify the correct path. This is important in the case Swiss Timing vary the syntax for the folder structure. Using an FTP client software also serves a secondary purpose to check that your computer is able to access the FTP server. If your computer is not able to access the FTP server via the FTP client software, then you know the issue is either with your connection, or the Swiss Timing server and not HH Timing.

A computer not being able to access the FTP server because of a connection issue is the most common issue for users having issues with live data. If HH Timing seems to be having trouble showing data, the first thing is to check your computer can "see" the correct folders on the FTP server independently HH Timing by using a FTP client software.

Any FTP client software can be used to check and access the FTP server, the steps for using the free FTP client software "FileZilla" are given below. FileZilla can be downloaded  here. Select the "FileZilla Client" as shown below for download.

![](https://help.hhtiming.com/assets/images/swiss_timing_9-1e96ce886e54c3a1caf27eaa2d630bd8.png)

After installing and launching FileZilla the first step is to create a new profile:

![](https://help.hhtiming.com/assets/images/swiss_timing_10-b2961f73b2aa4f00173fed7f52643685.png)

Click New Site, enter a name of your choice. In the General tab, configure the settings as shown below:

- Host - The correct Host will be given to you from Swiss Timing as part of their information, to date this has always been: xml-motorsport.sportresult.com
- User - The correct User will be given to you from Swiss Timing as part of their information, in 2023 this should be: xml-motorsport.sportresult.com|xml
- Password - The correct Password will be given to you from Swiss Timing as part of their information, in 2023 this should be: TEAMS2023

![](https://help.hhtiming.com/assets/images/swiss_timing_11-4a380b8054e97d193e5155d01ca5753a.png)

In the Transfer Settings, set the Transfer Mode to Active as shown below:

![](https://help.hhtiming.com/assets/images/swiss_timing_12-8b7f63841bd1a948cae9dbbaac1b0694.png)

The FTP site is now created and every time you want to access the site you can select it from the drop down menu without having to reenter the connection information. Click on small arrow and select site you made previously as shown below:

![](https://help.hhtiming.com/assets/images/swiss_timing_13-ad991f5f2e5a0d6dfdcec438ae9d24e9.png)

If your computer can access the FTP you will see this in the Connection Status Information are shown below. The files on your local PC are on the left, and if you have access to the FTP you will see the timing data file structure on the right side.

![](https://help.hhtiming.com/assets/images/swiss_timing_14-b9c610f8fac48e5d1f62d7eb18f4bc51.png)

Now that FileZilla is connected to the T&S Server, the next step is to locate the directory for the session that you are interested in. An example of how the relevant directory would appear to a user in FileZilla is shown below:

![](https://help.hhtiming.com/assets/images/swiss_timing_15-c1c0c766e400c450bd671e2feb222390.png)

### Championship Configuration in HH Timing​

Once located, this information needs to be entered in the appropriate championship configuration [https://help.hhtiming.com/settings-options/championship-configuration]. By default, a championship called “Blancpain FTP” is created in all new projects.  Double click on this item to open it in your workbook.  Enter the path in the “Additional Connection Information” field as shown in the following screenshot.

 |  |
| Protocol | Swiss Timing FTP
| Host | xml-motorsport.sportresult.com
| Username | xml
| Password | Teams2023

#### FTP Directory​

The FTP Directory is the part you can copy from the FTP directory in FileZilla. You will find the directory path in the "Connection Status Information" after clicking through to the correct path in the "Files on FTP Server" section.

A feature has been added to HH Timing to automatically identify the correct session folder on the FTP server. This means the user only needs to update the FTP Directory once per event. The user needs to manually add the text NEWEST to the end of the FTP Directory. The software will then always check for the newest results folder and import the data accordingly.

An example of what the entire entry into the FTP Directory field in HH Timing was at the BES Monza round in 2018 is shown below. Take note to ensure all syntax is respected, particularly the forward slashes.

![](https://help.hhtiming.com/assets/images/swiss_timing_16-c658b19af13ccee4af8ac5ecc1b45ab5.png)

Note that at some events Swiss Timing have been treating the Bronze Test at the start of the weekend as a separate event, if so the FTP Directory will need to be defined separately for the Bronze Test and then for the regular remaining sessions.

Below is an example if the folder structure that you will see in FileZilla, in this case for the Bronze Test at the Spa 24H 2018. Highlighted in red is the part of the directory you need to copy into the FTP Directory field in HH Timing. For this example, the full path to enter into HH Timing should be:

```
/TOTAL 24 Hours of Spa Round 7/TOTAL 24 Hours of Spa Bronze Test/
```

![](https://help.hhtiming.com/assets/images/swiss_timing_17-95cad9d9fd9d7267f26824dedb619118.png)

#### Speed Trap Lines​

Normally the speed traps are automatically managed by HH Timing without any input from the user. Unfortunately Swiss Timing have a history of using inconsistent convention a some events. Typically, there are 3 speed traps included in the timing feed at the following positions:

- Finish Line (F for Finish)
- End of Sector 1 (I1 for Interval 1)
- End of Sector 2 (I2 for Interval 2)
If this is the case (and Swiss Timing use consistent syntax), then the required input for the Speed Trap Lines would typically be:
F,I1,I2

Note the values are comma separated with no spaces.

These speed traps are sometimes not at the same positions on track as the ones provided on some of the PDF format results that teams may be used to referring to. This is controlled by Swiss Timing and HH Development have no control over this.

If one or all of the speed traps are not being shown within HH Timing, you should check with Swiss Timing which position on track the speed traps are located and what convention they have used to name them.

tip
Monza: F, I1, I2, S2, PI, PO
Imola: F, S2, PI, PO
Brands Hatch: F, I1, I2, S3, S5, PI
Paul Ricard: F, I1, I2, S3
Valencia: F,I1,S1,PI,PO
Zandvoort: F,I1,I2,S2,PI,PO

#### Connection​

Once the championship configuration [https://help.hhtiming.com/settings-options/championship-configuration] is ready and you have connection to the FTP server, you can click the connect button in the data tab [https://help.hhtiming.com/getting-started/ribbon-bar/data] to connect as you would in any other championship.

## Post-Session Static Data Import​

To import the complete results for each session, timing and scoring data can be downloaded from the GT World Challenge Team Area in "Race by Race Information" section.

### Timed Session Data​

Download the Session_Name Sector List (CSV Format) for the session of interest. Then use the Import T&S Data button in the Data tab, select Timed, and navigate to the correct file.

![](https://help.hhtiming.com/assets/images/swiss_timing_18-2f3c38737611faf6f4a7e8405a93d853.png)

### Race Data​

As Swiss Timing do not provide a single data file with all the required information to display all the data correctly, two files for the relevant session must be downloaded:

- Session_Name Pit Stop List (PDF Format)
- Session_Name Sector List (CSV Format)
Then use the Import T&S Data button in the Data tab, select Timed, and navigate to the correct file.

![](https://help.hhtiming.com/assets/images/swiss_timing_19-f938539dd193db7ad729203f117fcea4.png)

![](https://help.hhtiming.com/assets/images/swiss_timing_20-597f59ad0334829d42c740aecefcd312.png)

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
- Swiss timing — https://help.hhtiming.com/timekeeper-specific-info/swiss-timing/
- Time service — https://help.hhtiming.com/timekeeper-specific-info/time-service/
- TSL Timing — https://help.hhtiming.com/timekeeper-specific-info/tsl-timing/
- ITS Chrono — https://help.hhtiming.com/timekeeper-specific-info/its-chrono/
- Alkamel V2 — https://help.hhtiming.com/timekeeper-specific-info/alkamel-v2/
- Alkamel standard — https://help.hhtiming.com/timekeeper-specific-info/aklamel-standard/
- USAC Timing — https://help.hhtiming.com/timekeeper-specific-info/usac/
- Perugia Timing — https://help.hhtiming.com/timekeeper-specific-info/perugia-timing/
- MyLaps X2 Server — https://help.hhtiming.com/timekeeper-specific-info/MyLaps-X2/
- MyLaps HTML Scraping - Speedhive — https://help.hhtiming.com/timekeeper-specific-info/MyLaps-SpeedHive/
- Cronococa Enhanced RMon Timing — https://help.hhtiming.com/timekeeper-specific-info/Cronococa/
- Calculation definition — https://help.hhtiming.com/calculation-definitions/driving-time/
- Plugins — https://help.hhtiming.com/plugins/drive-time-plugin/
- Tips & tricks — https://help.hhtiming.com/tips_tricks/
- Tutorial videos — https://help.hhtiming.com/videos/getting-started/
- Support — https://help.hhtiming.com/support/email/
- Notes — https://help.hhtiming.com/notes/v0-9-plugin-updates/
- championship configuration — https://help.hhtiming.com/settings-options/championship-configuration
- data tab — https://help.hhtiming.com/getting-started/ribbon-bar/data

