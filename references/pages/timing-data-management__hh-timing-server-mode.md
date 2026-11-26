---
url: https://help.hhtiming.com/timing-data-management/hh-timing-server-mode/
title: HH timing server mode
slug: timing-data-management__hh-timing-server-mode
---

# HH timing server mode

-
- Timing data management
- HH timing server mode

# HH timing server mode

A server mode is available in HH Timing to allow the messages from the timing and scoring network to be forwarded to other instances of HH Timing. This can be useful in situations where only a single computer is able to connect to the timing feed due to the configuration of the supplied timing network. This allows a team to forward the timing information to as many computers within the team as required without requiring additional timing feed connections.

One instance of HH Timing shall act as the server.  All other instances of HH Timing act as clients and connect to the server instance of HH Timing.

## Setting up the Server​

By default, this feature is disabled and so the first step is to enable the feature. This is done by launching the software and enabling the feature in the user options.  At this point the port number can also be changed from the default value.  Once these changes are made the software must be restarted before they will take effect. The user is responsible for ensuring that the correct port is opened on any firewalls on the computer that will be acting as the server.

[内嵌示意图]

Once the software has been restarted, the server will start automatically (and unseen by the user).  Now, the software can be connected to the T&S network feed as normal, or a replay can be started for testing purposes.

The IP address of the server machine is shown on the "About" tab of the backstage.

![](https://help.hhtiming.com/assets/images/server_mode_2-769054a0739047fc37d158380b79c69f.png)

Note that it is the user needs to ensure that the IP address of the computer acting as the server does not change. If a static IP address is not used for the server machine and the IP address of the server is assigned a new IP address, the clients will have issues with timing dropouts. One option is to assign a static IP address to the server computer. The other is to use the computer name instead of the IP address to allow the clients to connect to identify the server on the network. One way to find the name of the client computer is to open command prompt and type “hostname”.

## Setting up clients​

To connect clients to the server instance of HH Timing a new championship item must be created (or an existing one can be edited or copied and edited).  The IP address should be set to point at the computer that is acting as the server and the port should be set to the value specified in the server instance.  Finally, the protocol should be selected as "HHTiming".  An example is shown below:

![](https://help.hhtiming.com/assets/images/server_mode_3-db1d8d4e93233c7ec4a411efdb35cb70.png)

caution
It is important the machine acting as the server has a static IP address. Otherwise if this computer is issued a new IP address the clients will no longer be able to connect to the server. Failing to do this is the most common reason for teams having issues with server mode.

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

