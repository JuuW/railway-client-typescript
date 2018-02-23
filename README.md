# railway-client-typescript
High speed railway client (TypeScript version)


## Usage
1. 安装依赖包 `npm install`

2. 更改 **./dist/index.js** 文件中的账号和乘车信息。

3. 查询余票信息：`node dist/index.js leftTicketReport` ， 添加车次到 **./dist/index.js** 文件中

4. 订票: `node dist/index.js`，首次登录需要输入验证码，验证码文件 `./captcha.BMP`，打开验证码文件，找到答案对应的坐标依次输入到命令行窗口，用 "," 连接，例如：110,45,110,110,250,110

```
| 1 | 2 | 3 | 4 |
| 5 | 6 | 7 | 8 |
```

5. 取消排队订单：`node dist/index.js cancelOrderQueue`

### 查询余票

* `node dist/index.js leftTickets 2018-03-01 徐州 上海` 查询2018年3月1日徐州到上海的车票
* `node dist/index.js leftTickets 2018-03-01 徐州 上海 G,T` 查询2018年3月1日徐州到上海的高铁和特快车票

### 查询跨站余票

* `node dist/index.js passStationTickets 2018-03-01 上海 苏州 徐州` 查询2018年3月1日上海到徐州途经并停靠 **苏州** 的车票
* `node dist/index.js passStationTickets 2018-03-01 上海 苏州 徐州 G` 查询2018年3月1日上海到徐州途经并停靠苏州的 **高铁** 车票

输出报表数据如下：

```
3    |4       |5       |6       |7     |8    |9    |10   |11|20|21      |22|23  |24  |25    |26  |27|28  |29  |30    |31    |32
车次 |起始    |终点    |出发    |到达  |出发 |到达 |历时 |  |  |高级软卧|  |软卧|软座|特等座|无座|  |硬卧|硬座|二等座|一等座|商务座
G1970|上海虹桥|兰州西  |上海虹桥|苏州北|06:09|06:32|00:23|Y |  |        |  |    |    |      |    |  |    |    |有    |4     |7
G1802|上海虹桥|郑州东  |上海虹桥|苏州北|06:14|06:37|00:23|Y |  |        |  |    |    |      |    |  |    |    |有    |1     |1
G102 |上海虹桥|北京南  |上海虹桥|苏州北|06:30|06:53|00:23|Y |  |        |  |    |    |      |    |  |    |    |有    |11    |1
G108 |上海虹桥|北京南  |上海虹桥|苏州北|07:19|07:42|00:23|Y |  |        |  |    |    |      |    |  |    |    |有    |有    |1
G1974|上海虹桥|重庆西  |上海虹桥|苏州北|07:24|07:48|00:24|Y |  |        |  |    |    |      |    |  |    |    |有    |1     |无
G1232|上海虹桥|丹东    |上海虹桥|苏州北|07:39|08:12|00:33|Y |  |        |  |    |    |      |    |  |    |    |有    |无    |无
...
```

## Develop

`npm install`

`npm start` or `node dist/index.js`

### Prerequisites:

gulp: `npm install gulp -g`

## Updates

### v1.2

1. 新增跨站查询余票报表
2. 简化验证码输入方式
