---
url: https://help.hhtiming.com/tips_tricks/router-configuration/
title: Router configuration
slug: tips_tricks__router-configuration
---

# Router configuration

-
- Tips & tricks [https://help.hhtiming.com/tips_tricks/]
- Router configuration

# Router configuration

For series where the timing feed comes over a network in pit lane, it is often a challenge to be able to receive both Internet and the timing feed over the same network.

We have found that using a business router such as an Ubiquiti Edge Router X configuration is a good, low-key solution.

Once acquired, the router needs to be setup in 4 parts:

- Interfaces
- Routing
- DHCP
- DNS Forwarding (Alkamel) The setup page for the router can usually be accessed from https://192.168.1.1
Timing access interface settings should be requested to the timing provider.

For timing provider that uses a DNS server, a setup of the DNS forwarding needs to be performed.

Internet access interface should be requested to the internet access provider.

## Interfaces​

- Port Eth0 is for the Timing connection using a fixed IP address.
- Port Eth1-Eth4 are the user connection and do not required special setup.

![](https://help.hhtiming.com/assets/images/router_1-abe7855e99b92bee26712f1fb418d6d8.png)

## Routing​

- Internet route via your Internet access interface (example 192.168.1.2)
- Timing route via the Timing interface (example 10.10.105.1)

![](https://help.hhtiming.com/assets/images/router_2-15a77aa47bf7afb60e5a03d0bcf313e6.png)

## DHCP​

- Set DNS 1 to the timing provider DNS (example 10.10.105.1)
- Set DNS 2 to Google DNS (8.8.8.8)

![](https://help.hhtiming.com/assets/images/router_3-ec65a51a892a2b2601f8e278a4a77066.png)

## DNS Forwarding​

- Set forwarding DNS request on "eth0" to the Alkamel DNS via the timing connection.

![](https://help.hhtiming.com/assets/images/router_4-bd66160cfa02708b184889377579d1df.png)

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

