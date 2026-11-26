---
url: https://help.hhtiming.com/settings-options/championship-configuration/
title: Championship configuration
slug: settings-options__championship-configuration
---

# Championship configuration

-
- Settings & options
- Championship configuration

# Championship configuration

## Making a New Championship​

To make a new championship click Add New Championship in the Components tab.

![](https://help.hhtiming.com/assets/images/championship_config_1-33dbc0eaa9f3a7153fd7101f3547cd4f.png)

The championship project item is used to define the network connection information for a given championship. Default championships for all supported championships are added to each new project. The championship project item is responsible for defining three types of parameters:

- Network connection information
- Championship filter information
- Championship specific information
A Championship Configuration is active when it is bold in the project tree [https://help.hhtiming.com/getting-started/project-tree], activate by right-clicking and select "Activate".

## Network Connection Information​

The network connection information allows you to specify how incoming data will be managed by the software by selecting communication protocol, entering the timing and server connection information and entering some configuration parameters if applicable. You can find information on series specific network information in the series specific information section.

In the project tree [https://help.hhtiming.com/getting-started/project-tree] you will find some pre-configured Championship Configurations. If the championship you need is not listed here you can create your own by going to the Components [https://help.hhtiming.com/getting-started/ribbon-bar/components] tab and selecting "Add New" Championship. You then select the protocol from the dropdown and input the data source details as shown below. If you are not sure what protocol to use you can ask us. In most series, it is best to get the host and port number from the timing provider but you are welcome to check with us.

The additional options are series specific and vary.

![](https://help.hhtiming.com/assets/images/championship_config_2-2c85fddfc92e1bce116cae5a74131d62.png)

The Championship Configuration network connection information will generally only need to be configured once per season as the connection details and protocol information do not generally change between events. There are some exceptions to this, see Series Specific Information section to see if this applies to the series you are part of.

## Championship Filter Information​

The championship filter is used to ensure that only data for the championship you are interested in following is added to the software. This can be useful for blocking data of other series so their cars and drivers are not added to your project.

The championship filter is defined by two parameters:

- Allow string
- Block string
The Allow string allows you to define words that MUST appear in the event name defined by the timing and scoring data feed to allow the data to pass.

The Block string allows you to define words that MUST NOT appear in the event name defined by the timing and scoring data feed to allow the data to pass.

Often, only one of these fields will be necessary to achieve the desired results.

![](https://help.hhtiming.com/assets/images/championship_config_3-43209a17e44684d6ff2f120f9228346d.png)

When enabled and blocking the timing and scoring, the filter will display a message at the bottom of the screen:

[内嵌示意图]

caution
The fields in the championship filter are case sensitive.

The championship filter can be disabled by deselecting the check box.

tip
As an example consider a championship filter for ELMS. The string that will be compared to the filter inputs is the session name which is defined by the timing provider. This can be found in the Session Data tab once you have connected to the timing feed for the first time. An example for the ELMS may look like this:

![](https://help.hhtiming.com/assets/images/championship_config_5-c3c15efb85fcb0c9af3ca6c26944cf56.png)

In this case, a suitable "Allow String" could be: " European Le Mans Series"

## Import a Championship Configuration​

To import a championship into your project, use the Import button in the Components tab.

![](https://help.hhtiming.com/assets/images/championship_config_6-91c9e91a49732d15c276bcf590f81c4e.png)

## Championship specific information​

In order to use the Championship points scoreboard [https://help.hhtiming.com/displays/scoreboards/championship-point-scoreboard] the points for each finish position muse be defined in the Championship Configuration. These are entered as shown below:

![](https://help.hhtiming.com/assets/images/championship_config_7-7dc03d5d1f4cd742f69e95f43f89c301.png)

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- Workbooks & layouts — https://help.hhtiming.com/workbooks-layouts/
- Displays — https://help.hhtiming.com/displays/
- Timing data management — https://help.hhtiming.com/timing-data-management/session-data/
- Settings & options — https://help.hhtiming.com/settings-options/backstage-settings/
- Backstage options — https://help.hhtiming.com/settings-options/backstage-options/
- Car options — https://help.hhtiming.com/settings-options/car-options/
- Championship configuration — https://help.hhtiming.com/settings-options/championship-configuration/
- Track item / Track Map / Ghosts — https://help.hhtiming.com/settings-options/track-item-ghosts/
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
- project tree — https://help.hhtiming.com/getting-started/project-tree
- Components — https://help.hhtiming.com/getting-started/ribbon-bar/components
- Championship points scoreboard — https://help.hhtiming.com/displays/scoreboards/championship-point-scoreboard

