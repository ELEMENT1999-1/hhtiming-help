# Support（支持与联系方式）

## 概述

Support 章节说明如何联系 HH Development 支持团队、如何发送日志文件与整个项目文件夹以便排障，以及如何用信用卡在线支付发票。共 4 个子页（本章节没有单独的根页，入口即 Email 页）。

## 子页 1：Email（邮件支持）

- URL：https://help.hhtiming.com/support/email/

### 完整要点

- 支持邮箱：**support@hh-dev.com**
- HH Development 团队成员常分布在不同时区；发到该地址的邮件会进入共享的客户管理工具（shared customer management tool），以便团队快速回复。
- 这是官方首选的联系渠道（优先于直接发给个人邮箱）。
- FAQ 中的价格咨询、系列赛添加请求也均指向该渠道。

## 子页 2：Sending log files（发送日志文件）

- URL：https://help.hhtiming.com/support/sending-logs/

### 完整要点

- 排障时官方可能索要错误日志：HH Timing 每次启动都会创建**按日期命名的文件夹**，并在其中生成 `log.txt`，记录相关事件与错误。
- **软件内打开**：File → Support → **Open logs folder**。
- **资源管理器手动打开**，路径：

  ```
  %localappdata%\HH Timing\Logs
  ```

- 该目录下每个运行日期一个文件夹；打开问题发生当天的文件夹，把其中的 `.txt` 日志文件发给支持团队。

## 子页 3：Sending an HH Timing project（发送项目文件）

- URL：https://help.hhtiming.com/support/sending-project/

### 完整要点

- 某些问题需要发送整个项目给官方分析。**必须发送整个项目文件夹**，而不只是项目文件本身。
- 项目文件夹默认位置：

  ```
  C:\Users\YOUR_USER_NAME\Documents\HH Timing\Projects
  ```

- 也可在软件 Backstage → Project Management 中查看项目路径。
- 项目文件夹内容结构中，项目文件本身只是其中一项（官方截图以红框标出）；应把包含全部内容的文件夹压缩（zip）后，用自选的文件分享工具（Dropbox、WeTransfer 等）发送。

## 子页 4：Paying with credit card（信用卡付款）

- URL：https://help.hhtiming.com/support/paying-credit-card/

### 完整要点

- **注意：该网页区块仅 Account Admin（账户管理员）用户可访问。**
- 步骤：
  1. 用获取许可证与软件下载时相同的凭据登录官网；
  2. 进入 Admin 区域下的 **Billing**；
  3. 输入发票号（invoice number）与金额，点击 **Make Payment**；
  4. 输入信用卡信息完成支付。

## 常见问答

- **Q：怎么联系官方支持？** A：发邮件到 support@hh-dev.com（首选渠道）。
- **Q：支持团队要日志，去哪里找？** A：File → Support → Open logs folder，或访问 `%localappdata%\HH Timing\Logs` 下对应日期文件夹中的 log.txt。
- **Q：支持团队要项目文件，发什么？** A：整个项目文件夹（默认在 `Documents\HH Timing\Projects\...`），zip 后分享；不要只发项目文件本身。
- **Q：在哪里用信用卡付款？** A：官网登录（与下载许可证同一账号）→ Admin → Billing → 填发票号与金额 → Make Payment；仅 Account Admin 可见该功能。
- **Q：价格/授权问题？** A：邮件联系 support@hh-dev.com 洽谈（租期 12 个月，含更新与邮件/电话支持）。
