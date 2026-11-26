---
url: https://help.hhtiming.com/whats-new/2025-april
title: 2025 April Release
slug: whats-new__2025-april
---

# 2025 April Release

# 2025 April Release

April 21, 2025 · 4 min read

The 2025 April release of HH Timing brings exciting improvements, many of which were requested by you! So thank you for continuously sharing your feedback and ideas. We have also included numerous bug fixes for improved stability.

Layout
Breaking change: layouts opened/saved with 0.8 versions won't load with versions 0.7.

As always, if you have any questions or issues with the release, please contact us at support@hh-dev.com.

## Advancing replay​

When replaying a session, you now have the option to jump to a specific session time, moving either forward or backward. This eliminates the need to replay the entire session from the beginning. A new button has been added to the replay bar in the bottom-right corner of the screen:

[内嵌示意图]

A control pop-up will let you set the desired elapsed time of the session you want to advance to:

[内嵌示意图]

After clicking the 'OK' button, HH Timing will process the replay and begin playback from the selected elapsed time.

## Graphs​

X and Y axes can be changed without creating a new graph. The selection can be made from the ribbon bar of any scatter plot or moving average graph:

[内嵌示意图]

Additionally, we implemented the ability to:

- change the car/driver series directly from the ribbon bar.
- filter the displayed series based on driver categorization.

![](https://help.hhtiming.com/assets/images/2025_april_release_04-c1655eeb1b289fb6b819b4744c4d1d88.png)

## Strategy overview​

The stint time can now be displayed on the strategy overview. This stint time is the time from pit out to pit in except fo rthe first or last stint where the race start/end times are used:

![](https://help.hhtiming.com/assets/images/2025_april_release_05-b0bfcf54194d51383030c1a6edbe88aa.png)

![](https://help.hhtiming.com/assets/images/2025_april_release_06-b86422a7b56429b01cf1a03baa97da15.png)

## Virtual finish ghost car​

A virtual finish ghost car is now available on the full track map. This feature displays a car running to a specified average lap time and finishing the session precisely when the session time reaches zero. This helps to quickly assess whether another lap is likely or not depending of the current track postion.

This setting can be changed on the ribbon bar of the full track map:

[内嵌示意图]

![](https://help.hhtiming.com/assets/images/2025_april_release_09-310af47b1848c3fde849245fbade6b1c.png)

GPS
The virtual ghost car does not work when using a GPS track map. This will be implemented in a future release.

## Alkamel V2 enhanced read history​

A newly enhanced option has been added to the Read History parameter of the championship config for the Alkamel V2 protocol. When enabled, HH Timing will process Alkamel lap and sector times correction messages (i.e. lap deleted for track limit or other penalty). Scoreboards and graphs will be updated accordingly:

[内嵌示意图]

## IMSA IWSC GTP telemetry​

HH Timing can now record and display IMSA telemetry data provided by IMSA GTP telemetry website: https://www.imsa.com/gtp-telemetry/.

Add the Enable Telemetry Reading parameter to the championship config from either IMSA Enhanced RMon Timing protocol (IMSA Timing) or Al Kamel V2 North America protocol to enable the recording.

[内嵌示意图]

Recorded from the telemetry, the following columns will be available on the main scoreboard:

- Energy Rem
- Energy Refill Time

![](https://help.hhtiming.com/assets/images/2025_april_release_11-36cb53c9eb0eb6bccae543d1c372aeb7.png)

Live data can be plotted using the telemetry graph (found under Displays --> Other Graphs) and selecting the Live Telem Plot Mode:

![](https://help.hhtiming.com/assets/images/2025_april_release_12-2d70b72bbc3f4a98eb2de6027bc8f62c.png)

Data Fidelity
The intention of IMSA is to provide an immersive experience and insight of the race strategy for fans, TV and radio commentators. Therefore the data is unofficial and may not reflect the reality. The website provides 1 Hz filered and rounded data.

## Indycar telemetry​

When using the RIS protocol with the option to record telemetry, you can now display live data on our telemetry graph (Displays --> Other Graphs) by selecting the Live Telem Plot Mode:

![](https://help.hhtiming.com/assets/images/2025_april_release_13-514adc450afd8e823d90b361b0cbaf65.png)

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- 2025 June Release — https://help.hhtiming.com/whats-new/2025-june
- 2025 April Release — https://help.hhtiming.com/whats-new/2025-april
- 2024 February Release — https://help.hhtiming.com/whats-new/2024-february
- 2023 November Release — https://help.hhtiming.com/whats-new/2023-november

