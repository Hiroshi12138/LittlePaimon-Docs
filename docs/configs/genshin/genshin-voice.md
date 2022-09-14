---
title: 原神语音
icon: markdown
order: 7
category:
  - 功能配置
---

## 更新原神语音资源
::: tip 需超级用户权限。
:::
更新原神语音相关资源。
- 命令：**`更新原神语音资源`**
- 示例：
  - `更新原神语音资源`

## 原神语音
获取指定角色的指定语音或随机一条语音。
- 命令：**`原神语音<角色名|序号>[语言]`**
- 参数：
  - 角色名：支持别名，随机发送一条该角色的语音
  - 序号：角色名和序号**二选一**，为序号时则指定一条语音，序号从命令`原神语音列表`获得
  - 语言：可选`中|英|日|韩`，默认为`中`
- 示例：
  - `原神语音钟离 中`
  - `原神语音1234`

## 原神语音列表
查看指定角色指定语言的原神语音列表。
- 命令：**`原神语音列表<角色名>[语言]`**
- 参数：
  - 角色名：支持别名
  - 语音：可选`中|英|日|韩`，默认为`中`
- 示例：
  - `原神语音列表钟离`
  - `原神语音列表胡桃 日`

## 原神猜语音
原神猜语音小游戏，bot会发送一条语音，看谁第一个猜对是哪位角色的语音。
- 命令：**`原神猜语音[语言]`**
- 参数：
  - 语音：可选`中|英|日|韩`，默认为`中`
- 示例：
  - `原神猜语音`
  - `原神猜语音日`
---
查看原神猜语音小游戏排行榜。
- 命令：**`原神猜语音排行榜`
- 示例：
  - `原神猜语音排行榜`

## 原神AI语音合成
使用原神语音合成api，合成指定角色的指定文本内容的语音。
- 命令：**`<角色名>说<内容>`**
- 支持角色：`派蒙|凯亚|安柏|丽莎|琴|香菱|枫原万叶|迪卢克|温迪|可莉|早柚|托马|芭芭拉|优菈|云堇|钟离|魈|凝光|雷电将军|北斗|甘雨|七七|刻晴|神里绫华|戴因斯雷布|雷泽|神里绫人|罗莎莉亚|阿贝多|八重神子|宵宫|荒泷一斗|九条裟罗|夜兰|珊瑚宫心海|五郎|散兵|女士|达达利亚|莫娜|班尼特|申鹤|行秋|烟绯|久岐忍|辛焱|砂糖|胡桃|重云|菲谢尔|诺艾尔|迪奥娜|鹿野院平藏'`，必须为全名
- 示例：
  - `八重神子说旅行者祈愿全保底，旅行者副本零掉落`
  - `钟离说我没有摩拉`