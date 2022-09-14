---
title: 原神便签与札记
icon: markdown
order: 4
category:
  - 功能配置
---

## 实时便签
::: tip
该功能需要绑定私人Cookie。
:::
查看原神实时便签（包含当前树脂、钱币、派遣等信息）。
- 命令：**`ssbq(uid)`**
- 别名：`实时便笺|实时便签|当前树脂`
- 示例：
  - `ssbq100123456`
::: details 实时便签图
![ssbq](https://static.cherishmoon.fun/LittlePaimon/readme/ssbq.jpg)
:::
---
设置实时便签提醒，在树脂|钱币达到一定量时向你发送提醒。
- 命令：**`ssbq提醒开启|关闭 (树脂|钱币)(数量) (uid)`**
- 示例：
  - `ssbq提醒开启树脂160 100123456`
  - `ssbq提醒开启树脂120钱币1000 100123456`

## 每月札记
::: tip
该功能需要绑定私人Cookie。
:::
查看指定月份的原石、摩拉获取情况。
- 命令：**`myzj (月份) (uid)`**
- 别名：`札记信息|每月札记`
- 参数：
  - 月份：必须为阿拉伯数字，只能查看近三个月的，默认为本月
- 示例：
  - `myzj100123456`
  - `myzj8 100123456`
::: details 每月札记图
![myzj](https://static.cherishmoon.fun/LittlePaimon/readme/myzj.jpg)
:::