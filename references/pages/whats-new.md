---
url: https://help.hhtiming.com/whats-new
title: Blog
slug: whats-new
---

# Blog

## 2025 June Release [https://help.hhtiming.com/whats-new/2025-june]

June 10, 2025 · 3 min read

The 2025 June release of HH Timing brings exciting improvements, many of which were requested by you! So thank you for continuously sharing your feedback and ideas. We have also included numerous bug fixes for improved stability.

As always, if you have any questions or issues with the release, please contact us at support@hh-dev.com.

## Full Track Map​

It is now possible to zoom in on different cars on the Full Track Map.

This feature enables a closer view of one or multiple vehicles during a session.

In the example below, the view is focused on the three safety cars used at Le Mans:

![](https://help.hhtiming.com/assets/images/2025_june_release_03-3fa68e1d3dc10a0a14e61db4545e0b01.png)

The zoom can also be applied to cars from the same team, offering a detailed view of their positioning on track.

For instance, the following image shows a zoom on two cars from the same team:

![](https://help.hhtiming.com/assets/images/2025_june_release_04-ef29d5bed270c8d5d5d97edf41e3102a.png)

The zoom level can be adjusted manually using the slider to set the desired scale.

To activate this feature, the Zoom On Car [https://help.hhtiming.com/displays/track-maps/full-track/#zoom-on-car] option must be enabled from the ribbon in the Full Track Map. When active, the map automatically centers around the selected reference car, adapting the view dynamically as their position evolves.

## Advanced Car Stopwatch​

The Advanced Car Stopwatch [https://help.hhtiming.com/displays/clocks/#advanced-car-stopwatch] now includes additional visual indicators to enhance race monitoring and analysis.

### Pit Entry / Pit Exit Light Status​

Two new columns can be added via dedicated checkboxes to display the pit entry and pit exit light status.
These indicators reflect real-time conditions and are updated as soon as the light status changes.

Below is an example where the pit entry is red because track status is Prepare for FCY then FCY:

![](https://help.hhtiming.com/assets/images/2025_june_release_01-8e1e64d36e35d7388b4e215218456b20.png)

And an example where Track Status in Red under the FCY then Green when the FCY ends:

![](https://help.hhtiming.com/assets/images/2025_june_release_02-df710fdab36d03b5f5fea4e6128fa0f0.png)

### Safety Car Highlighting​

All Safety Cars now appear with a yellow background color in the stopwatch.

![](https://help.hhtiming.com/assets/images/2025_june_release_05-72c0b49645599a48d09410936b114316.png)

## Quick Access to Car Scoreboard​

A double mouse wheel click on any car row in the Main Scoreboard now opens the Car Scoreboard for that specific car.

This provides a fast and convenient way to access detailed timing information without navigating through the tree or the ribbon bar to add the car scoreboard.

## Use Micro sectors as main sectors (WEC [https://help.hhtiming.com/series-specific-info/lm24/#microsectors---using-slow-zones-as-main-sectors-experimental], EXPERIMENTAL)​

When available from the timing feed, microsectors can be used in place of standard sectors to allow for more granular timing analysis.

### Defining Micro Sectors​

Microsectors must be entered either in pairs or triplets:

- Pair format: entry,exit→ sectors are automatically named MS1, MS2, ...
- Triplet format: name,entry,exit→ allows assigning custom names to each sector
Each microsector definition should be separated by a semicolon (`;`).

#### Example​

Using triplets, Slow Zones can be created at Le Mans with timing lines from the feed:

- FL to Z4
- Z4 to IP1
- IP1 to Z12
- Z12 to A7-1
- A7-1 to A8-1
- A8-1 to SCLB
- SCLB to PORIN
- PORIN to POROUT
- POROUT to FL
Micro Sectors: SZ1,FL,Z4;SZ2,Z4,IP1;SZ3,IP1,Z12;SZ4,Z12,A7-1;SZ5,A7-1,A8-1;SZ6,A8-1,SCLB;SZ7,SCLB,PORIN;SZ8,PORIN,POROUT;SZ9,POROUT,FL

![](https://help.hhtiming.com/assets/images/2025_june_release_07-760f8f0767859f2a52feda75d4ea328b.png)

To ensure full functionality — including features such as ghost cars — the dedicated Track Map must be used.

![](https://help.hhtiming.com/assets/images/2025_june_release_08-43fd9549a80b25b37f979ad26e82ebd9.png)

![](https://help.hhtiming.com/assets/images/2025_june_release_06-ac0b51fea4ef7214daa14e814671f75e.png)

caution

- The option "Use Micro Sectors As Main Sectors" must be enabled to activate this feature.
- The server must be updated.
- This feature is experimental.
- We recommend you remove the SZs you entered in the additional options.

## 页面相关链接（站点导航）

-  — https://help.hhtiming.com/whats-new/atom.xml
- Docs — https://help.hhtiming.com/getting-started/website/access/
- What's New — https://help.hhtiming.com/whats-new
- 2025 June Release — https://help.hhtiming.com/whats-new/2025-june
- 2025 April Release — https://help.hhtiming.com/whats-new/2025-april
- 2024 February Release — https://help.hhtiming.com/whats-new/2024-february
- 2023 November Release — https://help.hhtiming.com/whats-new/2023-november
- help section on gap graph — https://help.hhtiming.com/displays/graphing/gap-graph/
- "Copy Track Loops" option — https://help.hhtiming.com/tips_tricks/copy-loops-list/
- Perugia timing protocol — https://help.hhtiming.com/timekeeper-specific-info/perugia-timing/
- car off track display — https://help.hhtiming.com/displays/car-off-track/
- ➔ Complete Help section — https://help.hhtiming.com/timing-data-management/remote-replays-database/
- ➔ Complete Help section — https://help.hhtiming.com/displays/graphing/gps-speed/
- ➔ Complete Help section — https://help.hhtiming.com/displays/track-limits-warning/

