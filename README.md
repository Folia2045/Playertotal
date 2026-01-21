# PlayerTotal



一个支持 Minecraft 1.21.X 的服务器统计插件，记录玩家数据并提供 PlaceholderAPI 变量。

目前未对Folia核心进行适配



## 功能特性



- 自动记录每位玩家的名称和 UUID 到 JSON 文件

- 提供 PlaceholderAPI 变量显示不同时间段的玩家总数

- 支持管理员命令查看统计数据



## PlaceholderAPI 变量



- `%player_total%` - 显示服务器总玩家数

- `%player_day_player_total%` - 显示一天内加入的玩家数

- `%player_week_player_total%` - 显示一周内加入的玩家数

- `%player_mon_player_total%` - 显示一个月内加入的玩家数

- `%player_year_player_total%` - 显示一年内加入的玩家数



## 命令



- `/playertotal` - 查看统计数据

- `/playertotal reload` - 重新加载数据（需要 `playertotal.admin` 权限）



## 编译说明



由于系统中未安装 Maven，需要手动编译：



### 方法 1: 使用 Maven（推荐）



```bash

cd PlayerTotal

mvn clean package



# 编译后的 JAR 文件位于 target/PlayerTotal-1.0.0.jar

```



## 安装



1. 编译完成后，将 `target/PlayerTotal-X.X.X.jar` 复制到服务器的 `plugins` 文件夹

2. 确保已安装 PlaceholderAPI 插件

3. 重启服务器或使用 `/plugman load PlayerTotal` 加载插件



## 数据存储



玩家数据存储在 `plugins/PlayerTotal/playerdata.json` 文件中，格式如下：



```json

{

  "uuid-1": {

    "playerName": "玩家名称",

    "uuid": "玩家UUID",

    "joinTimestamp": 1737408000000

  },

  ...

}

```



## 依赖



- Paper API 1.21.4

- PlaceholderAPI 2.11.6

- Gson 2.10.1（已包含在插件中）
